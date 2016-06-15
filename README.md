Nginxに下記のプラグインを追加しています。
https://github.com/cubicdaiya/ngx_dynamic_upstream

Buildには下記のツールを使用しています。
https://github.com/cubicdaiya/nginx-build

## Version

```
$ nginx -V
nginx version: nginx/1.10.0
built by gcc 4.9.2 (Debian 4.9.2-10)
built with OpenSSL 1.0.1t  3 May 2016
TLS SNI support enabled
configure arguments:
--add-module=../njs/nginx
--add-module=../ngx_dynamic_upstream
--with-cc-opt='-g -O2 -fstack-protector-strong -Wformat -Werror=format-security -Wp,-D_FORTIFY_SOURCE=2'
--modules-path=/usr/lib/nginx/modules
--user=nginx
--http-uwsgi-temp-path=/var/cache/nginx/uwsgi_temp
--http-scgi-temp-path=/var/cache/nginx/scgi_temp
--http-log-path=/var/log/nginx/access.log
--http-client-body-temp-path=/var/cache/nginx/client_temp
--http-fastcgi-temp-path=/var/cache/nginx/fastcgi_temp
--with-ld-opt='-Wl,-z,relro -Wl,--as-needed'
--prefix=/etc/nginx
--conf-path=/etc/nginx/nginx.conf
--error-log-path=/var/log/nginx/error.log
--pid-path=/var/run/nginx.pid
--group=nginx
--http-proxy-temp-path=/var/cache/nginx/proxy_temp
--sbin-path=/usr/sbin/nginx
--lock-path=/var/run/nginx.lock
--with-stream_ssl_module
--with-stream
--with-http_dav_module
--with-http_stub_status_module
--with-http_mp4_module
--with-mail
--with-http_flv_module
--with-mail_ssl_module
--with-http_xslt_module=dynamic
--with-http_realip_module
--with-http_auth_request_module
--with-http_slice_module
--with-threads
--with-http_ssl_module
--with-http_v2_module
--with-http_sub_module
--with-http_geoip_module=dynamic
--with-http_perl_module=dynamic
--with-http_secure_link_module
--with-http_addition_module
--with-http_gunzip_module
--with-http_random_index_module
--with-http_image_filter_module=dynamic
--with-ipv6
--with-http_gzip_static_module
--with-file-aio
```

## Usage

`/etc/nginx/nginx.conf`をセットしてビルドしてください。

例: `docker run`

```
docker run -d -v /path/to/nginx.conf:/etc/nginx/nginx.conf:ro togana/docker-ngx-dynamic-upstream
```

例: `Dockerfile`

```
FROM togana/docker-ngx-dynamic-upstream
COPY /path/to/nginx.conf /etc/nginx/nginx.conf
```
