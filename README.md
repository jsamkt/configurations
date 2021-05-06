# Конфигурации

###### Создание бесплатного сертификата

`sudo certbot certonly --standalone`

это создаст файлы в **/etc/letsencrypt/live/<domain>**
  
Потом делаем из этих фалов keystore.p12 для Java

`openssl pkcs12 -export -in fullchain.pem -inkey privkey.pem -out keystore.p12 -name tomcat -CAfile chain.pem -caname root`

И Пихаем ее в java приложение
