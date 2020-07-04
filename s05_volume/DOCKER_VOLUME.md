# Docker Volume

### Installation

Create nginx configuration file at var/www/conf/conf.d

```
events {
  worker_connections 768;
  # multi_accept on;
}

http{
    include /etc/nginx/conf.d/*.conf; #includes all files of file type.conf

    server {
        listen  80;
        server_name localhost;
        location / {
            root    /usr/share/nginx/html;
            index   index.html;
        }

        location /50x.html {
            root    /usr/share/nginx/html;
        }
    }
}
```

Create a simple html file at var/www/

```
<!DOCTYPE html>
<html>
    <body>
        Hello 30shines
    </body>
</html>
```

Run a nginx container which mounts both files above in ReadOnly mode
```sh
docker run --name my-custom-nginx -v $PWD/var/www:/usr/share/nginx/html:ro \
-v $PWD/var/www/conf/conf.d:/etc/nginx:ro -P -d nginx
```

Access to nginx webserver at localhost with the random port generated
```sh
curl localhost:{NGINX_PORT}
```
