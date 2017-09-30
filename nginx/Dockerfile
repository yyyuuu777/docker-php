FROM nginx:1.9
ADD ./config/* /etc/nginx/conf.d/
RUN mkdir /opt/htdocs && mkdir /opt/log && mkdir /opt/log/nginx
RUN chown -R www-data.www-data /opt/htdocs /opt/log
VOLUME ["/opt"]
