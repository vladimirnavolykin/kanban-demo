FROM nginx:latest

RUN apt install openssl -y

# так можно самому сгенерировать сертификаты в контейнере, или модно использовать сертификаты через volumes
# RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/certs/self.key \
#     -out /etc/ssl/certs/self.crt \
#     -subj "/C=RU/ST=Ulyanovsk/L=Home/O=mentaltrap Code/OU=Org/CN=localhost"
