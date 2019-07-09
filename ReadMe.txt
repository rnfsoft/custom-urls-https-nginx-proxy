References:
    https://medium.com/@francoisromain/set-a-local-web-development-environment-with-custom-urls-and-https-3fbe91d2eaf0

    https://blog.ssdnodes.com/blog/host-multiple-websites-docker-nginx/

    https://devcenter.heroku.com/articles/ssl-certificate-self

    https://github.com/jwilder/nginx-proxy/issues/667#issuecomment-269768389
    
sudo nano /etc/hosts
    127.0.0.1        my-app.local
    127.0.0.1        my-other-app.local

    Ctrl + x

create certificate in certs folder

nginx-proxy:
    docker-compose up -d --build

my-app.local:
    docker-compose.yml
        add VIRTUAL_HOST: my-app.local

    docker-compose up -d --build
        

my-other-app.local:
    docker-compose.yml
        add VIRTUAL_HOST: my-other-app.local
        container_name: wordpress_db2
        container_name: wordpress2

    docker-compose up -d --build


docker-compose down -v