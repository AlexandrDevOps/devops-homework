# Домашнее задание к занятию "3.1. Работа в терминале, лекция 1"
пункт 5: Оперативная память - 1024Mb, 2 ядра процессора, интегрированная графическая карта 4мб видеопамяти, жесткий диск SATA-0 64 ГБ свободного пространства, гигабитная сетевая карта. Данные ресурсы являются ресурсами по умолчанию.
#
пункт 6:  В файле настроек Vagrantfile необходимо добавить следующий код:
#
config.vm.provider "virtualbox" do |vb|
  vb.memory = 1024
  vb.cpus = 2
end
#
пункт 8: HISTFILESIZE количество строк, содержащихся в файле истории. Если значение равно 0, файл истории усекается до нулевого.
manual page bash(1) line 912.
ignoreboth — не записывать команду, которая начинается с пробела, либо команду, которая дублирует предыдущую.
#
пункт 9: фигурные скобки применимы в сценариях где используются составные команды или указывается диаппазон.
manual page bash(1) line 406      раздел "Shell Function Definitions"
#
пункт 10: 100000 файлов создать возможно, а вот 300000 нет. 
Данный диаппазон ограничен и система сообщит следующее -bash: /usr/bin/touch: Argument list too long.
#
