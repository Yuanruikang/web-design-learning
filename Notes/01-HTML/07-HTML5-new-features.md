# HTML5 新增语义化标签
* \<header>：头部标签
* \<snav>：导航标签
* \<article>：内容标签
* \<section>：定义文档某个区域
* \<aside>：侧边栏标签
* \<footer>：尾部标签

注意:
* 这种语义化标准主要是针对搜索引擊的
* 这些新标签页面中可以使用多次
* 在IE9中，需要把这些元素转换为块级元素
* 在移动端更喜欢使用这些标签
# 新增多媒体标签-\<video>
HTML5在不使用插件的情况下，也可以原生的支持视频格式文件的播放，但支持的格式是有限的。
当前,\<video>元素支持三种格式：尽量使用mp4格式  
[详见👉各浏览器对视频格式支持情况](https://www.runoob.com/tags/tag-video.html)

\<video>常见属性
| 属性     | 值                                         | 描述                                                          |
| :------- | :----------------------------------------- | :------------------------------------------------------------ |
| autoplay | autoplay                                   | 视频就緒自动播放（谷歌浏览器需要添加muted来解決自动插放问题） |
| controls | controls                                   | 向用户显示播放控件                                            |
| width    | pixels(像素）                              | 设置插放器宽度                                                |
| height   | pixels(像素）                              | 设置播放器高度                                                |
| loop     | loop                                       | 插放完是否继续播放该视频，循环播放                            |
| preload  | auto（预先加载视频）/none （不应加载视频） | 规定是否预加载视频(如果有了autoplay 就忽路该属性)             |
| src      | url                                        | 视频url地址                                                   |
| poster   | Imgurl                                     | 加载等待的画面图片                                            |
| muted    | muted                                      | 静音播放                                                      |

但一般用JS控制播放器控件
```html
<!-- 多播放源写法,若mp4不支持就执行ogg,若ogg格式也不支持就输出“浏览器不支持video标签” -->
<video width="320" height="240" controls>
    <source src="movie.mp4" type="video/mp4">
    <source src="movie.ogg" type="video/ogg">
    您的浏览器不支持 video 标签。
</video>
```
# 新增音频标签 <audio>
| 属性     | 值       | 描述                                             |
| :------- | :------- | :----------------------------------------------- |
| autoplay | autoplay | 如果出现该属性，则音频在就緒后马上播放。         |
| controls | controls | 如果出现该属性，则向用户量示控件，比如播放按钮。 |
| loop     | loop     | 如果出现该属性，则每当音频结束时重新开始插放。   |
| src      | url      | 要播放的音频的 URL。                             |












