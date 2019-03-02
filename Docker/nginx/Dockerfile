FROM nginx
WORKDIR /app
ADD ./Docker/nginx/nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

ENTRYPOINT ["nginx","-g","daemon off;"]
