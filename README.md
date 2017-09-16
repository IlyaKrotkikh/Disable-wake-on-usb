# Скрипт выключает пробуждение системы по сигналу USB

## Требования к системе
* Материнская плата: GIGABYTE GA-Z77X-D3H (Rev. 1.0);
* ОС: Ubuntu подобная операционная система.
Работоспособность скрипта проверена на Linux Mint 18.x

## Установка
### 1. Копируем скрипт в директорию скриптов автозапуска:
```sh
$ cp disable_wake /etc/init.d/
$ chmod 755 /etc/init.d/disable_wake
```
### 2. Устанавливаем ссылки в необходимые уровни инициализации
```sh
$ update-rc.d -n disable_wake enable
```
## Удаление
### 1. Убираем ссылки
```sh
$ update-rc.d disable_wake disable
```
### 2. Удаляем скрипт
```sh
$ rm /etc/init.d/disable_wake
```

## Использование
Управлять возможностью пробуждения по USB сигналу можно с помощю стандартной утилиту управления сервисами в системе.
Выполнив команду `start` активируется блокировка пробуждения.
```sh
$ service disable_wake start
```
Команда `stop` эмулирует остановку сервиса, тем самым активируя пробуждение системы по USB.
```sh
$ service disable_wake stop
```
Команда `status` выдает текущее состояние работы сервиса.
```sh
$ service disable_wake status
```
 _TODO_: _исправить вывод статуса_
 
 ##### Автор
ivashca99@gmail.com
##### Источники
* [linuks.it_disable-wake-on-usb] - Запретить вывод из спящего режима по USB
* [nix.zeya.org_work-wich-init] - Работа с init-скриптами в Debian Squeeze
* [help.ubuntu.ru_Creating-your-own-autorun-script] - Создание своего скрипта автозапуска при загрузке компьютера

[//]: # (Source links list)
[linuks.it_disable-wake-on-usb]: <http://www.linuks.lt/blog/ru/index.php/2012-11-03-linux--keyboard>
[nix.zeya.org_work-wich-init]: <http://nix.zeya.org/forum/index.php?topic=64.0>
[help.ubuntu.ru_Creating-your-own-autorun-script]: <http://help.ubuntu.ru/wiki/%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5_%D1%81%D0%BA%D1%80%D0%B8%D0%BF%D1%82%D0%B0_%D0%B0%D0%B2%D1%82%D0%BE%D0%B7%D0%B0%D0%BF%D1%83%D1%81%D0%BA%D0%B0>
