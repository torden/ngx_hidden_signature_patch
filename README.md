# Just! a Hide Server Signature of Nginx Web Server

Depending on the environment of production, We may need to hide server signature.

As We knew, Nginx can be turned on and off in the "Server" response header field and in the Embedded Error pages

However it's not enough.

## What is this?

This is a simple patches which hide server signature of nginx web server.

## List of Tested Version


|*Nginx Version*|*Patch File 1*|*Patch File 2*|
|---|---|---|
|1.0.x|[nginx-1.0-ngx_http_header_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.0-ngx_http_header_filter_module.c.patch)|[nginx-1.0.15-1.11.9-ngx_http_special_response.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.0.15-1.11.9-ngx_http_special_response.c.patch)|
|1.2.x|[nginx-1.2-ngx_http_header_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.2-ngx_http_header_filter_module.c.patch)|[nginx-1.0.15-1.11.9-ngx_http_special_response.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.0.15-1.11.9-ngx_http_special_response.c.patch)|
|1.4.x|[nginx-1.4-ngx_http_header_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.4-ngx_http_header_filter_module.c.patch)|[nginx-1.0.15-1.11.9-ngx_http_special_response.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.0.15-1.11.9-ngx_http_special_response.c.patch)|
|1.6.x|[nginx-1.6-ngx_http_header_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.6-ngx_http_header_filter_module.c.patch)|[nginx-1.0.15-1.11.9-ngx_http_special_response.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.0.15-1.11.9-ngx_http_special_response.c.patch)|
|1.8.x|[nginx-1.8-ngx_http_header_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.8-ngx_http_header_filter_module.c.patch)|[nginx-1.0.15-1.11.9-ngx_http_special_response.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.0.15-1.11.9-ngx_http_special_response.c.patch)|
|1.10.x|[nginx-1.10-ngx_http_header_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.10-ngx_http_header_filter_module.c.patch)|[nginx-1.0.15-1.11.9-ngx_http_special_response.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.0.15-1.11.9-ngx_http_special_response.c.patch)|
|1.11.x|[nginx-1.11-ngx_http_header_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.11-ngx_http_header_filter_module.c.patch)|[nginx-1.0.15-1.11.9-ngx_http_special_response.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.0.15-1.11.9-ngx_http_special_response.c.patch)|
|1.12.x|[nginx-1.12.0-ngx_http_header_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.12.0-ngx_http_header_filter_module.c.patch)|[nginx-1.12.0-ngx_http_special_response.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.12.0-ngx_http_special_response.c.patch)|
|1.13.x|[nginx-1.13.0-ngx_http_header_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.13.0-ngx_http_header_filter_module.c.patch)|[nginx-1.13.0-ngx_http_special_response.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.13.0-ngx_http_special_response.c.patch)|
|1.14.x ~ 1.17.x|[nginx-1.14.x-1.17.x-ngx_http_header_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.14.x-1.17.x-ngx_http_header_filter_module.c.patch)|[nginx-1.14.x-1.17.x-ngx_http_special_response.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.14.x-1.17.x-ngx_http_special_response.c.patch)|


## Patch

```bash
wget http://nginx.org/download/nginx-1.10.3.tar.gz
tar xvzf nginx-1.10.3.tar.gz
cd nginx-1.10.3
patch -p0 < ../ngx_hidden_signature_patch/nginx-1.10-ngx_http_header_filter_module.c.patch
# patching file src/http/ngx_http_header_filter_module.c
patch -p0 < ../ngx_hidden_signature_patch/nginx-1.0.15-1.11.9-ngx_http_special_response.c.patch
# patching file src/http/ngx_http_special_response.c

./configure
make
make install
```

### Generally Response of Nginx

You can looking for server signature.

```bash
HTTP/1.1 404 Not Found
*Server: nginx/1.10.3*
Date: Mon, 06 Feb 2017 05:45:59 GMT
Content-Type: text/html
Content-Length: 169
Connection: keep-alive

<html>
<head><title>404 Not Found</title></head>
<body bgcolor="white">
<center><h1>404 Not Found</h1></center>
*<hr><center>nginx/1.10.3</center>*
</body>
</html>
```


### Response of Nginx after adding a "server_tokens off;" to nginx.conf

You can looking for server signature.

```bash
HTTP/1.1 404 Not Found
*Server: nginx*
Date: Mon, 06 Feb 2017 06:03:59 GMT
Content-Type: text/html
Content-Length: 162
Connection: keep-alive

<html>
<head><title>404 Not Found</title></head>
<body bgcolor="white">
<center><h1>404 Not Found</h1></center>
*<hr><center>nginx</center>*
</body>
</html>
```


## Response Header of Nginx After Patched

Make Sure the removed server signature 

```bash
HTTP/1.1 404 Not Found
Date: Mon, 06 Feb 2017 05:45:25 GMT
Content-Type: text/html
Content-Length: 134
Connection: keep-alive

<html>
<head><title>404 Not Found</title></head>
<body bgcolor="white">
<center><h1>404 Not Found</h1></center>
</body>
</html>
```

---

plz feel free
