# Dev tricks

## Change localhost to specific domain
1. Set up a nginx proxy

     - Install nginx
          ```
          sudo apt-get install nginx
          ```

     - Edit configuration in ```/etc/nginx/nginx.conf```:
          ```
          http {
               ...
               server {
                    listen 80;
                    server_name chozoi.com dev.chozoi.com;

                    location / {
                         proxy_set_header   X-Forwarded-For $remote_addr;
                         proxy_set_header   Host $http_host;
                         proxy_pass         "http://127.0.0.1:3000";
                    }
               }
               ...
          }
          ```


2. Point the domain to ```127.0.0.1``` in ```/etc/hosts```
     ```
     127.0.0.1	chozoi.com dev.chozoi.com
     ...
     ```

3. Reboot
