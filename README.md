# Домашнее задание к занятию «2.4. Инструменты Git»
1. Полный хэш коммита aefead2207ef7e2aa5dc81a34aedf0cad4c32545;
   Комментарий:  Update CHANGELOG.md;
   Команда: $ git show --pretty=reference aefea
#
2. Коммиту с хэшем 85024d3 соответствует тег v0.12.23
   Команда: $ git show 85024d3
#
3. У коммита b8d720 2 родителя: 56cd7859e05c36c06b56d013b55a252d0bb7e158 и 9ea88f22fc6269854151c571162c5bcf958bee2b
   Команда: git log --pretty=%P -n 1 b8d720
#
4. Команда: $ git log v0.12.23..v0.12.24
   1) b14b74c4939dcab573326f4e3ee2a62e23e12f89
      [Website] vmc provider links
   2) 3f235065b9347a758efadc92295b540ee0a5e26e 
      Update CHANGELOG.md
   3) 6ae64e247b332925b872447e9ce869657281c2bf 
      registry: Fix panic when server is unreachable
      Non-HTTP errors previously resulted in a panic due to dereferencing the
      resp pointer while it was nil, as part of rendering the error message.
      This commit changes the error message formatting to cope with a nil
      response, and extends test coverage.
      Fixes #24384
   4) 5c619ca1baf2e21a155fcdb4c264cc9e24a2a353
      website: Remove links to the getting started guide's old location
      Since these links were in the soon-to-be-deprecated 0.11 language section, I
      think we can just remove them without needing to find an equivalent link.
   5) 06275647e2b53d97d4f0a19a0fec11f6d69820b5
      Update CHANGELOG.md
   6) d5f9411f5108260320064349b757f55c09bc4b80
      command: Fix bug when using terraform login on Windows
   7) 4b6d06cc5dcb78af637bbb19c198faff37a066ed
      Update CHANGELOG.md
   8) dd01a35078f040ca984cdd349f18d0b67e486c35
      Update CHANGELOG.md
   9) 225466bc3e5f35baa5d07197bbc079345b77525e
      Cleanup after v0.12.23 release
#
5.  






# Домашнее задание к занятию "3.1. Работа в терминале, лекция 1"
пункт 5: Оперативная память - 1024Mb, 2 ядра процессора, интегрированная графическая карта 4мб видеопамяти, жесткий диск SATA-0 64 ГБ свободного пространства, гигабитная сетевая карта. Данные ресурсы являются ресурсами по умолчанию.
#
пункт 6:  В файле настроек Vagrantfile необходимо добавить следующий код:
#
config.vm.provider "virtualbox" do |vb|
  vb.memory = 2048
  vb.cpus = 4
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
пункт 11: конструкция проверяет наличие файлов в дирректории /tmp и предварительно проверяет существование данной директории.
#
пункт 13: Команда at используется для выполнения команды на заданное время один раз. Команда batch используется для выполнения одноразовых задач, которые должны выполняться, когда загрузка системы становится минимальной.
