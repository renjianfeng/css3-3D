# css3-3D场景技术
css3场景技术是利用css3的3D变形和透视制作的基于css3的3d场景效果；

1.将浏览器的css3渲染模式改为3D
```css  
  -moz-transform-style: preserve-3d;
  transform-style: preserve-3d;
  -webkit-transform-style: preserve-3d;
```
2.设置透视距离
在3d世界中，离你近的东西看起来比较大，离你远的东西看起来比较小，这样我们在才能看到一个比较立体的世界。设置的代码入下：
```css  
   -moz-perspective: 900px;
   perspective: 900;
   -webkit-perspective: 900; /* Safari 和 Chrome */
```
注意这里除了头文件兼容，还要注意，在火狐和ie下面一定要注意后面的单位

3.旋转和移动
css3提供了transform的属性支持3d场景下面的位移和旋转
包含两个属性
rotate（旋转）
translate（位移）
3D场景中坐标由原来的二维坐标（x,y）变更为三维坐标，即(x,y,z)；
所以以上两个属性分别支持3方向的位移和旋转；
如
```css  
  transform: rotateX(20deg) rotateY(15deg) rotateZ(0deg) translateX(200px) translateY(300px) translateZ(300px);
```

4.动画
css3提供了两种动画模式，均是参考传统的交互动画，即animation（逐帧动画）和transtion（渐变动画），两种的使用场景参考如下；
anmimation
```css  
  .map_tu
        {
            animation: dh_nav 15s infinite linear ;
            -webkit-animation: dh_nav 15s infinite linear ;
        }
        @keyframes dh_nav {
            0% {
                transform: rotateX(0deg) rotateY(0deg) rotateZ(0deg) translateX(0px) translateY(300px) translateZ(0px);
                -webkit-transform: rotateX(0deg) rotateY(0deg) rotateZ(0deg) translateX(0px) translateY(300px) translateZ(0px);
            }
            50% {
                transform: rotateX(0deg) rotateY(180deg) rotateZ(60deg) translateX(0px) translateY(900px) translateZ(3000px);
                -webkit-transform: rotateX(0deg) rotateY(180deg) rotateZ(60deg) translateX(0px) translateY(900px) translateZ(3000px);
            }
            100% {
                transform: rotateX(0deg) rotateY(360deg) rotateZ(0deg) translateX(0px) translateY(300px) translateZ(0px);
                -webkit-transform: rotateX(0deg) rotateY(360deg) rotateZ(0deg) translateX(0px) translateY(300px) translateZ(0px);
            }
        }
```
 transtion
 ```css  
  .map_tu
        {
          -webkit-transition: 0.5s;
	        transition: 0.5s;
	        background:red;
        }
  .map_tu:hover
        {
          -webkit-transition: 0.5s;
          transition: 0.5s;
          background:green;
        }
```

当然css3的动画还有很多的效果，在这里我只是稍微列举一下，方便大家理解上面的代码，如果大家有兴趣，可以深入学习！
