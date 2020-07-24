---
title: " Vue中实现用户登录及token验证\t\t"
tags:
  - 其他
id: '131'
date: 2019-06-04 11:01:25
---

**Vue中实现token验证大致如下：**  
1、第一次登录的时候，前端调后端的登陆接口，发送用户名和密码  
2、后端收到请求，验证用户名和密码，验证成功，就给前端返回一个token  
3、前端拿到token，将token存储到localStorage和vuex中，并跳转路由页面（本项目根据是否记住密码来判断token存储到sessionStorage或 localStorage ）  
4、前端每次跳转路由，就判断 localStroage 中有无 token ，没有就跳转到登录页面，有则跳转到对应路由页面  
5、每次调后端接口，都要在请求头中加token  
6、后端判断请求头中有无token，有token，就拿到token并验证token，验证成功就返回数据，验证失败（例如：token过期）就返回401，请求头中没有token也返回401  
7、如果前端拿到状态码为401，就清除token信息并跳转到登录页面  

### **login.vue**

调登录接口成功，在回调函数中将token存储到localStorage、sessionStorage和vuex中

     methods: {
                handleSubmit(e) {
                    e.preventDefault();
                    this.form.validateFields((err, values) => {
                        if (!err) {
                            this.$api.user.login(values
                            ).then(res => {
                                if (res.data.id_token) {
                                    this.$store.commit('login',{token:res.data.id_token,rememberMe:values.rememberMe});
                                    this.$store.dispatch('initAccount');
                                    this.$router.push('/home');
                                }
                            }).catch(()=>{
                                this.$message.error('用户名或密码错误');
                            })
                        }
                    });
                },
            }

### store.js

登录成功以及退出登录的token处理

    import Vuex from 'vuex';
    import Vue from 'vue';
    
    
    Vue.use(Vuex);
    export default new Vuex.Store({
        state: {
            token: null,
        },
        mutations: {
            // 登录成功将, token保存在localStorage和sessionStorage中
            login: (state, data) => {
                if (data.rememberMe) {
                    localStorage.token = data.token;
                } else {
                    sessionStorage.token = data.token;
                }
                state.token = data.token;
            },
            // 退出登录将, token清空
            logout: (state) => {
                localStorage.removeItem('token');
                sessionStorage.removeItem('token');
                state.token = null
            },
        }
    })

### http.js

请求头部加token以及状态码处理

    /**
     * 请求拦截器
     * 每次请求前，如果存在token则在请求头中携带token
     */
    instance.interceptors.request.use(
        config => {
            // 登录流程控制中，根据本地是否存在token判断用户的登录情况
            // 但是即使token存在，也有可能token是过期的，所以在每次的请求头中携带token
            // 后台根据携带的token判断用户的登录情况，并返回给我们对应的状态码
            // 而后我们可以在响应拦截器中，根据状态码进行一些统一的操作。
            if (store.state.token) {  // 判断是否存在token，如果存在的话，则每个http header都加上token
                config.headers.Authorization = 'Bearer '+ `${store.state.token}`;
            }
            return config;
        },
        error => Promise.error(error));
    
    // 响应拦截器
    instance.interceptors.response.use(
        // 请求成功
        res => Promise.resolve(res),
        // 请求失败
        error => {
            const { response } = error;
            if (response) {
                // 请求已发出，但是不在2xx的范围
                errorHandle(response.status, response.data.message);
                return Promise.reject(response);
            } else {
                // 处理断网的情况
                // eg:请求超时或断网时，更新state的network状态
                // network状态在app.vue中控制着一个全局的断网提示组件的显示隐藏
                // 关于断网组件中的刷新重新获取数据，会在断网组件中说明
            }
        });
    /**
     * 请求失败后的错误统一处理
     * @param {Number} status 请求失败的状态码
     */
    const errorHandle = (status, other) => {
        // 状态码判断
        switch (status) {
            // 401: 未登录状态，跳转登录页
            case 401:
                toLogin();
                break;
            // 404请求不存在
            case 404:
                message.error('请求的资源不存在',5);
                break;
            default:
                console.log(other);
        }};