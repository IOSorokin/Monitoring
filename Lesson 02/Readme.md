# Задание 1

   ## 1. Используя директорию help внутри этого домашнего задания, запустите связку prometheus-grafana.
   ## 2. Зайдите в веб-интерфейс grafana, используя авторизационные данные, указанные в манифесте docker-compose.
   ## 3. Подключите поднятый вами prometheus, как источник данных.
   ## 4. Решение домашнего задания — скриншот веб-интерфейса grafana со списком подключенных Datasource.
  ![изображение](https://github.com/IOSorokin/Monitoring/assets/148979909/281ab92c-7c68-4a3b-acbf-8efeed14cae6)



# Задание 2

   ## 1. Изучите самостоятельно ресурсы:

    PromQL tutorial for beginners and humans.
    Understanding Machine CPU usage.
    Introduction to PromQL, the Prometheus query language.

  ## 2. Создайте Dashboard и в ней создайте Panels:

    утилизация CPU для nodeexporter (в процентах, 100-idle);
```
   100 - (avg by (instance) (rate(node_cpu_seconds_total{job="nodeexporter",mode="idle"}[2m])) * 100)
```
    
    CPULA 1/5/15;
```
100 - (avg(rate(node_cpu_seconds_total{mode="idle"}[1m])) * 100) 100 - (avg(rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100) 100 - 
(avg(rate(node_cpu_seconds_total{mode="idle"}[15m])) * 100)
```
    количество свободной оперативной памяти;
```
node_memory_MemAvailable_bytes
```
    количество места на файловой системе.
```
((node_filesystem_size_bytes{mountpoint="/"} - node_filesystem_avail_bytes{mountpoint="/"}) - node_filesystem_size_bytes{mountpoint="/"}) * -1
```
Скриншот
![изображение](https://github.com/IOSorokin/Monitoring/assets/148979909/6ba2d233-a4c3-4104-9036-0ab738d3bb24)


# Задание 3

    Создайте для каждой Dashboard подходящее правило alert — можно обратиться к первой лекции в блоке «Мониторинг».
    В качестве решения задания приведите скриншот вашей итоговой Dashboard.
   ![изображение](https://github.com/IOSorokin/Monitoring/assets/148979909/b9e7c68d-c95b-43c3-b6bc-002b5ad78ada)


# Задание 4

    Сохраните ваш Dashboard.Для этого перейдите в настройки Dashboard, выберите в боковом меню «JSON MODEL». Далее скопируйте отображаемое json-содержимое в отдельный файл и сохраните его.
    В качестве решения задания приведите листинг этого файла.

