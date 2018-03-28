
# docker image for ngrok server

获取这个镜像:

```
docker pull jueying/ngrok-server

考虑到国内访问docker hub很慢，也可以通过下面命令构建镜像：
docker build -t jueying/ngrok-server https://github.com/jueying/docker-ngrok-server.git
```

使用镜像启动容器:

```
docker run -p http_port:http_port -p https_port:https:port -p tunnel_port:tunnel_port jueying/ngrok-server your_domain http_port https_port tunnel_port

例如:
docker run -p 80:80 -p 8082:8082 -p 443:443 jueying/ngrok-server google.com 80 8082 443
```

使用镜像在后台运行容器:

```
docker run -d -p http_port:http_port -p https_port:https:port -p tunnel_port:tunnel_port jueying/ngrok-server your_domain http_port https_port tunnel_port

例如:
docker run -d -p 80:80 -p 8082:8082 -p 443:443 jueying/ngrok-server google.com 80 8082 443
```

从容器内获取ngrok客户端:

```
docker cp container_id:/usr/local/ngrok/bin/ /tmp/
在/tmp/bin/中可以找到win64, win32和macos64对应的客户端
```
