**使用VLESS协议：** 
TLS-XRAY+NGINX

**工作原理：** 
本机发送TLS加密的数据包到google $\Longrightarrow$ XRAY使用VLESS协议对数据包封装，并用TLS对数据包加密，伪装成HTTPS流量 $\Longrightarrow$ 数据包穿过墙到达你的服务器 $\Longrightarrow$ 服务器端的XRAY对数据进行处理 $\Longrightarrow$ 如果是VLESS协议的数据包，则由XRAY处理出站；如果不是VLESS协议的数据包，比如正常的HTTPS流量，则回落到NGINX监听的端口，展示NGINX搭建的网页

**配置文件：** 
本地XRAY配置：[config_client.json](config_client.json)
服务器XRAY配置：[config_server.json](config_server.json)
服务器NGINX配置：[nginx.conf](nginx.conf)

**参考：** 
[XTLS搭建](https://www.youtube.com/watch?v=7GHh91AYAmM&t=372s)