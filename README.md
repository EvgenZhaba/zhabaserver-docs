# **Информация по игре Ace of Spades 0.75 и сервере zhabaserver**
v0.2.1
____

# Клиент 

## 1. Где и что взять
Дистрибутивы. Менеджеры версий (бенис лончер, spadille). Возможно md5 для каждого дистра написать. 

## 2. Как это установить
Порты. Обработка браузером ссылок. Как делается ссылка. 

## 3. Настройка конфигурации клиента
Конфиг.ини. Контролс.ини. Файловая структура. Кастомизация. 

## 4. Как в это играть

### 4.1 Управление

### 4.2 Команды
У каждого игрока **[player]** есть свой номер, например, #1. Игрока можно указать по его нику или его номеру. Если в команде, где надо указать игрока, ничего не указать, то по умолчанию команда подействует на вводимого.  
Время **\<duration\>** вводится в формате вида 1d1h1m1s = 1 день + 1 час + 1 минута + 1 секунда. Для, например, 5 минут 32 секунд будет 5m32s. Более подробно и другие способы ввода: `\piqueserver\utils\_timeparse.py`

Часто используемые команды: **time, streak, ping, intel, kill, pm**

`исходный файл`  
**Команда \<Обязательно\> [Необязательно]** *Краткая команда*  
Описание

`\piqueserver\core_commands\game.py`  
**/time**  
Вывести оставшееся время до смены карты.  

`\piqueserver\core_commands\info.py`  
**/streak**  
Вывести текущую серию убийств (количество убийств с момента прошлой смерти).  
**/ping [player]**  
Вывести пинг (задержку) до сервера.  
**/rules**  
Вывести правила сервера.  
**/commands**  
Вывести все доступные команды.  
**/help \<command_name\>**  
Вывести справку по команде (на англ языке).  

`\piqueserver\core_commands\map.py`  
**/mapname**  
Вывести название текущей карты.  
**/showrotation**  
Вывести список карт.  

`\piqueserver\core_commands\player.py`  
**/client [player]** *cli*  
Вывести информацию о клиенте этого игрока.  
**/weapon \<player\>**  
Вывести информацию об оружии этого игрока. Аргумент обязателен.  
**/intel**  
Вывести того, кто несёт вражеский интел.  
**/kill**  
Убить себя.  
**/deaf**  
Переключить получение сообщений чата.  

`\piqueserver\core_commands\server.py`  
**/server**  
Вывести имя и адрес сервера.  
**/version**  
Вывести версию сервера.  
**/scripts**  
Вывести список скриптов на сервере.  

`\piqueserver\core_commands\social.py`  
**/pm \<player\> \<message\>**  
Отправить личное сообщение этому игроку.  
**/admin \<message\>**  
Отправить сообщение всем админам онлайн.

### 4.3 Советы

## 5. Администрирование

### 5.1 Команды

Авторизация: login. Часто используемые команды: **timelimit, map, advancemap, kick, ban, dban, wban, banip, unban, undoban, say, mute, unmute, ip, whowas, god, godsilent, unstick, teleport, tpsilent, fly, login**

`\piqueserver\core_commands\game.py`  
**/resetgame**  
Перезапуск карты.  
**/lock \<2ch|0chan|spectator\>**  
Заблокировать эту команду для выбора новыми игроками.  
**/unlock \<2ch|0chan|spectator\>**  
Разблокировать эту команду для выбора новыми игроками.  
**/switch [player]**  
Сменить у игрока команду. Не работает для наблюдателей.  
**/setbalance \<on|off\>**  
Включить/выключить автобаланс.  
**/togglebuild [player]** *tb*  
Переключить возможность строить для этого игрока. Без аргумента - для всех игроков.  
**/togglekill [player]** *tk*  
Переключить возможность стрелять для этого игрока. Без аргумента - для всех игроков.  
**/toggleteamkill** *ttk*  
Переключить возможность стрелять по своим.  
**/globalchat \<on|off\>**  
Включить/выключить глобальный чат.  
**/timelimit \<duration\>**  
Установить время до смены карты.  
**/fog red green blue** (all values 0-255)  
**/fog #aabbcc** (hex representation of rgb)  
**/fog #abc** (short hex representation of rgb)  
Установить цвет тумана.  

`\piqueserver\core_commands\map.py`  
**/map \<mapname\>**  
Установить эту карту следующей после смены карты.  
**/rotation \<map1\> ... \<mapN\>**  
Изменить текущий список карт и уведомить об этом всех на сервере.  
**/rotationadd \<map\>**  
Добавить в список карт эту карту.  
**/revertrotation**  
Вернуть текущий список карт.  
**/advancemap**  
Переход к следующей карте в списке карт.  

