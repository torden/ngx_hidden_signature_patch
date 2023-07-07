
# Just! a Hide Server Signature of Nginx Web Server

Depending on the environment of production, We may need to hide server signature.

As We knew, Nginx can be turned on and off in the "Server" response header field and in the Embedded Error pages

However it's not enough.

[![Build Status](https://github.com/torden/ngx_hidden_signature_patch/actions/workflows/ngx_hidden_signature_patch.yml/badge.svg)](https://github.com/torden/ngx_hidden_signature_patch/actions)

## What is this?

This is a simple patches which hide server signature of nginx web server.

## List of Tested Version


### For HTTP, HTTPS

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
|1.14.x ~ 1.23.x|[nginx-1.14.x-1.17.x-ngx_http_header_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.14.x-1.17.x-ngx_http_header_filter_module.c.patch)|[nginx-1.14.x-1.17.x-ngx_http_special_response.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.14.x-1.17.x-ngx_http_special_response.c.patch)|
|1.22.x ~ 1.24.x|[nginx-1.22.x-1.23.x-ngx_http_header_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.22.x-1.23.x-ngx_http_header_filter_module.c.patch)|[nginx-1.14.x-1.23.x-ngx_http_special_response.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.14.x-1.23.x-ngx_http_special_response.c.patch)|

### For HTTP/2

|*Nginx Version(http v2 module)*|*Patch File*|
|---|---|
|1.9.x ~ |[nginx-1.9.5-ngx_http_v2_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.9.5-ngx_http_v2_filter_module.c.patch)|
|1.10.x ~ |[nginx-1.10.3-ngx_http_v2_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.10.3-ngx_http_v2_filter_module.c.patch)|
|1.12.x ~ |[nginx-1.12.2-ngx_http_v2_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.12.2-ngx_http_v2_filter_module.c.patch)|
|1.14.x ~ 1.23.x|[nginx-1.14.x-1.17.x-ngx_http_v2_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.14.x-1.17.x-ngx_http_v2_filter_module.c.patch) OR [nginx-1.14.x-1.23.x-ngx_http_v2_filter_module.c.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.14.x-1.23.x-ngx_http_v2_filter_module.c.patch)|
|1.25.x ~ |[nginx-1.25.x-ngx_http_v2_filter_module.patch](https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.25.x-ngx_http_v2_filter_module.patch)|

## Patch

```bash
curl -s -O https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.22.x-1.23.x-ngx_http_header_filter_module.c.patch
curl -s -O https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.14.x-1.23.x-ngx_http_special_response.c.patch
curl -s -O https://github.com/torden/ngx_hidden_signature_patch/raw/master/nginx-1.14.x-1.23.x-ngx_http_v2_filter_module.c.patch
curl -s -O http://nginx.org/download/nginx-1.23.1.tar.gz

tar xvzf nginx-1.23.1.tar.gz
cd nginx-1.23.1

patch -p0 < ../ngx_hidden_signature_patch/nginx-1.22.x-1.23.x-ngx_http_header_filter_module.c.patch
patch -p0 < ../ngx_hidden_signature_patch/nginx-1.14.x-1.23.x-ngx_http_special_response.c.patch
patch -p0 < ../ngx_hidden_signature_patch/nginx-1.14.x-1.23.x-ngx_http_v2_filter_module.c.patch

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

HTTP/2 200
*server: nginx/1.10.3*
date: Mon, 06 Feb 2017 05:45:25 GMT
content-type: text/html
content-length: 612
last-modified: Thu, 30 Jan 2020 05:03:50 GMT
etag: "5e3263b6-264"
accept-ranges: bytes

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

HTTP/2 200
*server: nginx*
date: Mon, 06 Feb 2017 05:45:25 GMT
content-type: text/html
content-length: 612
last-modified: Thu, 30 Jan 2020 05:03:50 GMT
etag: "5e3263b6-264"
accept-ranges: bytes

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

HTTP/2 200
date: Mon, 06 Feb 2017 05:45:25 GMT
content-type: text/html
content-length: 612
last-modified: Thu, 30 Jan 2020 05:03:50 GMT
etag: "5e3263b6-264"
accept-ranges: bytes

<html>
<head><title>404 Not Found</title></head>
<body bgcolor="white">
<center><h1>404 Not Found</h1></center>
</body>
</html>
```

---

plz feel free
