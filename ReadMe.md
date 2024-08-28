#  Стенд с Vagrant c Rsyslog


Цель домашнего задания
Научится проектировать централизованный сбор логов. 
Рассмотреть особенности разных платформ для сбора логов.






### 1.Настроим стенд Vagrant с двумя виртуальными машинами: web и log.

[Vagrantfile](Vagrantfile)

![текст](screenshots/vagrant_status.png)  




### 2.Пишем playbook

[playbook](playbook.yml)




__Устанавливаем на web и log необходимые пакеты__
![текст](screenshots/install_packages.png)  





__Проверим, что nginx работает корректно:__  
![текст](screenshots/nginx_status_playbook.png)
![текст](screenshots/nginx_status.png)





__Конфигурируем /etc/nginx/nginx.conf / проверяем конфигурацию / если все ок то прегружаем сервис nginx__
![текст](screenshots/nginx_playbook.png)
![текст](screenshots/nginx_status2.png)





__Конфигурируем /etc/rsyslog.conf__
![текст](screenshots/rsyslog_status_playbook.png)
![текст](screenshots/rsyslog_status.png)





__Если ошибок не допущено, то у нас будут видны открытые порты TCP,UDP 514:__
![текст](screenshots/status_port_514.png)  





__Проверяем что логи отправляются корректно__
![текст](screenshots/cat_var_log_success.png)
![текст](screenshots/cat_var_log_error.png)