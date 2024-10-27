### 1. Установка Elasticsearch + kibana

Так как у меня аритектура arm64 и macOS, скачивала с официального сайта elastic Kibana 8.1.1 и Elasticsearch 8.1.1


Проделывание инструкций из 01.sh, адаптированных под ноут:

![alt text](01_sh.png "Folders")

Запуск Kibana и проделывание конфигурации на http://0.0.0.0:5601/:

![alt text](kibana_start.png "Folders")

Так как у меня до этого в config/elasticsearch.yml не было xpack, он был сгенерирован позже, то вручную поменяла
`xpack.security.enabled: false`

![alt text](handed_xpack.png "Folders")

Не работал дефолтный пароль `changeme`, так что я его ресетнула, затем перезапустила Эластик

![alt text](reset_password.png "Folders")

Поменяла в конфигурационном файле config/kibana.yml; `https://` на `http://`, затем перезапустила Кибану.

В файле 02.yaml поменяла `FLUENT_ELASTICSEARCH_HOST` на свой INTERNAL ADDRESS и пароль от эластика `FLUENT_ELASTICSEARCH_PASSWORD` на новый

![alt text](change_02_yaml.png "Folders")



### 2. Запуск fluentd

Запуск minikube, настройка алиасов и применение манифеста 02.yaml

![alt text](minikube_start.png "Folders")

fluentd начал читать логи:

![alt text](logs.png "Folders")

Создала DataView с именем logstash-*, страница Discover:

![alt text](discover.png "Folders")

Dashboard:

![alt text](dashboard.png "Folders")