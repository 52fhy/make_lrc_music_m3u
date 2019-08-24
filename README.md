# 网易云音乐歌单同步
![wiki](https://github.com/zanjie1999/make_lrc_music_m3u/raw/master/wiki.gif)

起个冷门名字防ban<br>
这个东西其实是弃了很久的坑的了<br>
之前做了一个读网易云音乐客户端本地数据库生成播放列表的东西,为我的mp3提供歌单<br>
但是这样要依赖客户端,用别人的电脑就不太方便了<br>
于是下定决心写一个可以自动更新mp3里的音乐的东西<br>
为了方便尽量只使用python标准库<br>
(比如可以把mp3插到路由器上运行一下新的音乐就下完了)<br>
<br>
最初只有下载歌词的功能的<br>
刚好找到个接口就顺便把自动下载缺失音乐的功能加上了,这样就不用整天去翻客户端缓存目录<br>
再想想反正歌单json都拿到了那就顺便把播放列表也生成了<br>
<br>
然后有了这么个玩意<br>
可以在程序中配置一下mp3下载目录和m3u列表目录<br>
仅供交流使用,网易别来找我麻烦哦<br>
<br>
<br>
2017/10/20 我喜欢的音乐已经超过1000首了,碰巧网易也取消了1000这个限制,因为用了旧的网页api所以就获取不到1000之后的音乐啦,待修复<br>

2017/11/10 解决掉文件名命名的问题,现在和网易云客户端的命名方式一样了,某些歌曲接口返回的歌曲名结尾居然带空格,好气喔<br>

2017/11/23 网易开始查ua了,已解决此问题

2017/12/21 再次改ua,接口死后复生

2018/01/07 修复在山灵播放器上播放列表找不到文件的bug<br>
           (这个明明是山灵的bug,在"\\"做路径时没有问题,用"/"做路径时,个别歌曲找不到路径)<br>
           再次编辑:<br>
               刚刚发现文件名过长也会找不到文件,例如:<br>
                   "Pinkie Pie,Rarity,Applejack,Applebloom,Rainbow Dash,Big Mac,Granny Smith,Twilight Sparkle,Fluttershy - We Got This Together.mp3"<br>
               <del>(山灵的程序猿你能给点力吗?)</del>现在m1的固件已经没人维护了(之前一直是海贝在维护),bug还没修呢

2018/01/24 难得一天闲了一下来加点功能,一定是工作量不饱和(x)<br>
           新增按歌单分类和开关选择是否下载歌词的功能(播放器不支持歌词的话下载了歌词文件夹很乱)

2018/01/26 最近真高产啊...填了一个之前的坑...增加双语歌词

2018/04/13 增加Android端下载歌曲转pc端下载文件名的规则<br>
           renameAndroid.py 用来给Android下的音乐重命名成pc端规则的的,就是这种操作😂<br>
           另外修正了关于文件名带空格的规则

2018/05/30 修复 Android file name 的问题

2018/09/14 花了十来分钟把Python2升级为Python3语法, 发现有些问题更容易解决了

2018/12/20 修好了下载的功能, 加了个头部防ban, 本来想加个进度条的然后失败了...<br>
           顺便改了下项目名字
           
2019/02/23 网易最近清了一堆歌手,整理了数据库,导致很多歌手名字变化以及歌手的顺序变化<br>
           名字变化一个个搜索了改吧,这里更新一下把那些歌手顺序翻转的改回来
           
2019/08/24 添加更多格式文件支持，部分代码重构，文件名不区分大小写，自动根据现有文件名写入播放列表，兼容更多filesystem，解决明明有这个文件却被覆盖下载的问题（主要在日语）


