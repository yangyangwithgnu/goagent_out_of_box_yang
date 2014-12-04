#全民翻墙：小白关爱版 goagent v3.2.3
yangyang.gnu@gmail.com  
http://yangyangwithgnu.github.io/  
2014-12-4 13:06:35   


##公告
----------------
* **捐赠：支付宝 yangyang.gnu@gmail.com 。支付宝链接 https://shenghuo.alipay.com/send/payment/fill.htm?optEmail=yangyang.gnu@gmail.com ，支付宝二维码 $_$**
<div align="center">
<img src="https://raw.githubusercontent.com/yangyangwithgnu/yangyangwithgnu.github.io/master/pics/donate_qr.png" alt=""/><br>
</div>


##版本
----------------
更新至最新 v3.2.3，需客户端重新导入证书，除常规功能提升和 bug 修复外，两点重要更新：0）GAE 不再支持 pagespeed，删除 proxy.ini 中的 pagespeed 选项；1）PAC 存在漏洞，假定某运行 goagent 的客户端 IP 为 123.2.2.11，那么可以通过 http://123.2.2.11:8086/%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f/ 访问该客户端上任意文件，禁用 PAC 以封堵该漏洞。


##缘由
----------------

你知道，天朝在互联网上树了一堵墙 GFW，作为一个热爱折腾的新时代入党积极分子，墙外一切的一切无时无刻不在吸引着我，所以，翻墙是必须嘀。当前的开源翻墙工具很多，全局翻墙的 PPTP-VPN 和 openVPN、socks 翻墙的 SSH 和 shadowsocks、HTTP 翻墙的 goagent，对于那些原本不支持代理功能的软件可以用 proxychains 透明代理后具备代理功能，一旦具备翻墙能力后，你甚至可以用 tor 指定任意国家或地区作为出口 IP。

虽然，小部分民众都可以参照各类教程自己配置可用的代理，但是，仍然有大部分小白欠缺计算机基础操作能力，所以，我为动手能力相对较弱的朋友准备了一份开箱即用的 goagent。只要时间允许，我会尽可能同步至最新版的 goagent，让大家轻松愉悦的游离网络。

如果，你有意愿自己配置一套 goagent，又或者，对其他各类代理工具感兴趣，可以参考《美丽新世界：linux 下的惬意生活》中“3.2 搭梯翻墙”章节（https://github.com/yangyangwithgnu/the_new_world_linux#3.2 ）。


##注意
----------------

**惜用流量**。简单来说，这份预配置的 goagent 是有流量限制的，所有使用它的用户每天共享 25G 流量，所以，你，只可以用它访问网页，切勿用它下载任何资源。具体而言，你知道，goagent 是 GAE 的上层产物，为更好地使用 goagent，所以 GAE 的某些属性我们应当有所了解。GAE 分收费版和免费版，我们使用的免费版，自然有些限制：一个 google 帐号对应一个 GAE 使用权，一个 GAE 使用权可以创建最多 25 个 APP；流量方面，每个 APP 每天 1GB、每分钟 56MB；URL 请求方面，每个 APP 每天 657000 次、每分钟 3000 次。一旦的某个 APP 超过以上配额，该 APP 后续请求均将失败，直到当日太平洋时间 0 点（北京时间 15:00） GAE 自动重置后方可恢复。


##使用
----------------

####linux/osX
运行 goagent 代理程序
```
python goagent_out_of_box_yang/proxy.py
```

设置浏览器代理地址。firefox 可通过 edit - preferences - advanced - network - connection - settings 设置代理服务器地址为 127.0.0.1，端口为 8087，重启 firefox 生效。

浏览器中导入证书。firefox 可通过 edit - preferences - advanced - encryption - view certificates - authorities - import，选择证书 goagent_out_of_box_yang
/CA.crt，在确认对话框中勾选 websites、email users、software developers 等三类信任，重启 firefox 生效。

####windows
1. 你得确保你是**管理员身份登录系统**。进入 computer - mangage - system tools - local users and groups - users，双击 administrator，**取消** general 选项卡下的 account is disabled。重启系统；
2. 赋予 goagent.exe 管理员权限。具体请右键 goagent.exe，选中 properties - compatibility - privilege level - run this program as an admin；
3. 双击 goagent.exe 运行；
4. 设置浏览器代理地址。firefox 可通过 edit - preferences - advanced - network - connection - settings 设置代理服务器地址为 127.0.0.1，端口为 8087，重启 firefox 即可生效。IE 可通过 tools - internet options - connections - LAN settings，勾选 use a proxy server for your LAN，add 填入 127.0.0.1，port 填入 8087，重启 IE 即可；
5. 浏览器中导入证书。firefox 可通过 edit - preferences - advanced - encryption - view certificates - authorities - import，选择证书 goagent_out_of_box_yang/CA.crt，在确认对话框中勾选 websites、email users、software developers 等三类信任，重启 firefox 生效。IE 可通过 tools - internet options - content - certificates 进行证书 goagent_out_of_box_yang/CA.crt 的选择。

可访问 http://www.ip38.com/ 查看“来自”信息确认代理是否生效，通常情况应显示“美国谷歌公司云数据中心”。
