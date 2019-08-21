FROM nginx:latest

RUN apt-get update \
  && apt-get install -y curl git bzip2 libfontconfig1-dev xz-utils gnupg2

RUN apt-get install nodejs

RUN npm install -g n
RUN n 8.6.0

CMD ["nginx", "-g", "daemon off;"]
