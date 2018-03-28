
# docker image for ngrok server

To get this image:

```
docker pull jueying/ngrok-server
```

To run the server:

```
docker run -p http_port:http_port -p https_port:https:port -p tunnel_port:tunnel_port jueying/ngrok-server your_domain http_port https_port tunnel_port

for example:
docker run -p 80:80 -p 8082:8082 -p 443:443 jueying/ngrok-server google.com 80 8082 443
```

To run the server as a daemon:

```
docker run -d -p http_port:http_port -p https_port:https:port -p tunnel_port:tunnel_port jueying/ngrok-server your_domain http_port https_port tunnel_port

for example:
docker run -d -p 80:80 -p 8082:8082 -p 443:443 jueying/ngrok-server google.com 80 8082 443
```

To get the ngrok-client from container:

```
docker cp container_id:/usr/local/ngrok/bin /tmp
```

On the image, ngrok is cloned at `/usr/local/ngrok/`.
