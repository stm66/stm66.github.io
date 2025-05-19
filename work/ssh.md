# разрешить root вход на сервер
/etc/ssh/sshd_config
раскомментировать
PermitRootLogin yes
перезапусить sshd

# смотреть лог в файле
/var/log/messages
