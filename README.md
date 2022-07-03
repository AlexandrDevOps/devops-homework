
                                             # Домашнее задание к занятию "5.1. Основы виртуализации"

 ##  1. Опишите кратко, как вы поняли: в чем основное отличие полной (аппаратной) виртуализации, паравиртуализации и виртуализации на основе ОС.
### Ответ:
  * Под аппаратной виртуализацие понимается набор технологий и инструкций представленный в разных микропроцессорных архитектурах позволяющий развернуть изолированные друг от друга гостевые ОС с помощью аппаратных средств. Одной из первых компаний начавших разработки в данном направлении была компания IBM в серии микропроцессоров POWER4 2001 год. На сегодняшний день существует большое количество решений например Intel VT, AMD-V, ARM Cortex A15. 
  * При Паравирутализации, гостевая ОС получает только те ресурсы, которые были выделены ей гипервизором. Гипервизор это программа обеспечивающая промежуточный слой между ОС на которой она развернута и гостевой ОС виртуализацию которой необходимо обеспечить.
  * При использовании виртуализации на основе ОС контейнеры (условно виртуальные машины) используют все доступные ресурсы хостовой машины: аппаратные системные устройства, доступные области памяти, динамические библиотеки, но при этом изолированы друг от друга и используют ресурс одного ядра ОС на которой развернуты.
  ## 2. Выберите один из вариантов использования организации физических серверов, в зависимости от условий использования.
 ### Ответ:
  * Высоконагруженная база данных, чувствительная к отказу - Физический сервер:
        Данное решение требуется для более высокого отклика как базы данных, так и приложений работающих непосредственно с ней. Плюс данное решение существенно сократит точки отказа в виде гостевых систем или гипервизоров.      
  * Различные web-приложения - Виртуализация уровня ОС (контейнеры):
        Требуется меньше ресурсов, выше скорость масштабирования при необходимости расширения. Нет жестких требований к аппаратнымм ресурсам, требует меньше ресурсов на администрирование.
  * Windows системы для использования Бухгалтерским отделом - Паравиртуализация:
        Организация бекапов существенно проще реализуема плюс для развертывания или восстановления нужны менее квалифицированные специалисты. Насыщенный рынок доступных кроссплатформенных решений включая решения в ядре системы Windows начиная с 10 профессиональной версии. Простой перенос существующей системы в случае апгрейда аппаратного парка.       
  * Системы, выполняющие высокопроизводительные расчеты на GPU - физический сервер:
        Необходима высокая скорость работы системы без дополнительных "слоев" программного обеспечения. Меньше точек отказа самой системы.
