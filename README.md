# **Информация по игре Ace of Spades 0.75 и сервере zhabaserver**
v0.3.6  
by EvgenZhaba
____

# Клиент 

## 1. Где и что взять
Все дистрибутивы также есть в папке `1. distrib`  
https://www.buildandshoot.com/download/ - тут можно скачать: лаунчер, OpenSpades (win, mac), оригинальный клиент 0.75, 0.76.

### 1.1 Лаунчер buildandshoot
http://launcher.buildandshoot.com/Build%20and%20Shoot%201.2%20Setup.exe  
SHA1: 9F24C2749B7697262284F615D44199F3ECD22831

Менеджер версий, графический интерфейс для конфига.  

### 1.2 OpenSpades  
mac: https://github.com/yvt/openspades/releases/download/v0.1.3/OpenSpades-0.1.3-Windows.zip  
SHA1: 8B8389F8263AA9ED1AAA3CE437004F2BC7C3C086  
windows: https://github.com/yvt/openspades/releases/download/v0.1.3/OpenSpades-0.1.3-Windows.zip  
SHA1: 19E127BCCC73715A1CB5974F66929F62E3040100  

Основная страница: https://openspades.yvt.jp/  
Страница на гитхабе: https://github.com/yvt/openspades/releases  

Графонистая версия клиента.  

### 1.3 Voxlap
0.75  
http://www.spadille.net/aos075install.msi  
SHA1: 46D03AC636CF8BBB49D43133DE791C4AB60059C9  

Тот самый тузач 0.75. Ванильная версия. Используется на большинстве серверов мастер-сервера https://www.buildandshoot.com/servers/

0.76  
http://www.spadille.net/aos076install_rc10.msi  
SHA1: EB22B5ACDDD0EEE0513376186816515CB7A413D3

Ace of Spades 0.76. Редко используется.

### 1.4 Spadille  
https://nateshoffner.com/projects/spadille/  
SHA1: 3B3ED500985F0065D52A8636185CAE3DBE5A8B8F  

Графический интерфейс. Показывает сервера с пингом, есть настройки для ванильного клиента. Можно подключиться напрямую по ip к какому-то серверу. Есть конвертер адреса в айпи и обратно. Встроен slab6 для редактирования файлов игры. Есть скриншотилка.   

## 2. Как это установить
Используемый порт: обычно 32887. Иногда сервер может использовать другой порт.  
Ссылки в браузере вида: `aos://число:порт:версия`  
Число по факту представляет собой перевод ip из 256-ричной системы счисления в десятичную. Переводить можно вручную, в spadille, или на сайте https://noway.github.io/aos-to-address/  
Ссылка обрабатывается браузером: открывается соответствующее приложение, указанное в настройках браузера.

## 3. Настройка конфигурации клиента

### 3.1 Voxlap (ванильный)
`Файловая структура`  

`config.ini` 
```
name                           = твой ник  
xres                           = разрешение по x  
yres                           = разрешение по y  
vol                            = громкость от 0 до 10  
inverty                        = инвертированность мыши  
windowed                       = в окне или нет (0 - полноэкранный)  
language                       = язык  
mouse_sensitivity              = чувствительность мыши  
show_news                      = открыть новостной сайт после закрытия игры  

Например:  
name                           = Player  
xres                           = 1280  
yres                           = 720  
vol                            = 10  
inverty                        = 0  
windowed                       = 0  
language                       = 0  
mouse_sensitivity              = 3.000000  
show_news                      = 0  
```
`controls.ini`  
Кнопки. Лучше не менять.  

`/kv6/`  
Файлы-ресурсы игры.  
Изменение моделек с сильно выходящими за их оригинальные пределы размерами не приветствуется.  
Открываются и редактируются в slab6, он также встроен в spadille. Если на win10 в slab6 мышка ведёт себя неадекватно, то в свойствах файла, во вкладке совместимость выбрать "Изменить параметры высокого DPI" и переопределить режим масштабирование на от приложения.  
http://www.advsys.net/ken/download.htm  
Прямая ссылка: http://www.advsys.net/ken/slab6.zip  
SHA1: 3EA61E3F12634A9AC0B208C99D311A3A39990BCF

`/png/`  
Изображения в игре.  
Тут можно отредактировать прицелы и прочие изображения. Лучше использовать графический редактор с поддержкой прозрачности, например Paint.NET. 

`/vxl/`  
Сюда сохраняется карта, если нажать f1 в игре.  

`/wav/`  
Звуки игры. Тоже можно заменить на свои.  

## 4. Управление
```
Передвижение:   W,S,A,D  
Прыжок:         Space  
Присесть:       Ctrl  
Шагом:          V  
Бежать:         L. Shift  
Стрелять:       L. Mouse  
Прицелиться     R. Mouse  
Общий чат:      T  
Командный чат:  Y  
Отправить сообщение: Enter  
Выбрать оружие:	1-4, Mouse Wheel  
Изменить цвет блока: Стрелочки  
Взять цвет блока, на который смотришь: E  
Карта:          M  
Таблица очков:	Tab  
Сменить команду: ,  
Сменить оружие:  .  
Сохранить карту: F1  
Сетевой график:  F11  
Громкость звуков: +/- Keypad  
Выход:           Esc  
```

### 4.1 Как в это играть

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
Все инструменты также есть в папке `2. tools`  

