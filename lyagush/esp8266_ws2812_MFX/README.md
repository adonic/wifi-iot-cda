Пакет спецэффектов для светодиодных лент WS2812.

В набор входит 4 иллюминационных эффекта: "камин", "радуга", "подсветка" и "метеор".

Настройка эффектов производится изменением значений глобальных переменных GET запросом, MQTT командами и в веб интерфейсе микроконтроллера (http://[IP]/configdes). 

В конструкторе кода вписать 9 в поле «глобальные переменные», а в «количество настроек»: вкл,длина,кол-во,1/скорость,цвет,насыщ1,ярко1,насыщ2,ярко2

Valdes 0 Выбор эффекта. 0 – Отключено. 1 – камин. 2 – радуга. 3 – подсветка. 4 – метеор.

Valdes 1 Количество светодиодов на ленте.

Valdes 2 Количество лент. 
Произведение количества светодиодов и лент не должно превышать 85. Эти параметры не обязательно указывать в соответствии с величиной подключенных лент. Например, для 1 ленты с 60  WS2812 можно указать 6 лент по 10 светодиодов. В таком случае по ленте будут пробегать одновременно 6 "метеоров".

Valdes 3 Скорость анимации.

Valdes 4 Цвет. Значения от 0 до 255 назначают цветовой тон палитры HSV. В "радуге" эта настройка не используется. На уровне 0 происходит цикличная смена цвета у "подсветки" и "метеора"

Valdes 5 и Valdes 7 Насыщенность начала и конца ленты. "Метеор" обесцвечивает передний край в пределах 255-129. На уровне 128 раскрашенные стороны меняются местами: передняя часть максимально насыщена, а хвост белый. По мере уменьшения значения весь метеор становится белым.

Valdes 6  и Valdes 8 Яркость. На уровне 0 происходит цикличная возрастание и спад яркости  "подсветки" и "радуги"

Параметры 7 и 8 задействованы только для "радуги" и "подсветки". Также для этих эффектов установка 0 яркости или насыщенности приводит к цикличному возрастанию и спаду этих параметров. 


Пример включения «камина» GET запросом на ленту из 30 элементов WS2812.
5 огоньков пламени по 6 диодов.

http://[IP]/valdes?int=1&set=6 
http://[IP]/valdes?int=2&set=5 
http://[IP]/valdes?int=3&set=15 
http://[IP]/valdes?int=4&set=0 
http://[IP]/valdes?int=0&set=1