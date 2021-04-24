server {
    listen  80;
    server_name ttshop.wang;
    # 告诉浏览器有效期内只准用 https 访问
    add_header Strict-Transport-Security max-age=15768000;
    # 永久重定向到 https 站点
    return 301 https://$server_name$request_uri;

    #charset koi8-r;
    # access_log  /var/log/nginx/host.access.log  main;
}

server {
    listen 443;
    server_name xxx;
    # 日志文件
    access_log  /home/Log/host.access.log  main;

    ssl on;
    # 证书路径
    ssl_certificate xxx.crt;
    # 私钥路径
    ssl_certificate_key xxx.key;
    # 安全链接可选的加密协议
    ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
    # 可选的加密算法,顺序很重要,越靠前的优先级越高.
    ssl_ciphers ECDHE-RSA-AES128-GCM-SHA256:HIGH:!aNULL:!MD5:!RC4:!DHE;
   # 在 SSLv3 或 TLSv1 握手过程一般使用客户端的首选算法,如果启用下面的配置,则会使用服务器端的首选算法.
    ssl_prefer_server_ciphers on;
    # 储存SSL会话的缓存类型和大小
    ssl_session_cache shared:SSL:10m;
    # 缓存有效期
    ssl_session_timeout 60m;

    # 这里配置vue项目的路径
    location / {
        root /home/html;
        index   index.html index.htm;
    }

}


#搭建kafka消息中间件需要进行相关的文件操作

搭建kafka集群

搭建zookeeper集群但是不需要搭建Hadoop集群，部署JDK
















