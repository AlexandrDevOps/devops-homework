# Домашнее задание к занятию "3.7. Компьютерные сети, лекция 2"
#
1.  Windows: команда в консоли: ipconfig /all или netsh interface show interface (кратко и что подключено)   
    C помощью GUI в поиске: ncpa.cpl открое сразу все сетевые подключения.    
    Linux:  команда в консоли: ifconfig -a (в старых версиях); ip a (в последних версиях) или ip l; ip link show покажет все сетевые интерфейсы;  
    возможно посмотреть по указанному пути ls /sys/class/net;  
#
2.  Протокол LLDP для обмена информацией между соседними устройствами, в Linux есть специальный пакет lldpd, который можно       
    установить и запустить для обмена информацией, аналогично нужно включить на соседнем устройстве данный протокол.  
    Команды: systemctl enable lldpd && systemctl start lldpd; lldpctl. Полное описание команд при работе с lldpd возможно получить командой man lldpd.  
#
3.  Virtual Local Area Network (VLAN) технология позволяющая организовать поверх одной физической сети несколько логических.   
    Пример конфигурации файла /etc/network/interfaces:
    auto vlan17
        iface vlan17 inet static
        address 172.16.5.55
        netmask 255.255.255.128
        vlan_raw_device eth0
    auto eth0.17
        iface eth0.17 inet static
        address 172.16.5.55
        netmask 255.255.255.128
        vlan_raw_device eth0
    поднят vlan c ID=17 для интерфейса eth0.      
#
4.  В Linux агрегацию интерфейсов принято называть термином Bonding. Основные типы обьединения интерфейсов:   
    0 (balance-rr) — round-robin распределение пакетов между интерфейсами. Обеспечивает отказоустойчивость и повышение пропускной способности.  
    1 (active-backup) — в каждый момент времени работает только один интерфейс, в случае его выхода из строя, mac-адрес назначается второму интерфейсу и трафик             переключается на него.  
    2 (balance-xor) — обеспечивает балансировку между интерфейсами на основании MAC-адресов отправителя и получателя.  
    3 (broadcast) — отправляет пакеты через все интерфейсы одновременно, обеспечивает отказоустойчивость.  
    4 (802.3ad) — обеспечивает агрегацию на основании протокола 802.3ad.  
    5 (balance-tlb) — в этом режиме входящий трафик приходит только на один «активный» интерфейс, исходящий же распределяется по всем интерфейсам.  
    6 (balance-alb) — балансирует исходящий трафик как tlb, а так же входящий IPv4 трафик используя ARP.  
    
    Пример конфигурации:  
   Для начала нужно отредактировать файл /etc/network/interfaces:  
    auto bond0  
    iface bond0 inet static  
    address 172.16.5.60  
    netmask 255.255.255.0      
    gateway 172.16.5.1  
    dns-nameservers 77.86.21.3 8.8.8.8  
    dns-search domain.local  
        slaves eth0 eth1  
        bond_mode 0  
        bond-miimon 100  
        bond_downdelay 200  
        bound_updelay 200  
   Для активации потребуется перезапустить службу: $ sudo systemctl restart networking.service
#
5.  В подсети с маской /29 всего 6 адресов для Host. Из подсети с маской /24 можно получить 32 подсети с маской /29
    Пример подсетей /29: 10.10.10.0/29 10.10.10.0 - адрес сети; 10.10.10.1 - 10.10.10.6 пулл адресов в подсети; 
    10.10.10.7 - Broadcast адрес в подсети; 10.10.10.8/29 - адрес следующей сети; 10.10.10.9 - 10.10.10.14 - пулл адресов;
    10.10.10.15 - Broadcast адрес в подсети; 10.10.10.16/29 - адрес следующей сети; 
#
6.  Допустимо взять адреса из следующего диапазона 100.64.0.0-100.127.255.255. Например: 100.64.0.1/26 (255.255.255.192) с учетом требований задания.
#
7.  Команда: ip neighbour show; ip n выведет ARP таблицу; Команда: ip neighbour flush очистит кэш полностью; Для удаления одного адреса или таблицы
    определенного интерфейста используют: ip neighbour delete dev eth0 10.0.2.2 или ip neigh flush dev eth0.

