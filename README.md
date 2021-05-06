# Конфигурации

##### Создание бесплатного сертификата

1. Создаем файлы в **/etc/letsencrypt/live/domain_name** \
`sudo certbot certonly --standalone`

1. Создаем из этих фалов **keystore.p12** для Java \
`openssl pkcs12 -export -in fullchain.pem -inkey privkey.pem -out keystore.p12 -name tomcat -CAfile chain.pem -caname root` 

1. Копируем **keystore.p12** в приложение
