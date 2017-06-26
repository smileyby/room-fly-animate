直播间右下角的点赞特效
===================

通过时间函数实现,贴出主要逻辑代码：

```js

  var J = document.getElementsByClassName('bones')[0];
  setInterval(function() {
      function e() {
          n.removeEventListener('webkitAnimationEnd', e, !1),
          J.removeChild(n)
      }
      var n = document.createElement("span")
        , t = Math.ceil(180 * Math.random())                                    // 旋转角度
        , i = Math.floor(9 * Math.random())                                      // 图片地址
        , o = Math.floor(3 * Math.random())                                     // 动画时间
        , q = ['http://oqpmmru7y.bkt.clouddn.com/icon_floats_1.png', 'http://oqpmmru7y.bkt.clouddn.com/icon_floats_2.png', 'http://oqpmmru7y.bkt.clouddn.com/icon_floats_3.png', 'http://oqpmmru7y.bkt.clouddn.com/icon_floats_4.png', 'http://oqpmmru7y.bkt.clouddn.com/icon_floats_5.png', 'http://oqpmmru7y.bkt.clouddn.com/icon_floats_6.png', 'http://oqpmmru7y.bkt.clouddn.com/icon_floats_7.png', 'http://oqpmmru7y.bkt.clouddn.com/icon_floats_8.png', 'http://oqpmmru7y.bkt.clouddn.com/icon_floats_9.png',  'http://oqpmmru7y.bkt.clouddn.com/icon_floats_10.png'];        // 图片地址数组
      n.style.transform = "rotateZ(" + t + "deg)",                             // 设置旋转角度
      n.style["-webkit-transform"] = "rotateZ(" + t + "deg)",             // 设置旋转角度
      n.style.background = "url(" + q[i] + ") no-repeat",                   // 设置背景图
      n.style.backgroundSize = "contain",                                      // 设置背景图样式
      n.style.animation = "linear " + o + "s 0.2s bone",                   // 设置动画基本参数
      n.style["-webkit-animation"] = "linear " + o + "s 0.2s bone",   // 动画兼容
      J.appendChild(n),                                                                 // 追加元素
      n.addEventListener('webkitAnimationEnd', e, !1)                  // 设置事件监听，动画结束后移除元素本身和绑定的事件
  }, 120)

```
## 需要理解和注意的地方

1. 通过createElement来创建元素并追加到页面中的这种方式有什么优点？和直接拼写元素追加到页面有什么不同？
2. addEventListener/removeEventListener 函数的所有参数含义