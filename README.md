# JsApiScan
扫描js文件中敏感api的burp插件，支持自动fuzz，过滤http状态码和域名
## 功能
### 设置
可设置是否开启自动扫描，过滤请求方法、相应码、MIME响应，配置"Root Directory"
![](https://github.com/sulab999/JsApiScan/blob/main/pic/1.png )
### 自动fuzz
自动Fuzz针对于JS中发现的API接口，其接口路径将直接拼接在Host根目录后，可能会因为某些站点存在前置路径导致Fuzz出现大量404，如果需要手动Fuzz，可在后续的Sensitive面板中复制出接口列表再Intruder中手动Fuzz
![](https://github.com/sulab999/JsApiScan/blob/main/pic/2.png )
### 信息面板
面板中展示JS中发现的所有敏感信息，列表中将反应不同信息类别的发现个数，可对信息类型进行Filter，并且可通过Copy按钮一键复制文本框内所有内容。  
1、Repeat功能，该功能主要是可以对"Sensitive Info"表中选中的行的Api地址进行重新Fuzz，该功能的设计初衷是为了防止AutoRepeater Fuzz的根路径并不是站点的真正根目录

2、在配置页面配置"Root Directory"，该配置是专为Repeat使用的，AutoRepeater不会使用该配置，该配置是用来更正网站根路径，可以为多个路径，例如admin,admin/manager，用逗号隔开，当然可以配置为空

3、选中表格中的某行后，点击repeat按钮，程序会将"Root Directory"配置中的路径拼接在所有API路径前，点击repeat按钮后状态将变为“working”，在fuzz结束前该按钮不能再次点击
![](https://github.com/sulab999/JsApiScan/blob/main/pic/3.png )
# 参考项目  
https://github.com/L4ml3da/Tinker/tree/master
