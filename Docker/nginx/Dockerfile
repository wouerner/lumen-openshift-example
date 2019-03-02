FROM nginx
WORKDIR /app
RUN ls -la
ADD ./nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

ENTRYPOINT ["nginx","-g","daemon off;"]
