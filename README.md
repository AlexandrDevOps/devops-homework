# Домашнее задание к занятию "3.8. Компьютерные сети, лекция 3"
#
1. Команды и их вывод внесены в документ по приложенной ссылке, скриншоты не делал, поскольку информация много скопировал    
из консоли. Внешний IP адрес моей машины узналь через сайт 2IP.ru выполнял не из дома поэтому внешний IP отличается от того    
который назывался в предыдущем ДЗ.      
#
2. Для создания Dummy интерфейса использовал следующие команды:    
  echo "dummy" >> /etc/modules  включение модуля dummy   
  echo "options dummy numdummies=2" >> /etc/modprobe.d/dummy.conf создание файла с настройками с указанием количества dummy интерфейсов  
  nano /etc/network/interfaces добавление ip адресов для созданных dummy интерфейсов:  
  auto dummy0  
    iface dummy0 inet static  
      address 192.168.1.17/24  
      pre-up ip link add dummy0 type dummy  
      post-down ip link del dummy0  
  auto dummy1  
    iface dummy1 inet static  
    address 172.16.2.1/27  
    pre-up ip link add dummy1 type dummy  
    post-down ip link del dummy1  
    
   после настроект файлов конфигураций обязательно необходимо перезапустить сетевые сервисы командой:  
   $ sudo service networking restart  
   тогда после запроса таблицы маршрутизации и интерфейсов система выведет необходиму информацию о добавленных dummy.  
   Вывод результатов находится в файле документа по приложенной ссылке.
#
3.  Команда $ sudo ss -tlpn покажет прослушиваемые TCP порты и приложения которые их используют с выводом IP адресов в числовом виде.  
    Согласно моей системе у меня прослушивается 22, 111 и 53 TCP порт, 111 использует демон rpcbind, systemd pid 556 и pid 1 соответственно.  
    22 порт выделен для ssh и его использует sshd демон с pid 692, 53 порт использует systemd-resolve c pid 559.   
    Возможно посмотреть данные порты еще с помощью утилит nmap и zenmap.  
#
4.  Аналогично заданию 3 можно использовать утилиту ss только указать флаг -u, что означает отобразить udp сокеты.
    $ sudo ss -ulpn Согласно рисунку приложенному в документе моя система прослушивает 53, 68 и 111 UDP сокет используемые демонами  
    systemd-resolve, systemd-network, rpcbind соответственно.
#
5.  Схема сети L3 построенная в Diagrams.net представлена в документе по ссылке.


