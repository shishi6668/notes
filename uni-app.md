# uni-app框架上手官网文档学习随记
woc刚刚用typora写的那么多保存失败了，就剩个标题，我tm...
不写了，详情参考uni-app官网教程框架简介：https://uniapp.dcloud.io/frame
## 开发规范
- 页面文件遵循 Vue 单文件组件 (SFC) 规范
- 组件标签靠近小程序规范，详见uni-app 组件规范

推荐将div标签替换为view，span转text,a转navigator,img转image等。如果开发者写了div等标签，在编译到非H5平台时也会被编译器转换为view等标签，但不推荐

- 其他

## 页面样式与布局
1. ` 页面元素在uin-app中的宽度（rpx单位）计算：`
设计稿1px / 设计稿基准宽度px = 框架样式1rpx / 750rpx基准
=>
元素设计npx / 设计稿基准宽度px = 元素在框架中nrpx / 750rpx基准
=>
元素在框架中nrpx的n = n * 750 / 设计稿基准宽度
例如：若设计稿宽度为 640px，元素 A 在设计稿上的宽度为 100px，那么元素 A 在 uni-app 里面的宽度应该设为：750 * 100 / 640，结果为：117rpx。
注：rpx 即响应式px，一种根据屏幕宽度自适应的动态单位。以750宽的屏幕为基准，750rpx恰好为屏幕宽度。屏幕变宽，rpx 实际显示效果会等比放大;rpx不支持动态横竖屏切换计算，使用rpx建议锁定屏幕方向;App端，在 pages.json 里的 titleNView 或页面里写的 plus api 中涉及的单位，只支持 px，不支持 rpx。
2. 为支持跨平台，框架建议使用Flex布局。
