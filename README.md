  # Домашнее задание к занятию "5.2 Применение принципов IaaC в работе с виртуальными машинами"

 ##  Задача №1

### Ответ:
* Процесс непрерывной интеграции позволяет совершать меньше ошибок в коде и ускорить выпуск продукта при условии высокого уровня инженерной культуры в команде. Непрерывное тестирования небольшими объемами позволяет легко исправлять эти ошибки и откатываться на более раннее состояние в случае критический ситуации. Паттерны IaaC позволяют избежать дрейфа конфигураций при работе в команде, у отдела разработки и тестирования всегда будут одинаковые среды и условия работы с продуктом. Увеличение скорости выпуска продукта напрямую зависит от увеличения скорости каждого этапа разработки ПО, что также обеспечивают основные принципы данной методологии.
* Основополагающий принцип IaaC состоит в идемпотентности. Данный подход позволяет создавать код выполнение которого всегда приводит к одинаковому предсказуемому результату.

 ## Задача №2

### Ответ:
* Ansible позволяет использовать SSH инфраструктуру без установки дополнительного окружения и не требует большого количества ресурсов на это. 
* Зависит от проекта и задачи, но на мой взгляд push метод позволяет проще контролировать конфигурацию для целевых хостов, однако в случае большого количества таковых может возникнуть вопрос к трафику при отправке таких конфигураций. Для метода Pull требуется реализация специальных агентов для сбора конфигурации, что является тоже является своеобразной точной отказа и не все фреймворки поддерживают работу с таким методом. На сегодняшний день судя по информации из лекции для небольшого количества целевых хостов будет эффективен метод Push, а для крупных проектов Pull. Иногда возможно использование гибридного метода, который позволяет использовать сильные стороны и Push и Pull в зависимости от решаемой задачи.

 ## Задача №3 

### Ответ:
1. Virtualbox:  
  `Графический интерфейс VirtualBox`
  `Версия 6.1.26 r145957 (Qt5.6.2)`  
2. Vagrant:   
  `PS D:\vagrant> vagrant -v`
  `Vagrant 2.2.18`  
3. Ansible:   
  `$ ansible --version`
  `ansible 2.8.2`
  `config file = /etc/ansible/ansible.cfg`
  `configured module search path = ['/home/KOT/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']`  
  `ansible python module location = /usr/lib/python3.7/site-packages/ansible`
  `executable location = /usr/bin/ansible`
  `python version = 3.7.12 (default, Nov 23 2021, 18:58:07) [GCC 11.2.0]`  

## Задача №4

### Ответ:

