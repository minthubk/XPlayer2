# XPlayer2 
基于ijkPlayer的Android视频播放器

## 示例apk的安装
 adb install -t *.apk 
 (adb install -t /Users/android_ls/Desktop/app-debug.apk)

## 视频播放器组件提供的基本功能
- 支持播放直播流（rtmp）
- 支持播放各种格式的多媒体（MP4、flv、MP3）
- 支持多种视频画面显示方式：16:9、4:3、全屏、竖直居中等
- 支持常用的动画(旋转、移动、缩放)
- 支持倍速播放（加快或者减慢播放速度）

## 特性
- 列表中所有XIVideoView对象共享同一个XIMediaPlayer播放器对象，实现思路：  
  1.列表中所有XIVideoView对象共享同一个XIMediaPlayer播放器对象  
  2.从之前正在播放的卡片到新的将要播放的卡片，XIMediaPlayer播放器对象做的动作依次是stop、reset、
     setVideoPath、setSurface、play  
  3.XIMediaPlayer播放器对象创建非常消耗资源，所以推荐尽可能的共享  
  
- 大小视频窗口切换，实现思路：  
  1.采用多个XIVideoView共享同一个XIMediaPlayer播放器对象  
  2.在滚动结束后，为XIMediaPlayer对象设置当前显示XIVideoView所持有的Surface  
  3.XIMediaPlayer播放器播放视频的动作从未停止，只是切换展示视频画面的Surface而已，从而实现无缝切换大小窗口的功能  
  4.小窗口支持在屏幕任意位置拖动，在拖动过程中播放动作不中断。  

## 示例Demo运行后的截图
<img src="https://github.com/hpdx/XPlayer2/blob/master/images/demo_05.jpeg" width="270px"/>        <img src="https://github.com/hpdx/XPlayer2/blob/master/images/demo_06.jpeg" width="270px"/>

<img src="https://github.com/hpdx/XPlayer2/blob/master/images/demo_01.jpeg" width="540px"/> 

<img src="https://github.com/hpdx/XPlayer2/blob/master/images/demo_02.jpeg" width="540px"/> 

<img src="https://github.com/hpdx/XPlayer2/blob/master/images/demo_03.jpeg" width="540px"/> 

<img src="https://github.com/hpdx/XPlayer2/blob/master/images/demo_04.jpeg" width="540px"/> 

