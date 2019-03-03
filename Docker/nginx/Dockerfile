#FROM nginx
#WORKDIR /app
#USER root
#ADD ./Docker/nginx/nginx.conf /etc/nginx/nginx.conf

#EXPOSE 80


FROM nginx:mainline-alpine

WORKDIR /app
COPY . /var/www/
# support running as arbitrary user which belogs to the root group
RUN chmod g+rwx /var/cache/nginx /var/run /var/log/nginx
RUN chgrp -R root /var/cache/nginx

# users are not allowed to listen on priviliged ports
RUN sed -i.bak 's/listen\(.*\)80;/listen 8081;/' /etc/nginx/conf.d/default.conf
EXPOSE 8081

# comment user directive as master process is run as user in OpenShift anyhow
RUN sed -i.bak 's/^user/#user/' /etc/nginx/nginx.conf

RUN addgroup nginx root
USER nginx





ENTRYPOINT ["nginx","-g","daemon off;"]
