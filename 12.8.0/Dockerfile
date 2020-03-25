FROM nginx:latest

RUN apt-get update \
  && apt-get install -y curl nodejs

CMD ["nginx", "-g", "daemon off;"]
