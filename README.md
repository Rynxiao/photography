# 图片翻转(视觉错觉)案例

## 原理
设置的背景图片略小，定位居中靠上，背景图片周围颜色需与整个页面的背景融合，这样在翻转的时候不会出现色差问题

1. 两个div的背景颜色相同，一个div静止，另一个则在鼠标移动的时候控制其3D偏转，并且透明度要降低，这样才能造成“影子”的效果，同时设置过渡效果

2. 关于偏转公式

```javascript
var xVal = -1/(win.height/2)*ev.clientY + 1,
    yVal = 1/(win.width/2)*ev.clientX - 1,
    transX = 20/(win.width)*ev.clientX - 10,
    transY = 20/(win.height)*ev.clientY - 10,
    transZ = 100/(win.height)*ev.clientY - 50;
```
解析：

`xVal = -1/(win.height/2)*ev.clientY + 1`, 控制的是X轴的偏转角度，解析为：

win.height / 2 - ev.clientY

---------------------------

    win.height / 2

表示的是当鼠标在屏幕上方时，则为正值，那么上部就会向里偏，下部就会向外偏，造成画面随着鼠标移动的效果

同理，当鼠标在屏幕下方时，则为负值

其他解释同理
