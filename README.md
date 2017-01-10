# Ansible для сетевых инженеров

###Автор: Наташа Самойленко

<br>

>#### Обратите внимание, что сейчас курс в процессе написания, поэтому не все разделы и домашние задания дописаны.
>#### Курс будет завершен в феврале 2017

<br>

#Ansible

Ansible - это система управления конфигурациями. Ansible позволяет автоматизировать и упростить настройку, обслуживание и развертывание серверов, служб, ПО и др.

На данный момент существует несколько [систем управления конфигурациями](http://xgu.ru/wiki/%D0%A1%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D0%B0_%D1%83%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F_%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B3%D1%83%D1%80%D0%B0%D1%86%D0%B8%D0%B5%D0%B9).

Однако, для работы с сетевым оборудованием, чаще всего используется Ansible.
Связано это с тем, что Ansible не требует установки агента на управляемые хосты.
Особенно актуально это для устройств, которые позволяют работать с ними только через CLI.

Кроме того, Ansible активно развивается в сторону поддержки сетевого оборудования и постоянно появляются новые возможности и модули для работы с сетевым оборудованием.

> Некоторое сетевое оборудование поддерживает другие системы управления конфигурациями (позволяет установить агента).

Одно из важных преимуществ Ansible заключается в том, что он очень прост в использовании. И его довольно легко начать использовать.

Прежде чем мы начнем разбираться подробнее с Ansible, перечислим несколько задач, которые Ansible решит, в контексте использования его для работы с сетевым оборудованием:
* подключение по SSH к устройствам
 * паралелльное подключение к устройствам по SSH (можно указывать ко скольки устройствам подключаться одновременно)
* отправка команд на устройства
* удобный синтаксис описания устройств:
 * можно разбивать устройства на группы и затем отправлять какие-то команды на всю группу
* поддержка шаблонов конфигураций с Jinja2

Это всего лишь несколько возможностей Ansible, которые относятся к сетевому оборудованию. Они перечислены тут, для того чтобы показать, что эти задачи Ansible сразу снимает и можно не использовать для этого какие-то скрипты, так как с Ansible это можно сделать намного удобней.

Прежде чем мы начнем разбираться с Ansible подробнее, нам надо установить его.

## Установка Ansible

Ansible нужно устанавливать только на той машине, с которой мы будем управлять устройствами.

Требования к управляющему хосту:
* поддержка Python 2.7 (или 2.6)
* Windows не может быть управляющим хостом

Ansible довольно часто обновляется, поэтому, будет лучше, если вы установите его в виртуальном окружении.

Установить Ansible можно [по-разному](http://docs.ansible.com/ansible/intro_installation.html#). Мы для этого будем использовать pip:
```
$ pip install ansible
```
