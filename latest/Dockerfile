FROM nginx:latest

RUN apt-get update \
  && apt-get install -y curl git bzip2 libfontconfig1-dev xz-utils gnupg2

RUN curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
RUN sudo apt-get install nodejs

RUN npm install -g n
RUN n 8.6.0

CMD ["nginx", "-g", "daemon off;"]
