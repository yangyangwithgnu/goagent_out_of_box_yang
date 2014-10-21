#开箱即用的 goagent 
yangyang.gnu@gmail.com  
http://yangyangwithgnu.github.io/  
2014-10-21 21:29:33   


##公告
----------------

**捐赠：如果觉得 hardseed 有用，可以考虑捐赠点碎银，支付宝 yangyang.gnu@gmail.com ，不好意思，$_$**


##缘由
----------------

你知道，天朝在互联网上树了一堵墙 GFW，作为一个热爱折腾的新时代入党积极分子，墙外一切的一切无时无刻不在吸引着我，所以，翻墙是必须。就当前的技术实现来看，翻墙手段很多，开源的代理工具就有 PPTP-VPN、openVPN、SSH、shadowsocks、goagent 等。

虽然，很多人都可以参照各类教程自己配置可用的代理，但是，仍然有很多很多人欠缺计算机基础操作能力，所以，我为动手能力相对较弱的朋友准备了一份开箱即用的 goagent。只要时间允许，我会尽可能同步至最新版的 goagent，让大家轻松愉悦的游离网络。

如果，你有意愿自己配置一套 goagent，又或者，对其他各类代理工具感兴趣，可以参考《美丽新世界：linux 下的惬意生活》中“3.2 搭梯翻墙”章节（https://github.com/yangyangwithgnu/the_new_world_linux#3.2 ）。

**当前版本 goagent v3.2.1**


##注意
----------------

**惜用流量**。简单来说，这份预配置的 goagent 是有流量限制的，所有使用它的用户每天共享 25G 流量，所以，你，只可以用它访问网页，切勿用它下载任何资源。具体而言，你知道，goagent 是 GAE 的上层产物，为更好地使用 goagent，所以 GAE 的某些属性我们应当有所了解。GAE 分收费版和免费版，我们使用的免费版，自然有些限制：一个 google 帐号对应一个 GAE 使用权，一个 GAE 使用权可以创建最多 25 个 APP；流量方面，每个 APP 每天 1GB、每分钟 56MB；URL 请求方面，每个 APP 每天 657000 次、每分钟 3000 次。一旦的某个 APP 超过以上配额，该 APP 后续请求均将失败，直到当日太平洋时间 0 点（北京时间 15:00） GAE 自动重置后方可恢复。


##使用
----------------

####linux/osX
1. 运行 goagent 代理程序
```
cd goagent_out_of_box_yang/
python proxy.py
```
2. 设置浏览器代理地址。firefox 可通过 edit - preferences - advanced - network - connection - settings 设置代理服务器地址为 127.0.0.1，端口为 8087，重启 firefox 即可生效。

####windows
1. 首先，你得确保你是**管理员身份登录系统**。进入 computer - mangage - system tools - local users and groups - users，双击 administrator，**取消** general 选项卡下的 account is disabled。重启系统。  
2. 然后，赋予 goagent.exe 管理员权限。具体请右键 goagent.exe，选中 properties - compatibility - privilege level - run this program as an admin。  
3. 接着，双击 goagent.exe 运行。
4. 最后，设置浏览器代理地址。firefox 可通过 edit - preferences - advanced - network - connection - settings 设置代理服务器地址为 127.0.0.1，端口为 8087，重启 firefox 即可生效。IE 可通过 tools - internet options - connections - LAN settings，勾选 use a proxy server for your LAN，add 填入 127.0.0.1，port 填入 8087，重启 IE 即可。
