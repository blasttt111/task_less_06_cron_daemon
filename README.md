CRON

1. Открыл `crontab` и создал скрипт
  - (`sudo crontab -e`)
<img width="669" height="247" alt="image" src="https://github.com/user-attachments/assets/322fb197-4d80-410a-8e0d-5a3fe0d62a47" />

2. Перед запуском скрипта cron, проверил вес директории где хранится кэш
  - (`sudo du -sh /var/cache/apt/archives/`)

<img width="730" height="230" alt="image" src="https://github.com/user-attachments/assets/3db09a27-0a98-4f8a-8a85-e852990e2837" />

3. Через минуту он был очищен скриптом

<img width="573" height="66" alt="image" src="https://github.com/user-attachments/assets/b8cc0e68-bd09-4cbf-b4a7-3b60d8f1781d" />

4. Поправил скрипт и выставил его работу на 1 раз в месяц в 16 часов
<img width="740" height="302" alt="image" src="https://github.com/user-attachments/assets/d156cb2f-5556-4047-afcd-d57efb59ec5d" />


DAEMON
1. Установил `node`

<img width="411" height="71" alt="image" src="https://github.com/user-attachments/assets/2e98507f-03d7-44b3-81f7-f9d6f7eaff43" />

2. Создал файл `app.js` в директории `/home/admin/Desktop/hw_6`

<img width="921" height="646" alt="image" src="https://github.com/user-attachments/assets/00a3e8a0-8d01-465f-8443-35324ec32b9a" />

3. Создал файл `/etc/systemd/system/nodeapp.service`

<img width="614" height="468" alt="image" src="https://github.com/user-attachments/assets/46924114-d268-4a31-b5e7-8534b9f833af" />

4. Создал нужные файлы `error.log` и `info.log`, в директории `/var/log/nodeapp`. Выдал доступ для `syslog`

<img width="759" height="227" alt="image" src="https://github.com/user-attachments/assets/b55eaf66-c048-42da-aa2c-392dbbd501aa" />

5. Перезапустил сервис, проверил статус

<img width="856" height="347" alt="image" src="https://github.com/user-attachments/assets/008d1f16-cc79-4a93-a027-e72f516c836a" />

<img width="1092" height="361" alt="image" src="https://github.com/user-attachments/assets/f5b383f3-fc87-4e53-a284-764d7d7ff85e" />

6. Курлыкнул
  - (`curl 127.0.0.1:3000`)

  <img width="514" height="64" alt="image" src="https://github.com/user-attachments/assets/58898811-69fa-417e-90f2-4612670f51f5" />

7. Убил сервис и проверил автозапуск

<img width="1033" height="388" alt="image" src="https://github.com/user-attachments/assets/6d8e2160-202e-4195-a164-a4a3679bcbcc" />

8. Поправил юнит файл чтобы сервис использовал `syslog`, добавил `logger`

<img width="707" height="433" alt="image" src="https://github.com/user-attachments/assets/649adaf8-1678-423c-bb85-4be784f2a7f8" />


9. Создал файл `/etc/rsyslog.d/100-nodeapp.conf` для перехвата логов через `syslog`

<img width="855" height="217" alt="image" src="https://github.com/user-attachments/assets/c1c24e97-6dbd-48dc-a96d-177df0bfe4c6" />

10. Настроил `logrotate` в /etc/logrotate.d/nodeapp

<img width="679" height="315" alt="image" src="https://github.com/user-attachments/assets/de1c2134-2493-44c7-85bb-ecbd72838afe" />

11. Проверил что логи выводятся в файл. Сообщение example отправил сам при помощи `logger --tag nodeapp "example"`

<img width="1004" height="349" alt="image" src="https://github.com/user-attachments/assets/6a853684-a2b6-417b-9d08-8724275c5e9f" />

