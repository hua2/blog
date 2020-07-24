---
title: " CSS动画\t\t"
tags:
  - 其他
id: '53'
date: 2018-05-08 19:25:40
---

CSS动画的两大组成部分：transition和animation。 **CSS Transition**

    img{
        transition: 1s 1s height ease;
    }

    img{
        transition-property: height;
        transition-duration: 1s;
        transition-delay: 1s;
        transition-timing-function（变化速度）: ease;
    }
    （1）linear：匀速；（2）ease-in：加速；（3）ease-out：减速；（4）cubic-bezier函数：自定义速度模式

**CSS Animation** 我们还需要用keyframes关键字，定义rainbow效果。我们还需要用keyframes关键字，定义rainbow效果。

    @keyframes rainbow {
      0% { background: #c00; }
      50% { background: orange; }
      100% { background: yellowgreen; }
    }
    

0%可以用from代表，100%可以用to代表，因此上面的代码等同于下面的形式。

    @keyframes rainbow {
      from { background: #c00 }
      50% { background: orange }
      to { background: yellowgreen }
    }
    

另外一点需要注意的是，浏览器从一个状态向另一个状态过渡，是平滑过渡。steps函数可以实现分步过渡。

    div:hover {
      animation: 1s rainbow infinite steps(10);
    }
    

`animation-play-state:`如果想让动画保持突然终止时的状态，就要使用animation-play-state属性。

    div {
        animation: spin 1s linear infinite;
        animation-play-state: paused;
    }
    
    div:hover {
      animation-play-state: running;
    }

    animation的各种属性值简写：
    div:hover {
      animation: 1s 1s rainbow linear 3 forwards normal;
    }
    可以分解成各个单独的属性。
     div:hover {
      animation-name: rainbow;
      animation-duration: 1s;
      animation-timing-function: linear;
      animation-delay: 1s;
      animation-fill-mode:forwards;
      animation-direction: normal;
      animation-iteration-count: 3 (infinite，可以让动画无限次播放);
    }
    animation-fill-mode还可以使用下列值。
    （1）none：默认值，回到动画没开始时的状态;（2）backwards：让动画回到第一帧的状态;
    （3）both: 根据animation-direction（见后）轮流应用forwards和backwards规则animation-fill-mode还可以使用下列值。
    

**浏览器前缀** 目前，IE 10和Firefox（>= 16）支持没有前缀的animation，而chrome不支持，所以必须使用webkit前缀。实际运用中，代码必须写成下面的样子。

    div:hover {
      -webkit-animation: 1s rainbow;
      animation: 1s rainbow;  
    }
    
    @-webkit-keyframes rainbow {
      0% { background: #c00; }
      50% { background: orange; }
      100% { background: yellowgreen; }
    }
    
    @keyframes rainbow {
      0% { background: #c00; }
      50% { background: orange; }
      100% { background: yellowgreen; }
    }