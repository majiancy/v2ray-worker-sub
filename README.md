##用于创建订阅链接的CF Worker代码

在Dist文件夹中下载JS脚本，并复制到你的服务里（CF Workers里）
您可以通过以下链接查看帮助视频：

### Youtube

- [第一部分，创建一个拥有干净IP的worker](https://youtu.be/oxYoILJ9Hgk)
- [第二部分，添加Mussoorie的子链接](https://youtu.be/Pq5FWdG31Yc)

### 电报群

[Telegram 频道上的视频和说明](https://t.me/vahidgeek/72)


创建工作程序后应在子应用程序客户端部分中输入的路径示例如下。 在这种情况下，不需要干净的 IP，将从干净域列表中选择一个随机域，并在某些运营商上以可接受的质量进行响应
https://my-worker.my-id.workers.dev/sub


您可以输入运营商的三字母代码，以便将相关运营商的干净 IP 添加到您的配置中。 例如第一个同伴（伊朗以外地区略过此功能）：
https://my-worker.my-id.workers.dev/sub/mci

三字母代码列表如下：

三字母代码    运营商
---         | --- 
afn         | افرانت       
apt         | عصر تلکام    
ast         | آسیاتک       
dbn         | دیده‌بان     
dtk         | داتک    
fnv         | فن‌آوا        
hwb         | های‌وب        
mbt         | مبین‌نت       
mci         | همراه اول    
mkh         | مخابرات      
mtn         | ایرانسل      
prs         | پارس‌آنلاین    
psm         | پیشگامان    
rsp         | رسپینا       
rtl         | رایتل        
sht         | شاتل         
ztl         | زیتل
---         | ---


或者添加以下链接并加上优选IP（1.2.3.4 是个IP示例）
https://my-worker.my-id.workers.dev/sub/1.2.3.4

也可以用 逗号 分割多个优选IP
https://my-worker.my-id.workers.dev/sub/1.2.3.4,9.8.7.6

您也可以使用优选域名
https://my-worker.my-id.workers.dev/sub/mci.ircf.space

或者一些未被污染的子域名
https://my-worker.my-id.workers.dev/sub/mci.ircf.space,my.domain.me

您可以使用 max 变量指定配置数量
https://my-worker.my-id.workers.dev/sub?max=200

您还可以使用数字 0 或 1，或 yes/no 来指定原始配置（不与工作线程组合）是否包含在输出中
https://my-worker.my-id.workers.dev/sub/1.2.3.4?max=200&original=yes
https://my-worker.my-id.workers.dev/sub?max=200&original=0

如有必要，您可以使用合并参数指定删除、组合配置
https://my-worker.my-id.workers.dev/sub?max=200&original=yes&merge=no

您还可以配置 fp 和 alpn值
https://my-worker.my-id.workers.dev/sub?max=200&fp=chrome&alpn=h2,http/1.1

如有必要，您可以指定为主配置列出哪些类型的配置

代码 | fp
---  | ---
 1   | chrome
 2   | edge
 3   | ios
 4   | firefox
 5   | ios
 6   | android
 7   | safari
 8   | randomized
 9   | random
---  | ---

可接受的 alpn 列表：
代码 | alpn
---  | ---
1    | h2,http/1.1
2    | h2
3    | http/1.1
---  | ---

如有必要，您可以指定为主配置列出哪些类型的配置
https://my-worker.my-id.workers.dev/sub?max=200&type=vmess,ss,ssr,vless

如有必要，您可以限制提供商列表
https://my-worker.my-id.workers.dev/sub?provider=mahdibland,vpei

代码 | fp
---  | ---
 1   | mahdibland
 2   | vpei
 3   | mfuu
 4   | peasoft
 5   | ermaozi
 6   | aiboboxx
 7   | pawdroid
 8   | autoproxy
 9   | freefq
---  | ---