`\piqueserver\core_commands\moderation.py`  
**/kick \<player\> [reason]**  
Кикнуть(выгнать) этого игрока.  
**/ban \<player\> [duration] [reason]**  
Забанить этого игрока.  
**/hban \<player\> [reason]**  
Забанить этого игрока на час.  
**/dban \<player\> [reason]**  
Забанить этого игрока на день.  
**/wban \<player\> [reason]**  
Забанить этого игрока на неделю.  
**/pban \<player\> [reason]**  
Забанить этого игрока навсегда.  
**/banip \<ip\> [duration] [reason]**  
Забанить по айпи.  
**/unban \<ip\>**  
Разбанить по айпи.  
**/undoban**  
Отменить последний бан.  
**/say \<text\>**  
Сказать что-то в чат от имени сервера.  
**/mute \<player\>**  
Отключить чат этому игроку.  
**/unmute \<player\>**  
Включить чат этому игроку.  
**/ip [player]**  
Узнать айпи этого игрока.  
**/whowas \<player\>**  
Узнать айпи вышедшего с сервера игрока по его нику.  
**/invisible [player]** *invis inv*  
Переключить невидимость этого игрока. (вылетает на ванильном клиенте, если потом зайти в режиме наблюдения и попытаться переключиться на этого игрока)  
**/godsilent [player]**  
Без уведомления всем переключить этого игрока в режим бога (никто не может нанести урон, снимается при попытке выстрелить в кого-то).  
**/god [player]**  
С уведомлением всем переключить этого игрока в режим бога.  
**/godbuild [player]**  
Выдать право этому игроку строить блоки, которые могут разрушить только игроки в режиме бога.  

`\piqueserver\core_commands\movement.py`  
**/unstick [player]**  
"Освободить" этого игрока из блоков - переместить на открытое пространство рядом.  
**/moves [player] \<sector\>**  
**/moves [player] \<x\> \<y\> \<z\>**  
Без уведомления всем переместить этого игрока по координатам или в сектор. Если координата z в воздухе, то перемещает на землю.  
**/move [player] \<sector\>**  
**/move [player] \<x\> \<y\> \<z\>**  
С уведомлением всем переместить этого игрока по координатам или в сектор. Если координата z в воздухе, то перемещает на землю.  
**/where [player]**  
Вывести координаты этого игрока.  
**/teleport [player] \<target player\>** *tp*  
С уведомлением всем переместить себя (или заданного игрока) к этому игроку.  
**/tpsilent [player] \<target player\>** *tps*  
Без уведомления всем переместить себя (или заданного игрока) к этому игроку.  
**/fly [player]**  
Переключить возможность полёта для этого игрока - с зажатым ctrl можно бесконечно прыгать в воздухе.  

`\piqueserver\core_commands\player.py`  
**/kill [target]**  
Убить этого игрока.  
**/heal [player]**  
С уведомлением всем применить эффект палатки на этого игрока.  
**/deaf [player]**  
Переключить получение сообщений чата этого игрока.  

`\piqueserver\core_commands\server.py`  
**/servername \<new-name\>**  
Изменить имя сервера. В мастер-сервере тоже обновится.  
**/togglemaster** *master*  
Переключить видимость сервера для мастер-сервера.  

`\piqueserver\core_commands\social.py`  
**/login \<password\>**  
Авторизоваться под паролем для получения доступа к большему списку команд. 3 попытки, затем кикнет.

## 5.2 Средства
pubovl


# Сервер

## 1. Общая информация об реализациях

### 1.1 Pyspades, Pysnip, Piqueserver

### 1.2 Как установить piqueserver.
Порты. Для резервирования piqueserver или zhabaserver пока текущий вариант: сделать venv.

### 1.3 Как установить zhabaserver 
Накатить piqueserver 1.0.0. Накатить файлы из папки.

## 2. Игровые режимы
Описания.
- ctf
- tc
- onectf
- tow
- nuketown
- push
- babel
- добавить режимы

## 3. Скрипты
Возможны переводы некоторых страниц с инфой.  
Часто используемые команды: **rollback, votekick, y, cancel, ratio, squad, follow, airstrike, paint, votemap, vote**

### 3.1 Общеизвестные
Почти всегда включены на серверах. Имеющиеся на zhabaserver (ctf) помечены :star:

*Включены в стандартный конфиг.*

`\piqueserver\scripts\rollback.py` :star:  
Откатывает состояние карты к исходному поблочно. Для администраторов.  
**/rollmap \<map name\>**  
Меняет состояние текущей карты на заданную. Может занять много времени!  
**/rollmap \<map name\> \<sector\>**  
Меняет сектор текущей карты на этот же сектор заданной карты.  
**/rollback**  
Откатывает карту.  
**/rollbackcancel**  
Отмена отката карты.  

