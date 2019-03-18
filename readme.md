# Assets-for-Ebook
Ebook 书城项目的 Nginx 静态资源


### nginx.conf 配置
user  lvshijie owner; # nginx 访问本机时赋予 lvshijie 的角色，可访问静态资源

server {
        listen 4810;
        server_name resource;
        root /Users/lvshijie/Downloads/resource; # 静态资源路径
        autoindex on; # 查看文件列表
        location / {
                add_header Access-Control-Allow-Origin *; # 允许跨于访问
        }
        add_header Cache-Control "no-cache, must-revalidate"; # 不走缓存，每次校验
    }
