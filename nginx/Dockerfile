FROM nginx:1.9
RUN apt-get update && apt-get install vim
RUN mkdir /opt/htdocs && mkdir /opt/log && mkdir /opt/log/nginx
RUN chown -R www-data.www-data /opt/htdocs /opt/log
VOLUME ["/opt"]
