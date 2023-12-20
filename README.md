# Кондаков Павел  

### Задание 1
- Составьте команду rsync, которая позволяет создавать зеркальную копию домашней директории пользователя в директорию `/tmp/backup`
- Необходимо исключить из синхронизации все директории, начинающиеся с точки (скрытые)
- Необходимо сделать так, чтобы rsync подсчитывал хэш-суммы для всех файлов, даже если их время модификации и размер идентичны в источнике и приемнике.
- На проверку направить скриншот с командой и результатом ее выполнения
```
rsync -av --delete --exclude '.*' /home/chistov/ /tmp/backup
```  
![alt text](https://github.com/PavelKondakov22/backup1/blob/main/z1.png)  
![alt text](https://github.com/PavelKondakov22/backup1/blob/main/z1.1.png)  
### Задание 2
- Написать скрипт и настроить задачу на регулярное резервное копирование домашней директории пользователя с помощью rsync и cron.
- Резервная копия должна быть полностью зеркальной
- Резервная копия должна создаваться раз в день, в системном логе должна появляться запись об успешном или неуспешном выполнении операции
- Резервная копия размещается локально, в директории `/tmp/backup`
- На проверку направить файл crontab и скриншот с результатом работы утилиты.  
```
#!/bin/sh
rsync -av --delete --exclude '.*' /home/chistov/ /tmp/backup >> /var/log/crontab.log  
```
![alt text](https://github.com/PavelKondakov22/backup1/blob/main/z2.png)  

https://github.com/PavelKondakov22/backup1/blob/main/pavel  

