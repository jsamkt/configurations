# Конфигурации

#### Создание бесплатного сертификата

1. Создаем файлы в **/etc/letsencrypt/live/domain_name** \
`sudo certbot certonly --standalone`

1. Создаем из этих фалов **keystore.p12** для Java \
`openssl pkcs12 -export -in fullchain.pem -inkey privkey.pem -out keystore.p12 -name tomcat -CAfile chain.pem -caname root` 

1. Копируем **keystore.p12** в приложение

#### Двойной порт-ворвардинг

1. Из **А** в **Б** прокидываем порт на SSH порт **22** \
`ssh -R 9999:localhost:22 USER_IN_B@SERVICE_B`

1. Из **Б** в **А** прокидываем порт на ресурс подключаясь к прокинутому SSH порту \
`ssh -R 7777:SERVICE_C_ADDRESS:8888 USER_IN_A@localhost -p 9999`
