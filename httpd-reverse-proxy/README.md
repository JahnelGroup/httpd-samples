# Apache httpd Reverse Proxy

This sample demonstrates a simple Apache httpd reverse proxy serving an nginx backend. 

## ProxyRequest Hacking

By defaul the apache configuration here is setup to only seemingly only proxy requests to one host called `nginx`, but in realty it could be exploited if misconfigured. If you want to simulate a hack then set `ProxyRequests On` in [httpd.conf](./httpd/httpd.conf). Then Use the following command to send a request to the seemingly unexposed `nginx2` backend.

```bash
printf "GET http://nginx2 HTTP/1.1\r\nUser-Agent: nc/0.0.1\r\nHost: 127.0.0.1\r\nAccept: */*\r\n\r\n" | nc 127.0.0.1 80
```