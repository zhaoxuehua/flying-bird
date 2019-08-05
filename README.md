# flying-bird
The case of the flying bird

链接：https://zhaoxuehua.github.io/flying-bird/

简介

一、思路

1、游戏规则：鸟撞到管道上，地上要死亡，飞到屏幕外要死亡。

2、鸟在飞翔的过程中，会掉落，类似落体运动，需要玩家不断点击屏幕让鸟向上飞。

3、鸟和背景元素的相对移动的过程，鸟不动，背景左移。

二、游戏实现

1.设置canvas画布，准备图片数据，当图片加载完成后执行回调函数；

 注意： 必须保证图片资源加载完成后再执行其他操作  即需保证5张图片全部加载完毕后，进行游戏画面绘制，可以定义一个加载函数，当图片全部加载完返还给图片调用者，注意：在加载图片的过程中需监听每一张img的onload事件，当所有图片都触发onload则调用回调，把加载完毕的资源传递过去（存到某个对象中）
 
  小鸟的绘制
  
  天空的绘制  
  
  地面的绘制  与天空绘制大致同
  
  绘制管道   难点管道高度的绘制 
            管道必须有一个固定高度+一个随机高度，且上下管道之间的留白是固定的宽度
             管道不是连续的，两个相邻的管道之间有间隔
             管道在无缝播放，抽回后必须付给一个新的随机高度，给用户一种错觉，以为又一个管道飘了过来


三：判断游戏是否犯规
    接触到地面和天空顶部，结束游戏
    碰到管道结束游戏
    
    
    优化：为了更加形象，小鸟在点击鼠标后向上运动抬头，向下运动低头
     实现办法：移动canvas 坐标系和选择坐标系的角度  ctx.translate()和ctx.rotate()
