FROM nginx:1.19.9-alpine
WORKDIR /usr/share/nginx/app
RUN adduser -u 1000 -G www-data -D www-data && \
    touch /var/run/nginx.pid && \
    chown -R www-data:www-data /var/run/nginx.pid && \
    chown -R www-data:www-data /var/cache/nginx
COPY nginx.conf /etc/nginx/nginx.conf
COPY site.conf /etc/nginx/conf.d/default.conf
USER www-data
COPY build ./
EXPOSE 8089
CMD ["nginx","-g","daemon off;"]
