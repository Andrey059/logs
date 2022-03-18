# Домашнее задание
1. В Vagrant разворачиваем 2 виртуальные машины web и log
2. на web настраиваем nginx
3. на log настраиваем центральный лог сервер на любой системе навыбор
- journald;
- rsyslog;
- elk.
4. Настраиваем аудит, следящий за изменением конфигов nginx.  
Все критичные логи с web должны собираться и локально и удаленно.  
Все логи с nginx должны уходить на удаленный сервер (локально
только критичные).  
Логи аудита должны также уходить на удаленную систему.  
Формат сдачи ДЗ - vagrant + ansible.  


# Для выполнения задания выбран ```rsyslog```

Для проверки выполнить :
 ```
vagrant up
curl 192.168.50.10
```
На curl получить положительный ответ, после  чего можно проверить логи на сервере
```
vagrant ssh otusLog
sudo -i
cat /var/log/rsyslog/otusweb/nginx_access.log | tail -50
```
В ответ получаем логи в консоли

![Image_alt](https://github.com/Andrey059/logs/blob/main/123.JPG)
