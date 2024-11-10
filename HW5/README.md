## 1. Первое задание

### 1.1. Разворачивание Prometheus через docker-compose

![alt text](task1/prometheus.png "Task1")

### 1.2. Запросы основных типов метрик:

   1. Counter  
       ![alt text](task1/counter.png "Task1")
   2. Gauge   
          ![alt text](task1/gauge.png "Task1")
   3. Histogram  
       ![alt text](task1/histogram.png "Task1")
   4. Summary  
       ![alt text](task1/summary.png "Task1")


## 2. Второе задание

### Изменения в монифестах:
1. config.yaml
    ![alt text](task2_pics/config.png "Task2")
2. service.yaml
    ![alt text](task2_pics/service.png "Task2")
3. ingress.yaml
    ![alt text](task2_pics/ingress.png "Task2")
4. deployment.yaml
    ![alt text](task2_pics/deployment.png "Task2")

Отдельно манифесты в папке task2_files

### Dockerfile и prometheus_client
Файлы в папке task2_files

В prometheus_client 2 метрики oncall которые называются http_requests_total, tsdb_head_chunks и каждые 5 сек меняют значения

### Конфигурация prometheus

Файл prometheus.yml в папке task2_files, из дефолтного варианта только поменяла  
` - targets: ["oncall.metrics.local:8000"]`

### Запрос к метрикам из Prometheus UI

![alt text](task2_pics/notifier_metric_1.png "Task2")

![alt text](task2_pics/notifier_metric_2.png "Task2")







