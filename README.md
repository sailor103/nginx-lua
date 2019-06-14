# About

Nginx with Lua module support.

Only 2 modules is add:
 - [simpl/ngx_devel_kit](https://github.com/simpl/ngx_devel_kit)
 - [openresty/lua-nginx-module](https://github.com/openresty/lua-nginx-module)

# Version info

Nginx version: 1.16.0
Lua nginx module version: 1.10.15

# Usage

1. Create your own **Dockerfile** ...

    ```
    FROM danday74/nginx-lua
    COPY /your/nginx.conf /nginx/conf/nginx.conf
    ```

2. Add this location block to your **nginx.conf** file

    ```
    location /hellolua {
        content_by_lua '
            ngx.header["Content-Type"] = "text/plain";
            ngx.say("hello world");
        ';
    }
    ```
You can also just run it by `dokcer run` command, for example:

  ```
  docker run -d -p 80:80 -v /yourpath/nginx.conf:/etc/nginx/nginx.conf firesh/ngingx-lua
  ```

# Reference

[firesh/nginx-lua: Official NGINX Dockerfiles](https://github.com/firesh/nginx-lua)