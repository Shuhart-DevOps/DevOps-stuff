ARG BASE_IMAGE=registry.red-soft.ru/ubi8/ubi

FROM $BASE_IMAGE
RUN dnf install -y curl vim telnet ca-certificates wget nginx-1.28.0
RUN chown -R nginx:nginx /etc/nginx /var/log/nginx /usr/share/nginx
USER nginx
CMD nginx -g "daemon off;"