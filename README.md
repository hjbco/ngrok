# ngrok - Introspected tunnels to localhost ([homepage](https://ngrok.com))
### "I want to securely expose a web server to the internet and capture all traffic for detailed inspection and replay"
![](https://ngrok.com/static/img/overview.png)

## 对原版的改进

1. 增加授权(auth_token)的检查
2. 强制子域名绑定
3. 将统计数据存储
4. 支持转发到监听端口的请求(例如监听9080,然后nginx将80端口的请求转发过来)

均依赖本地的redis实例

## TODO

1. HTTP API
2. CNAME 支持

## Redis数据定义

```
hset ngrok $auth_token $subdomain

zset ngrok:report $now $report
```