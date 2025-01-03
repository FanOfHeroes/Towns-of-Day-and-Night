### Мод: **Towns of Day and Night**
> [!TIP]
> Вы можете самостоятельно добавить графику в этот мод [Руководство по модификации](#Modification)
---

#### **Обзор**

"Towns of Day and Night" выводит на новый уровень погружение и реализм в **Heroes of Might and Magic III**. С этим модом города в вашей игре будут динамически менять свой облик в зависимости от времени суток. Наблюдаете ли вы восход солнца над безмятежным Оплотом или наблюдаете за таинственными сумерками, опускающимися на Некрополис, каждый город предложит визуально уникальный опыт, который углубит вашу связь с миром.

---

#### **Особенности**

- **Динамическая смена времени суток**: города теперь меняют свой облик с течением времени, демонстрируя прекрасные переходы между **рассветом**, **днем**, **закатом** и **ночью**.

- **Уникальная атмосфера для каждого типа города**: каждый тип города имеет свою собственную тщательно проработанную дневную и ночную графику, усиливающую его неотъемлемые характеристики:
- **Замки** сияют в лучах солнечного света и приобретают теплое сияние в сумерках.
- **Некрополи** становятся темнее и жутче с наступлением ночи, окутанные тайной.
- **Башни** отражают меняющиеся оттенки неба, от ясного утра до сумеречных звезд.

- **Построение иммерсивного мира**: почувствуйте игру как никогда раньше, где каждое посещение города ощущается живым и реагирует на течение времени. Исследуйте города на рассвете, ожидая приключений, или готовьтесь к ночным испытаниям, когда тени сгущаются.

- **Плавные переходы**: визуальные изменения между временем суток плавные и естественные, разработанные для сохранения эстетической целостности оригинальной игры, при этом улучшая ее атмосферу.

---
#### **Скриншоты**

- **Утро в замке**
[**Утро в замке**](https://raw.githubusercontent.com/FanOfHeroes/Towns-of-Day-and-Night/refs/heads/main/Screens/0.png)

- [**Ночь в некрополисе**](https://raw.githubusercontent.com/FanOfHeroes/Towns-of-Day-and-Night/refs/heads/main/Screens/6.png)

- [**Сумерки в крепости**](https://raw.githubusercontent.com/FanOfHeroes/Towns-of-Day-and-Night/refs/heads/main/Screens/4.png)

---

#### **Почему этот мод?**

**Heroes III** давно пользуется популярностью благодаря богатым стратегическим и фэнтезийным элементам, но этот мод добавляет в игру новый слой жизни. Вместо статичных городских экранов вы получите мир, который кажется более живым и реагирует на время суток. Строите ли вы свое королевство под ярким солнцем или защищаете свою цитадель под покровом темноты, «Towns of Day and Night» предлагает незабываемое улучшение вашего игрового процесса.

---

#### **Авторы**

- **Идея и оформление**: **FanOfHeroes**
- **Разработка кода и плагина**: **daemon_n**

Этот мод стал возможен благодаря творческому видению FanOfHeroes и технической экспертизе daemon_n
---

## Modification

Вы также можете изменить/добавить графику не только для любого из стандартных 9 городов, но и для новых городов, которые могут быть добавлены в игру иными модами:
> [!IMPORTANT]
> Вы можете (а я, daemon_n, рекомендую) помещать вашу графику в архивы иных модов, чтобы при обновлении данного мода не потерять внесённые изменения;

### Добавление/Изменение статичного фона городов
- создать картинку фона в формате "png" и размером 800x374;
- назвать согласно префиксу города, добавив "время дня" в имя файла по шаблону "[prefix]_[time]BG.png":
	```
	например, картинка для времени "0" и города "Цитадель" будет называться "TBSt_0BG.png";
	```
- поместить картинку в ваш zip-файл (в данном моде используется [data/todan_pcx.zip](data/todan_pcx.zip)) в подпапку "data/pcx/[townName]", где "townName" - имя города;

### Добавление анимированного фона
- создать набор картинок фона в формате "png" и размером 800x374;
- назвать согласно префиксу города, добавив "время дня" и "индекс" кадра в имя файла по шаблону "[prefix]_[time][index].png":
	```
	например, 7-я (считаем с 0) картинка для времени "2" и города "Башня" будет называться "TBTW_27.png";
	```
- поместить картинки в ваш zip-файл (в данном моде используется [data/todan_pcx.zip](data/todan_pcx.zip)) в подпапку "data/pcx/[townName]/animated", где "townName" - имя города;
> [!NOTE]
> Важно последовательное наименование файлов, чтобы анимация проигрывала все кадры, также после последнего кадра вновь отображается картинка с индексом "0";

### Добавление эффектов погоды
- создать "def"-файл-пустышку с кадрами размером 800x374 и количеством, нужном для вашей анимации;
- создать нужное количество кадров в формате "png" и размером 800x374, которые будут заменять кадры-пустышки;
- поместить "def" внутрь любого "pac"-файла, чтобы игра его загрузила;
- поместить "png"-файлы внутрь вашего zip-файла (в данном моде используется [data/todan_defs.zip](data/todan_defs.zip)) в подпапку "defs/[defName.def]/", где [defName.def] - имя вашего "def"-файла-пустышки;
- Создать json ключ в вашем json файле любого активного мода в подпапке "Lang" в формате:
	- "todan.animations.[prefix].[index]", где [prefix] отвечает за уникальный префикс каждого города, а [index] - за время суток, в котором будет использоваться данная анимация;
	> [!NOTE]
	> если выставить [index] = "-1", тогда эффект погоды будет работать в любое время суток для данного типа городов;
	- прописать имя "def"-файла-пустышки в значение созданного ключа;
	- например, анимация вулкана в Инферно на время "1" устанавливается вот так:
	```
	{
	"todan": {
        "animations": {
            "TBIn": {
                "1": [
                    "volcano.def"
                ]
				}
			}
		}
	}
	```
	или же просто ``"todan.animations.TBIn.1":"volcano.def"``;
	- можно установить несколько анимаций погоды для каждого города/времени (до 5 на данный момент);
	- иные примеры можно посмотреть в файле с настройками мода: [Lang/todan_settings.json](Lang/todan_settings.json);

### Добавление поддержки новых городов:
- создать нужное количество кадров в формате "png" и необходимого размера, которые будут заменять кадры оригинальных зданий в формате "0_[index].png", где [index] отвечает за номер кадра здания;
- cоздать json ключ в вашем json файле любого активного мода в подпапке "Lang" в формате:
	```
	"todan.townTypeNames.[prefix]":"[townTypeName]";
	```
	где [prefix] отвечает за уникальный префикс добавленного города, а[townTypeName] отвечает за имя папки со зданиями, которые используются для хранения png-картинок для замены оригинальных def-файлов зданий;
- поместить "png"-файлы внутрь вашего zip-файла (в данном моде используется [data/todan_defs.zip](data/todan_defs.zip)) в подпапку "defs/buildings/[townTypeName]/[time]/[buildingDefName.def]/", где:
	- [townTypeName] - имя папки, которую вы прописали пунктом выше;
	- [time] - время суток, для которого будет работать замена графики;
	- [buildingDefName.def] - имя def файла каждого строения (они везде одинаковы) "def"-файла-пустышки;

## info
### Список префиксов стандартных городов:
- "TBCs": "Castle"
- "TBDn": "Dungeon"
- "TBEl": "Conflux"
- "TBFr": "Fortress"
- "TBIn": "Inferno"
- "TBNc": "Necropolis"
- "TBRm": "Rampart"
- "TBSt": "Stronghold"
- "TBTw": "Tower"
