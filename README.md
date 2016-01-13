# node-remote-service-layer
node.js 后端service请求代理层

## 单个config文件的内容及格式

```javascript

// /some/path/to/some-config.js

module.exports.name = 'serviceName';
module.exports.config = {
    //请求的协议,比如 http https ...
    protocol : 'http',
    //向后端机器发送请求的负载均衡策略
    balance : 'roundrobin',
    //单个请求的超时时间 ms 
    timeout : 1000,
    //单个请求的重试次数
    retry : 2,
    
    // ///////////////////// 下面是 HTTP 协议的配置项 /////////////
    
    method : 'GET',
    //URL 中query部分参数
    query : {
        k1 : 'value1',
        k2 : 'value2'
    },
    //请求的 path 部分
    path : '/some/request/path',
    //请求的HTTP头
    headers : {
        x-header-1 : 'hello'
    },
    //后端机器列表
    server : [
        {
            host : 'test.we.com',
            port : 80
        },
        {
            host : '192.168.1.5',
            port : 8080
        }
    ]
};

```

## 


## 其他方案

[阿里方案](http://ued.taobao.org/blog/2014/04/modelproxy/)

[百度node-ral](https://github.com/fex-team/node-ral)
