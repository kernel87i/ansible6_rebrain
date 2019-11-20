## Задача

* Создать VPS с помощью Terraform
* Установить Nginx доменным именем по маске  <your_login>.devops.rebrain.srwx.net
* Создать роль Let's encrypt и автоматическое получение сертификата

## Предпосылки

* Установить terraform
* Установить Go 1.13 (to build the provider plugin)
* Собрать плагин terraform для vscale
* Установить ansible https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

## Развертывание

* Конфигурируем main.tf (создаем ресурс в Vscale)
* Выносим описание variables  в отдельный файл variables.tf
* Описываем в фале outputs.tf выводимые значения
* Переменные объявляем в файле terraform.tfvars (В файле объявляем токен, имя образа, Id дата-центра,secret_key, access_key для AWS, регион для AWS)
* В файле terraform.tfvars.sample описано назначение переменных
* Развертываем 3 roles для nginx

## Ansible Roles

# Первая роль для установки дефолтного Nginx и пробораса портов 80,443
# Вторая роль Установка letsencrypt + задача в cron  + генерация нового серта
# Третья роль Установка кастомного Nginx, настройка http, https, генерация сертификата


## Подключаемся по ssh.

* ssh root@82.202.236.164

## Проверяем подключение по 80 или 443 порту к виртуальным хостам.  

*  curl http://sbabanin2.devops.rebrain.srwx.net
*  curl https://sbabanin2.devops.rebrain.srwx.net


## Авторы

  - Sergey Babanin https://gitlab.rebrainme.com/babaninsergey

