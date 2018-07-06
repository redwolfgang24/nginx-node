# NGINX and Node
Creates a docker image with NGINX and Node installed in it. Useful to serve up a single page application built with node.

Supported tags and respective `Dockerfile` links

- `7.4.0` `latest` [(7.4.0/Dockerfile)](https://github.com/redwolfgang24/nginx-node/blob/master/7.4.0/Dockerfile)

## Usage

Make a `Dockerfile` something like this:

```bash
FROM sinet/nginx-node:latest

# Install and build the application
COPY . /usr/src/app
WORKDIR /usr/src/app
RUN npm install && npm run gulp -- build

COPY default.conf /etc/nginx/conf.d/

CMD ["nginx", "-g", "daemon off;"]
```

The `default.conf` would look something like this.

```
server {
    listen       80;
    server_name  localhost;

    location / {
        root   /usr/src/app/build;
        index  index.html index.htm;
    }
}
```
