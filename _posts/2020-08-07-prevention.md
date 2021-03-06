---
layout: post
title: Профилактика антресольного оборудования
subtitle: Профилактика (от греч. πρόφύλακτικός - предохранительный) - предупредительные меры для поддержания технического объекта и оборудования в исправном или работоспособном состоянии.
cover-img: /assets/img/03banner.jpg
tags: [gen8, apc, ups, bios, firmware]
---
Совсем не часто я провожу профилактику антресольного оборудования. В этот раз стало казаться, что вентиляторы микросервера стали громче шуршать. Предыдущий раз разбирал корпус наверное около двух лет назад.
<!--more-->
![Внешний вид](https://raw.githubusercontent.com/toleeck/toleeck.github.io/master/assets/img/03cleaningmb.jpg)
Особенно тяжко даётся отсоединить штекер питания из материнской платы. В остальном всё не сложно. Корпус очень грамотно спроектирован, хоть и тесновато там внутри.
Уборку производил подручными средствами: бытовым пылесосом прочистил вентилятор обдува корзины жёстких дисков и вентилятор блока питания, кулеры на материнской плате протёр ватными дисками и ватными палочками, использовал медицинский спирт. Вентиляторы снимал и смазывал маслом для обслуживания электробритвы Panasonic, но сами радиаторы и кулеры не снимал и пасту не менял.

На самой плате есть некоторые модификации:
* стоковый процессор заменён на xeon e3-1270v2. Он не горячий и можно было бы использовать его с родным радиатором, но когда-то было решено установить низкопрофильный кулер [akasa k25](http://www.akasa.com.tw/search.php?seed=AK-CC7118HP01). Запитан он через [термистор](https://aliexpress.ru/item/32428122979.html);
* радиатор с южного моста перекинул на чип iLO. Там посадил его на липкую [термопрокладку](https://aliexpress.ru/item/32608552933.html);
* на южный мост установил кулер [Deepcool Nbridge 2](https://deepcool.com/product/dcoolingaccessory/accessory/2013-12/48_650.shtml);
* на ethernet-чип влепил мини-радиатор zalman.
![Материнская плата с доработками](https://raw.githubusercontent.com/toleeck/toleeck.github.io/master/assets/img/03motherboard-g8.jpg)

Попутно решил глянуть что там есть насчёт firmware на сайте у HP. Был приятно удивлён, что для такой старой модели до сих пор выпускают обновления. Обновил биос и иЛО:
![bios](https://raw.githubusercontent.com/toleeck/toleeck.github.io/master/assets/img/03bios.png){: .mx-auto.d-block :}
![ilo1](https://raw.githubusercontent.com/toleeck/toleeck.github.io/master/assets/img/03ilo1.png){: .mx-auto.d-block :}
![ilo2](https://raw.githubusercontent.com/toleeck/toleeck.github.io/master/assets/img/03ilo2.png){: .mx-auto.d-block :}



А совсем недавно вышел из строя старенький ибп [apc smart-ups 1000](https://www.apc.com/shop/ru/ru/products/APC-Smart-UPS-1000-USB-230-/P-SUA1000I?isCurrentSite=false) третьего поколения, от которого питается электричеством всё антресольное оборудование.
Было плановое отключение электричества, после которого он не включился.
Я покупал его достаточно б/у-шным с не новыми батареями. После приобретения я ни разу внутрь не заглядывал. Года три точно прошло. В общем пришло его время.
Обе батареи были немного вздутыми, одна даже треснула:
![bios](https://raw.githubusercontent.com/toleeck/toleeck.github.io/master/assets/img/03brokenbattery.jpg)
Предохранитель на перемычке между батареями тоже выглядел удручающе:
![bios](https://raw.githubusercontent.com/toleeck/toleeck.github.io/master/assets/img/03fuse.jpg)
Батареи были заменены на новые CBS, предохранитель купил в ближайшем автомагазине. После установки новых батарей произвёл калибровку через утилиту [UpsDiag2](http://saprjkin.narod.ru/upsdiag.htm). Калибровал через не родной, но специальный, usb2com адаптер с эмуляцией виртуального com-порта.