`\piqueserver\scripts\protect.py` :star:  
Защищает карту от строительства. Для администраторов.  
**/protect \<sector\>**  
Защитить выбранный сектор.  
**/protect**  
Убрать все защиты.  

`\piqueserver\scripts\map_extensions.py` :star:  
Позволяет расширить возможности карты в файле `mapname.txt`  
Пример:
```
extensions = { 'water_damage' : 2,
               'boundary_damage' : {'left' : 64,
                                    'right' : 448,
                                    'top' : 128,
                                    'bottom' : 384,
                                    'damage': 1 } }
```
`water_damage` - урон от воды  
`boundary_damage` - за пределами этой области будет наноситься урон `damage`  

`\piqueserver\scripts\disco.py` :star:  
Дискотека! Меняет цвет тумана. Для администраторов.  
**/disco**  
Переключить режим дискотеки.  

`\piqueserver\scripts\votekick.py` :star:  
Голосование за кик игрока.  
**/votekick \<player\> \<reason\>**  
Начать голосование за кик этого игрока по заданной причине.  
**/y**  
Согласиться с текущим голосованием.  
**/togglevotekick [player]** *tvk*  
Переключить возможность начать голосование для этого игрока. Без аргумента - для всех игроков.  
**/cancel**  
Отменить текущее голосование. Для инициатора или админов.  

`\piqueserver\scripts\trusted.py` :star:  
Позволяет выдавать доверие игрокам - доверенные игроки не могут быть кикнуты голосованием.  
**/trust \<player\>**  
Сделать этого игрока доверенным.  

`\piqueserver\scripts\ratio.py` :star:  
Выводит соотношение количество убийств/смертей. Должно быть в конфиге после скрипта votekick!
**/ratio \<player\>**  
Вывести соотношение количество убийств/смертей.  

`\piqueserver\scripts\passreload.py` :star:  
**/reloadconfig**  
Перезагружает конфиг (без скриптов). Для администраторов. 

`\piqueserver\scripts\blockinfo.py` :star:  
Помогает искать гриферов. Для администраторов.  
**/griefcheck \<player\> \<minutes\>** *gc*  
Вывести, сколько этот игрок за это время сломал блоков.  

`\piqueserver\scripts\squad.py` :star:  
Даёт возможность объединяться в сквады. Игроки в скваде возрождаются не на базе, а рядом с другим живым игроком из сквада.  
**/squad \<key\>**  
Вступить в сквад с заданным именем. Если такого нет, то создаёт сквад. 
**/follow \<player\>**  
Возрождаться всегда с этим игроком.  

`\piqueserver\scripts\afk.py` :star:  
Кикает неактивных игроков.  
**/kickafk \<minutes\> [amount]**  
Принудительно кикнуть игроков, неактивных больше указанного времени.  

*Не включены в стандартный конфиг, но доступны для подключения.*

`\piqueserver\scripts\airstrike2.py` :star:  
Позволяет вызвать удар с воздуха - бомбометание гранатами определённого сектора - при наборе серии 8 убийств. Для вызова нужно прицелиться, нажать V и пройти пару шагов.  
**/airstrike** *a*  
Вызвать удар с воздуха.  
**/givestrike \<player\>**  
Выдать этому игроку право вызвать удар с воздуха. Для администраторов.  

`\piqueserver\scripts\paint.py` :star:  
Раскраска блоков. Когда выбран блок и нужный цвет, нажатие V окрашивает блок, на который смотришь.    
**/paint \<player\>**  
Выдать этому игроку право красить блоки. Для администраторов.

`\piqueserver\scripts\spadenadefix.py` :star:  
Исправляет баг(фичу) броска гранаты с уменьшенным временем взрыва.  

`\piqueserver\scripts\votemap.py` :star:  
Голосование за выбор следующей карты.  
**/votemap**  
Начать голосование за смену карты.  
**/vote \<map name\>**  
Проголосовать за эту карту.  

### 3.2 Исправления
Некоторые скрипты из piqueserver 1.0.0 содержали ошибки. Исправленные версии подключены как сторонние скрипты.

`\zhabaserver\scripts\aimbot2_.py` :star:  
Заменено parse на timeparse.  
Инструменты для обнаружения читеров и повышения ЧСВ.  
**/accuracy \<player\>**  
Вывести точность этого игрока по каждому виду оружия.  
**/hackinfo \<player\>**  
Вывести точность этого игрока, соотношение убийств/смертей, сколько убийств в голову, сколько раз навёлся на голову противника с поворотом больше определённого угла (90 градусов). Для администраторов.  

