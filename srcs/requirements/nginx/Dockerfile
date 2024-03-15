FROM debian:bullseye

RUN apt update && apt upgrade -y
RUN apt install nginx openssl -y

COPY ./config/nginx.conf /etc/nginx/nginx.conf

RUN mkdir -p /etc/nginx/ssl

RUN openssl req -x509 -nodes -out /etc/nginx/ssl/certificate.crt -keyout /etc/nginx/ssl/certificate.key -subj "/C=FR/ST=IDF/L=Paris/O=42/OU=42/CN=lboulatr.42.fr/UID=lboulatr"

CMD ["nginx"]
