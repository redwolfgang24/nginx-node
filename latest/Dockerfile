FROM ubuntu:latest

RUN apt-get update \
  && apt-get install -y curl git bzip2

RUN echo "deb [arch=amd64] http://nginx.org/packages/mainline/ubuntu/ bionic nginx" >> /etc/apt/sources.list.d/nginx.list
RUN echo "deb-src http://nginx.org/packages/mainline/ubuntu/ bionic nginx" >> /etc/apt/sources.list.d/nginx.list

RUN wget http://nginx.org/keys/nginx_signing.key | apt-key add -
RUN apt-get -y update
RUN apt-get remove nginx nginx-common nginx-full nginx-core

RUN apt-get install -y nginx

RUN apt-get install -y nodejs

RUN npm install -g n
RUN n 8.6.0

CMD ["nginx", "-g", "daemon off;"]
