docker run --name my-custom-nginx -v $PWD/var/www:/usr/share/nginx/html:ro  -v $PWD/var/www/conf/conf.d:/etc/nginx:ro -P -d nginx
