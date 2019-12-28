## Motivating Nginx
- A web server refers to some software running on a physical server that handles client re
quests from the world wide web
- A reverse proxy is a type of proxy server that retrieves resources on behalf of a client from one or more servers
- An HTTP cache occurs when the browser stores local copies of web resources for faster retrieval the next time the resource is required
- A load balancer refers to some software running on a physical server that acts as a reverse proxy and distributes network or application traffic across a number of separate servers
- There is a lot of overlap in these software, so Nginx tries to combine and organize all of these functionalities into one centralized service

## General Description
- Nginx is an open-source web server, reverse proxy, HTTP cache, and load balancer
- Suppose we have some python web application, then we would typically use nginx to do the following:
	1. Receive a request from some client's front end application
	2. Send that request to the appropriate back end application
	3. Receive a reponse from the back end application once it has finished running
	4. Send that response back to the front end application
- A major advantage of Nginx is the simplicity and customization it offers with its configuration files

## Benefits of Nginx
- Offers low memory usage
- Offers high concurrency
- Supports asynchronous events
	- Rather than creating new processes for each web request, Nginx uses an asynchronous event-driven approach where requests are handled in a single thread
	- Many web servers assign each request to its own process, where every process lives on its own individual thread
	- Nginx assigns each request to its own event, where every event lives on one single thread
- Reverse proxying with caching
	- Nginx stores local copies of web resources for faster retrieval the next time the resource is required
- Load balancing
- Limiting rate of traffic

## Example of Nginx Configuration
```
user       www www;  ## Default: nobody
worker_processes  5;  ## Default: 1
error_log  logs/error.log;
pid        logs/nginx.pid;
worker_rlimit_nofile 8192;

events {
  worker_connections  4096;  ## Default: 1024
}

http {
  include    conf/mime.types;
  include    /etc/nginx/proxy.conf;
  include    /etc/nginx/fastcgi.conf;
  index    index.html index.htm index.php;

  default_type application/octet-stream;
  log_format   main '$remote_addr - $remote_user [$time_local]  $status '
    '"$request" $body_bytes_sent "$http_referer" '
    '"$http_user_agent" "$http_x_forwarded_for"';
  access_log   logs/access.log  main;
  sendfile     on;
  tcp_nopush   on;
  server_names_hash_bucket_size 128; # this seems to be required for some vhosts

  server { # php/fastcgi
    listen       80;
    server_name  domain1.com www.domain1.com;
    access_log   logs/domain1.access.log  main;
    root         html;

    location ~ \.php$ {
      fastcgi_pass   127.0.0.1:1025;
    }
  }

  server { # simple reverse-proxy
    listen       80;
    server_name  domain2.com www.domain2.com;
    access_log   logs/domain2.access.log  main;

    # serve static files
    location ~ ^/(images|javascript|js|css|flash|media|static)/  {
      root    /var/www/virtual/big.server.com/htdocs;
      expires 30d;
    }

    # pass requests for dynamic content to rails/turbogears/zope, et al
    location / {
      proxy_pass      http://127.0.0.1:8080;
    }
  }

  upstream big_server_com {
    server 127.0.0.3:8000 weight=5;
    server 127.0.0.3:8001 weight=5;
    server 192.168.0.1:8000;
    server 192.168.0.1:8001;
  }

  server { # simple load balancing
    listen          80;
    server_name     big.server.com;
    access_log      logs/big.server.access.log main;

    location / {
      proxy_pass      http://big_server_com;
    }
  }
}
```

## References
- https://kinsta.com/knowledgebase/what-is-nginx/
- https://www.digitalocean.com/community/tutorials/how-to-set-up-uwsgi-and-nginx-to-serve-python-apps-on-ubuntu-14-04
- https://stackoverflow.com/questions/5844955/whats-the-difference-between-event-driven-and-asynchronous-between-epoll-and-a
- https://www.nginx.com/resources/wiki/start/topics/examples/full/
- https://www.nginx.com/blog/rate-limiting-nginx/