`\zhabaserver\scripts\analyze_.py` :star:  
https://github.com/piqueserver/piqueserver/commit/133344db6a1146d1e4aadcaf921c4e60c11e677e  
35 строка обновлена: "if player.player_id not in protocol.players:"  
Показывает детальную аналитику выстрелов игроков. В кого стреляет, расстояние, время с предыдущего выстрела.  
**/analyze \<player\>** *an*  
Переключить наблюдение за этим игроком.  

`\zhabaserver\scripts\daycycle_.py` :star:  
https://github.com/piqueserver/piqueserver/commit/d78b63c72e634fe775eadbda8b6705c57b5d9063  
Заменено start_time на daycycle_start_time - такая глобальная переменная уже была.  
Меняет цвет тумана, имитируя день и ночь.  
**/dayspeed \<speed\>**  
Установить скорость смены дня и ночи. По умолчанию в 48 раз быстрее, чем в реальности. Без аргумента выведет текущее значение. Для администраторов.  
**/daytime \<time\>**  
Без аргумента - вывести текущее время. С аргументов - для администраторов - установить текущее время (в часах).  

`\zhabaserver\scripts\bansbugfix.py` :star:  
https://github.com/piqueserver/piqueserver/commit/0b95c7f276d32b843667fd760141964e87d7a427  
https://github.com/piqueserver/piqueserver/commit/d0ee645609447b423ead69ca6a62d1d6929c0acc  
Исправляет работоспособность банов.  

`\zhabaserver\scripts\globalchatbugfix.py` :star:  
Изменено определение функции: "def global_chat(connection, value):"  
Исправляет работоспособность команды globalchat. 

`\zhabaserver\scripts\playeronlybugfix.py` :star:  
https://github.com/piqueserver/piqueserver/issues/610  
Убирает сломанный декоратор @player_only  

`\zhabaserver\scripts\revertrotation.py` :star:  
Карты берутся из `protocol.config['rotation']`.  
Исправляет команду revertrotation. 

### 3.3 Прочие
Сторонние скрипты.

`\zhabaserver\scripts\allahuakbar.py` :star:  
Позволяет взрывом показать силу А%%%%а. Чем больше серия убийств, тем сильнее взрыв.  
Для самоподрыва достаточно любой фразы в чат, удовлетворяющей условию:  
`".*(a(ll|l)ah|a(ll|l)ahu).*((a(k|h)bar)|(a(k|h)ba))"`  
`".*DEUS.*VULT"`  
Например, "allahu akbar".

`\zhabaserver\scripts\checknick.py` :star:  
Проверяет ник на уязвимости. Некоторые имена пишут ошибку в логи сервера, некоторые имена нельзя использовать, например, для голосования за кик.  
Заменяет:  
Пустой ник на "gay empty"  
Ник с "#" на "gay sharp"  
Ник с "%" на "gay percent"  

`\zhabaserver\scripts\dropintel.py` :star:  
Делает красивую анимацию выброса интела.  
**/drop**  
Выбросить интел.  

`\zhabaserver\scripts\kicklimbo.py` :star:  
Кикает тех, кто слишком долго не может определиться с выбором команды.  

`\zhabaserver\scripts\printshortscripts.py` :star:  
Выводит список серверов на сервере, заменяя "piqueserver.scripts" на "ps".  
**/scripts**  
Вывести список скриптов на сервере с сокращёнными именами. 

`\zhabaserver\scripts\spadearena.py` :star:  
Короли Ринга! Оставляет только лопатки и переносит всех на арену в воздухе.   
**/spademode**  
Переключить режим.  

`\zhabaserver\scripts\trollscriptplus.py` :star:  
Издевательства над игроками. В первую очередь над читерами. Для администраторов.  
**/burn \<player\>**  
Поджечь этого игрока. Красный туман и потеря здоровья до смерти.  
**/flash \<player\> [time]**  
Быстрая смена цвета тумана для этого игрока. Можно задать время в секундах, по умолчанию - 10.  
**/repeldamage \<player\>** *rdmg*  
Весь нанесённый этим игроком урон перенаправляется в его же.  
**/noammo \<player\> \<name\>**  
Установить новое имя этому игроку.  
**/namechange \<player\>** *nc*  
Изменить имя этого игрока.  
**/messagechange \<player\> [message]** *msg*  
Заменяет все сообщения в чат этого игрока.  
**/showtrollcommands** *stc*  
Вывести список команд этого скрипта.  


### 3.4 Для определенных карт или режимов


# Карты

## 1. Создание карт
Ссылка на гуглдиск Ананаса. Описание механизма работы. CubeGL. Slab6. (прочее). Карты со скриптами. 

## 2. Как потестить карту
Запуск на ванильном сервере карты.

## 3. Список карт на сервере zhabaserver


# Культурное наследие сообщества

## 1. Пикчи

## 2. Видосы

## 3. Пасты
