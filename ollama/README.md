# Open WebUI


## 什么是 Ollama ？

[Ollama](https://ollama.com/library) 是一个简明易用的本地大模型运行框架。能在本地启动并运行 Llama 2、Mistral、Gemma 及其他大语言模型。


### 启动服务

```sh
docker-compose up -d
```

访问 http://localhost:3000/ 注册一个账号


### Error response from daemon: Ports are not available: exposing port TCP 0.0.0.0:11434 -> 0.0.0.0:0: listen tcp 0.0.0.0:11434: bind: An attempt was made to access a socket in a way forbidden by its access permissions.


查看已占用的端口
```sh
netstat -ano
```

以管理打开终端

```sh
net stop winnat
net start winnat
```

问题解决