### pubovl
SHA1: 94C7737F8CE4C2600DCE3593754BBEA3D6E470DD  
Основное средство наблюдения от первого лица за игроками в режиме зрителя.  
Подключается любым dll инжектором. В папке лежит total injector.  
https://aloha.pk/index.php?topic=8329.0 - англоязычный гайд.  
```
X: Переключить подсветку противников сквозь стены.
Z: Показывать имена при включённой подсветке сквозь стены.
Стрелочки влево-вправо: Сменить наблюдаемого игрока, справа сверху номер и ник.
```

## 5.3 Советы
Самые используемые команды для поиска и бана хакеров:  
Поиск: **ip, whowas, accuracy, hackinfo, ratio**  
Наказание: **ban, dban, wban, banip, unban, undoban**  
Для поиска также используется pubovl. Если увидел, что прицел резко дернулся в голову другого игрока, которого не видно, или дергается туда-сюда по головам, раздавая хедшоты - это хакер. Если вдруг игрок как будто бы увидел того, кого на самом деле не должен видеть - это хакер. Но игрок может услышать по звукам кого-то - наблюдение нужно вести до полной уверенности.  

# Сервер

## 1. Общая информация об реализациях

### 1.1 Pyspades, Pysnip, Piqueserver

### 1.2 Как установить piqueserver.
Порты. Для резервирования piqueserver или zhabaserver пока текущий вариант: сделать venv.

### 1.3 Как установить zhabaserver 
Накатить piqueserver 1.0.0. Накатить файлы из папки.

## 2. Игровые режимы

### ctf
Первый из двух стандартных режимов. Нужно взять интел врага и принести в свою палатку. За каждый интел - 10 очков. 3 принесённых интела - победа.  

### tc
Второй из двух стандартных режимов. Нужно захватить все точки, захват происходит, когда рядом нет врагов.  Все точки захвачены - победа.  

### onectf
Модификация ctf. Интел общий, лежит в центре.  

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
Переключить возможность начать голосование для этого игрока. Без аргумента - для всех игроков. Для администраторов.  
**/cancel**  
Отменить текущее голосование. Для инициатора или администраторов.  

`\piqueserver\scripts\trusted.py` :star:  
Позволяет выдавать доверие игрокам - доверенные игроки не могут быть кикнуты голосованием. Для администраторов.  
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

`\piqueserver\scripts\rapid.py` :star:  
Переключает режим на быструю стрельбу и строительство. Для администраторов.  
**/rapid \<player\>**  
Переключить режим быстрой игры для этого игрока.  

`\piqueserver\scripts\spadenadefix.py` :star:  
Исправляет баг(фичу) броска гранаты с уменьшенным временем взрыва.   

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
Без аргумента - вывести текущее время. С аргументом - для администраторов - установить текущее время (в часах).  

`\piqueserver\scripts\votemap_.py` :star:  
Убрана функция lower(), из-за которой имя карты неправильно отображалось и соответственно вводилось - карта, в имени которой буквы разных регистров, не выбиралась. Также тут убран сломанный декоратор @player_only. Добавлена возможность выбора карты по её номеру в выводе votemap.  
Голосование за выбор следующей карты.  
**/votemap**  
Начать голосование за смену карты.  
**/vote \<map name\>**  
Проголосовать за эту карту. Вместо имени карты можно ввести её номер из votemap.  

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

`\zhabaserver\scripts\box.py` :star:  
Строит и удаляет параллелепипеды.  Для администраторов.  
**/box**  
После ввода 2 кубиками отметить точки, построится пустая коробка.  
**/db**  
После ввода сломать 2 кубика, между ними всё удалится.  

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

`\zhabaserver\scripts\pingstaff.py` :star:  
Сообщение админам отправляется не только админам, но и модераторам, и гвардам.  
**/admin \<message\>**  
Отправить сообщение всем админам, модераторам и гвардам онлайн.  

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

`\zhabaserver\scripts\updatemap.py` :star:  
Изменяет порядок выбора карт в ротации. Теперь выбираются случайно, перебирая все карты из ротации без пропусков. 3 последние карты гарантированно не будут поставлены. У каждой карты есть рейтинг для малого(больше 4) и большого (больше 14) количества игроков. В конце карты на основе текущего количества игроков и соответствующего рейтинга карт определяется следующая карта. Также при остановке сервера состояние сохраняется: название текущей карты, рейтинги, 3 последних карты; и при запуске вновь состояние загружается, ставится та карта, что была перед остановкой сервера. Рейтинги карт и состояние сервера хранятся в разных файлах.  
**/getmaps**  
Вывести список из лучших 7 карт-кандидатов с их рейтингом на текущий момент при текущем количестве игроков.  
**/lastmaps**  
Вывести 3 последние карты, которые не будут поставлены автоматически следующей картой.  

### 3.4 Для определенных карт или режимов

`\zhabaserver\scripts\rmatch.py` :star:  
Проведение матчей. До и после матча нельзя что-то построить, сломать или нанести любой урон.  
На основе https://www.buildandshoot.com/forums/viewtopic.php?t=9634  
**/start**  
Начать матч.  
**/stop**  
Закончить матч.  

`\zhabaserver\scripts\nothold.py` :star:  
Запрещает удержание интела: через 45 секунд игрока с интелом убивает. Для матчей.  

`\zhabaserver\scripts\onectf_update.py` :star:  
Позволяет сдать интел в чужую палатку, при этом интел не засчитается и появится в центре. Также задает координаты для спавна на карте muhosransk. Для матчей.  

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
