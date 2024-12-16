
# Сборка ARM LINUX

По мотивам статьи (GitHub) - [https://linux-for-arm.github.io/](https://linux-for-arm.github.io/)
Все необходимые материалы - [https://github.com/Linux-for-ARM](https://github.com/Linux-for-ARM) главный репозиторий проекта.


## 1 Введение

Образ Linux для ARM собирается на персональном компьютере с установленным linux Ubuntu.Этот linux будем называть Хост.

## Необходимое программное обеспечение


На вашей хост-системе должно быть установлено ПО из списка ниже с указанными минимальными версиями. Для большинства современных дистрибутивов Linux это не должно быть особой проблемой.
    
    bash-3.2 (/bin/sh должна быть ссылкой на bash)
    bc-1.07 (для компиляции Linux)
    binutils-2.13
    bison-2.7 (/usr/bin/yacc должен быть ссылкой на bison)
    coreutils-8.1
    diffutils-2.8.1
    findutils-4.2.31
    flex-2.6.4
    gawk-4.0.1 (/usr/bin/awk должен быть ссылкой на gawk)
    gcc-5.2 (влючающий компилятор языка С, C++)
    grep-2.5.1a
    gzip-1.3.12
    linux-4.19
    m4-1.4.10
    make-4.0
    ncurses-6.3 (для сборки BusyBox, Linux и U-Boot)
    patch-2.5.4
    perl-5.8.8
    python-3.4
    rsync-3.2.7 (для установки заголовков ядра на этапе сборки кросс-компилятора)
    sed-4.1.5
    python3-setuptools (для компиляции U-Boot)
    swig-4.0 (для компиляции U-Boot)
    tar-1.22
    texinfo-6.8 (для сборки binutils)
    u-boot-tools-2023.01 (для сборки ядра Linux и работы с загрузчиком U-Boot)
    xz-5.0
    wget-1.23 и md5sum (для скачивания исходного кода LFA)



## Установка недостающих пакетов

**bison**<br>
    >sudo apt install bison<br>
**flex**<br>
    >sudo apt install flex<br>
**gawk**<br>
    > sudo apt install gawk<br>
**swig**<br>
    > sudo apt install swig<br>
**texinfo**<br>
    >sudo apt install texinfo<br>
**u-boot-tools**<br>
    >sudo apt install u-boot-tools<br>
**setuptools**<br>
    >sudo apt-get install python-setuptools<br>

Пока не установил setuptools-66.1 (для компиляции U-Boot). Такого нет в ubuntu.
Похоже это пакет sudo apt-get install python-setuptools

## Создаем пользователя LFA

groupadd lfa
useradd -s /bin/bash -g lfa -m -k /dev/null lfa

    Значения новых параметров:

    groupadd lfa — создаёт новую группу lfa.

    -s /bin/bash — указывает /bin/bash оболочкой по умолчанию для пользователя lfa.

    -g lfa — добавляет пользователя lfa в группу lfa.

    -m — создаёт домашнюю директорию пользователя lfa (по умолчанию в /home/lfa).

    -k /dev/null — предотвращает копирование файлов из /etc/skel - каталога, в котором содержатся стандартные конфиги и иные файлы, которые обычно копируются в домашнюю директорию пользователя во время его создания.

  


Задайте для пользователя lfa новый пароль:
passwd lfa  

Теперь вам необходимо войти от имени lfa. Для этого выполните:

su - lfa

## Настройка окружения

##

## 

## Сборка ядра Linux

Неожиданно при сборке ядра Linux ARM на хостовой машине должен быть установлен пакет libssl-dev.
sudo aptitude install libssl-dev
Так же на хосте должны быть пакеты
need to install some required packages：
- make
- build-essential
- libncurses-dev 
- bison 
- flex 
- libssl-dev 
- libelf-dev

sudo apt-get install make build-essential libncurses-dev bison flex libssl-dev libelf-dev

## Сборка TF-A 

Официальный сайт проекта

https://www.trustedfirmware.org/projects/tf-a/

Проект Trusted Firmware-A предоставляет эталонную реализацию безопасного программного обеспечения для процессоров класса ARMv7-A и ARMv8-A.

- Документация
https://trustedfirmware-a.readthedocs.io/en/latest/getting_started/initial-build.html

- Исходники


- 
