# 1.4. Рендеринг
Итак, у нас есть объект с материалом и наложенной текстурой – пора, наконец-то, отрендерить его! Рендерингом (или визуализацией) в компьютерной графике называют процесс перевода математической модели объектов в графическое представление. В Blender это делается путем проецирования вершин, составляющих объекты, на экранную плоскость и вычисления пикселей между ними путем растеризации полигонов. 

Существует также другой подход – расчет траекторий лучей (или, как говорят специалисты, трассировка лучей). Для каждой точки растрового изображения проводится луч в некоем известном направлении (это может быть, например, вектор от позиции наблюдателя). Затем происходит перебор всех объектов-примитивов трехмерной сцены. Трассировщик проверяет луч на пересечение с примитивом и получает координаты точки пересечения. Если на сцене присутствуют источники света, проводятся дополнительные лучи от полученной точки к источникам света. На основании полученной информации (а также заранее определенных констант), вычисляется цвет пикселя в данной точке. 

Blender использует трассировку лучей при расчете зеркального отражения и преломления. Кроме того, на основе трассировки лучей построен новый рендер-движок Cycles, который теперь также является частью Blender (впрочем, Cycles, будучи большой и достаточно сложной в освоении системой, выходит за рамки охвата этой книги). 

Для построения проекции трехмерной сцены нам нужна виртуальная камера – объект, который, подобно реальной камере, будет «снимать» происходящее со своей точки обзора. По умолчанию Blender уже добавил на сцену одну камеру: вам остается только нажать клавишу `F12`, и вы увидите рендер, сделанный через нее. Чтобы вернуться обратно к сцене, нажмите Escape.
 
Камеру можно перемещать и поворачивать, как и любой другой объект. Чтобы понаблюдать, как сцена видна через камеру, можно сменить вид: выберите в меню View → Camera. Теперь нажмите клавишу N и в появившейся левой панели инструментов найдите вкладку View. Поставьте галочку напротив Lock Camera to View. Рамка паспарту теперь станет красной, а камера будет привязана к точке наблюдения навигации. То есть, если вы повернете точку наблюдения средней кнопкой мыши, камера тоже повернется соответствующим образом – это позволяет быстро настроить камеру наилучшим для вас образом. Не забудьте только отключить этот режим привязки, когда закончите позиционировать камеру. 

Настройки рендеринга находятся на той же панели свойств, в первой группе – Render. На вкладке Dimensions можно изменить разрешение финального изображения, а также указать процент масштаба финального изображения – это необходимо для быстрой визуализации маленьких промежуточных картинок. Сделав рендер клавишей `F12`, вы можете сохранить его: выберите в меню Image → Save As Image... В диалоге выбора файла вы можете указать формат сохранения (PNG, JPEG, Targa, OpenEXR, HDR, TIFF и др.), коэффициент сжатия и другие параметры. 

Добавим, что любое отрендеренное изображение можно не только сохранить, но и использовать внутри Blender для дальнейшей работы – в качестве текстуры для объекта или где-нибудь еще.

[Назад](materials) ● [К оглавлению](../index) ● [Далее](../ch2/lights) 

