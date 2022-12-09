# AAPS на смарт-часах с Wear OS

Приложение AndroidAPS можно установить в смарт-часах на ** Wear OS**. Версия на часах позволяет:

* **отображать данные на часах**: при помощи [пользовательских циферблатов](#aaps-watchfaces) или стандартных циферблатов с использованием [дополнений](#complications)
* **контролировать AAPS на телефоне**: чтобы подать болюс, установить временную цель и т. д.

### Перед тем как купить часы...

* Некоторые * дополнения *, требуют Wear OS версии 2.0 или новее
* Google переименовал *Android Wear 1.x* в *Wear OS* начиная с версии 2.x, так что *Android Wear* может означать старую версию 1.x системы
* Если описание смарт-часов указывает только на совместимость с * Android * и * iOS *-то это не **означает**, что они работают в * Wear OS *, - это может быть другой тип ОС от производителя часов, ** который несовместим с wear AAPS! **
* Проверьте [ список проверенных телефонов и часов ](../Getting-Started/Phones#list-of-tested-phones) и [ спросите пользователей ](../Where-To-Go-For-Help/Connect-with-other-users.md) в случае сомнений

### Создание Wear-версии AAPS

The Wear OS App of AAPS has been seperated from the AAPS build for the Android mobile. Therefore you have to generate a second signed APK. Select as module "AndroidAPS.wear" and as build variant "fullRelease" and a second apk file for the Wear OS clock is generated when [building the APK](../Installing-AndroidAPS/Building-APK.md) (or "pumpcontrolRelease" which will allow you to just remote control the pump without looping).

С марта 2021 года требуется самостоятельно устанавливать AAPS на часы, программа больше не доступна через циферблаты на Google Play. Его можно установить через [Wear Installer](https://youtu.be/8HsfWPTFGQI), который устанавливается как на часы, так и на телефон. The Wear Installer app can be downloaded from the Google Play Store. The linked video from Malcolm Bryant the developer of Wear Installer gives you detailed instructions to a) download the apk to your mobile b) setup the Android Debugger on the wear c) use Wear Installer on mobile and wear to sideload the AAPS wear app to the mobile. Once you have selected AndroidAPS as your app to upload wear version onto the watch you will be able to use watchfaces and complications and the AAPS controls.

### Настройка на телефоне

В конфигураторе AndroidAPS нужно [активировать Wear](../Configuration/Config-Builder#wear).

## Контроль AAPS с часов

AndroidAPS предусматривает возможность *управления* часами Android Wear. Если вы хотите подавать болюс и т. д. с часов, тогда в настройках часов Wear следует включить «Управление с часов».

С часов можно запустить следующие функции:

* установить временные целевые значения СК
* использовать калькулятор болюса (переменные могут быть определены в [настройках](../Configuration/Config-Builder#wear) на телефоне)
* расписать eCarbs
* подать болюс (инсулин + углеводы)
* настройки часов
* статус 
    * проверить состояние помпы
    * проверьте состояние замкнутого цикла
    * проверить и изменить профиль, CPP (Circadian Percentage Profile = time shift + percentage)
    * показать TDD (Общая суточная доза = болюс + базал в день)

## Циферблаты AAPS

Есть несколько часовых циферблатов на выбор, в которых показывается средняя дельта СК, активный инсулин IOB, действующий временный базал и профили базы и график мониторинга.

Убедитесь, что уведомления от AndroidAPS не заблокированы на часах. Подтверждение действия (например, болюс, временные цели) происходит через уведомления, которые нужно сдвинуть в сторону и нажать на галочку.

Чтобы быстрее попасть в меню AAPS, сделайте двойное нажатие на ГК. При двойном нажатии на кривую ГК можно изменить масштаб времени графика..

## Доступные циферблаты

![Доступные циферблаты](../images/Watchface_Types.png)

### Новый циферблат начиная с Android 2.8

![Цифровой стиль](../images/Watchface_DigitalStyle.png)

* Цвет, линии и круг настраиваются через меню - шестеренку в меню выбора циферблата.

## Циферблат AAPSv2 - Legend

![Циферблат Легенда AndroidAPSv2](../images/Watchface_Legend.png)

О - время с запуска последнего цикла

B - данные мониторинга ГК

C - минуты с последнего получения данных ГК

D - изменение по сравнению с последним полученным значением ГК (в mmol или mg/dl)

E - среднее изменение данных ГК за последние 15 минут

F - состояние аккумулятора телефона

G - скорость подачи базала (в ед/ч во время стандартной подачи и в % при временном базале TBR)

H - BGI (взаимодействие с глюкозой крови) -> Степень, с которой ГК “должна” расти или падать, основываясь только на активности инсулина (без учета других факторов).

I - углеводы (активные углеводы | e-carb в будущем)

J - активный инсулин (от болюсов | от базала)

## Доступ к главному меню AAPS

Для доступа к главному меню AAPS можно использовать следующие опции:

* дважды нажмите на значение ГК
* выбрать значок AAPS в меню приложения часов
* нажмите AAPS (если сконфигурировано в меню)

## Параметры (в часах Wear)

Чтобы получить доступ к настройкам циферблатов, войдите в главное меню AAPS, сдвиньте экран вверх и выберите "Настройки".

Заполненная звездочка соответствует включенному состоянию (**Вкл.**), а незаполненная указывает, что настройка отключена (**Выкл**):

![Параметры вкл./выкл](../images/Watchface_Settings_On_Off.png)

### Параметры спутника AAPS

* ** Вибрировать при болюсе ** (по умолчанию ` Вкл`):
* ** Единицы для принятия действий ** (по умолчанию ` мг/дл `): если ** Вкл** то на основе ` мг/дл `, если ** Выкл ** то на основе ` ммоль/л `. Используется при установке временной цели ТТ с часов.

### Параметры циферблатов

* ** Показать дату ** (значение по умолчанию `Выкл `): примечание: дата доступна не на всех циферблатах
* ** Показывать активный инсулин IOB ** (значение по умолчанию ` Вкл`): (детализация задается в параметрах Wear в AAPS)
* ** Показать активные углеводы COB ** (по умолчанию ` Вкл `): Показывать или не показывать значение COB
* ** Показать дельту ** (по умолчанию ` Вкл `): Показывать или не показывать изменение ГК за последние 5 минут
* ** Показывать среднюю дельту ** (по умолчанию ` Вкл `): Показывать или не показывать среднее изменение ГК за последние 15 минут
* ** Показывать заряд батареи телефона ** (по умолчанию ` Вкл `): Батарея телефона в%. Красная, если ниже 30%.
* ** Показать батарею платформы ** (по умолчанию ` Выкл`): Батарея платформы - это интегральная величина заряда батареи телефона, помпы и трансмиттера (как правило, наименьшее из трех значений)
* ** Показать базальную скорость ** (по умолчанию ` Вкл `): показывать на экране или нет текущую скорость базала (в ед/ч или в%, если TBR)
* ** Показать состояние цикла ** (по умолчанию ` Вкл`): показывает время в мин после недавней работы цикла (стрелки вокруг значения покраснеют, если выше 15 ').
* **Показать ГК** (по умолчанию `Вкл`): показывать или не показывать последнее значение ГК
* **Показать стрелку тренда** (по умолчанию `Вкл`): показывать или не показывать стрелку тренда ГК
* ** Показать Истекшее время ** (по умолчанию ` Вкл `): показать, сколько минут прошло с момента последнего поступления данных.
* **Темный фон ** (по умолчанию `Вкл`): Можно переключиться с темного фона на светлый фон (за исключением циферблатов Cockpit и Steampunk)
* ** Выделять базал ** (по умолчанию ` Выкл `): Улучшить видимость скорости базала и временных базалов
* **Разделитель в цвет** (по умолчанию `Выкл`): для циферблатов AAPS, AAPSv2 и AAPS(Крупный), показывать контрастный фон разделителя (**Выкл.**) или разделитель совпадает с цветом фона (**Вкл.**)
* ** Охват времени графика ** (по умолчанию ` 3 часа `): в подменю можно выбрать максимальное время от 1 часа до 5 часов.

### Настройка интерфейса пользователя

* **Дизайн ввода**: этим параметром вы можете выбрать положение кнопок "+" и "-" при вводе команд для AAPS (TT, Insulin, Carbs...)

![Варианты дизайна ввода](../images/Watchface_InputDesign.png)

### Специфические параметры циферблатов

#### Циферблат Стимпанк

* **Зернистость** (по умолчанию `Средняя`)

![Манометры_Стимпанк](../images/Watchface_Steampunk_Gauge.png)

#### Круглый циферблат

* ** Крупные цифры ** (по умолчанию ` Выкл.`): Увеличить размер текста для улучшения видимости
* ** Кольца хронологии ** (значение по умолчанию ` Выкл.`): Графическое представление хронологии ГК серыми кольцами в зеленом кольце часа
* ** Кольца хронологии неярко ** (значение по умолчанию ` Вкл.`): Графическое представление хронологии ГК более темными серыми кольцами в зеленом кольце часа
* ** Анимация ** (по умолчанию ` Вкл. `): Во включенном состоянии, при поддержке циферблатом и не в режиме энергосбережения, анимация циферблата

### Настройки команд

* ** Помощник в меню ** (по умолчанию ` Вкл. `): Разрешить интерфейс помощника в главном меню для ввода углеводов и подачи болюса с циферблата часов
* ** Первичное заполнение ** (по умолчанию ` Выкл. `): Разрешить действие Prime/Fill с часов
* ** Единичная цель ** (по умолчанию ` Вкл `):
    
    * ` Вкл. `: задается одно значение для временной цели TT
    * ` Выкл. `: задается низкое и высокое значение временной цели TT

* **Процент мастера** (по умолчанию `Выкл.`): разрешить коррекцию болюса с мастера (значение вводится в процентах до уведомления подтверждения)

## Усложнения (дополнительные функции)

* Усложнение *-это термин из традиционной часовой механики, который описывает дополнения основного циферблата в виде еще одного окошка ( с датой, днем недели, фазой луны и т. д.). Операционная система Wear OS 2.0 позволяет употребить эту метафору для описания дополнительных функций, выводимых на экран вроде погоды, уведомлений, счетчиков фитнеса а также добавлять их в любые циферблаты, поддерживающие усложнения.

Приложение AndroidAPS Wear поддерживает усложнения начиная с версии ` 2.6 ` и позволяет использовать любые сторонние циферблаты, поддерживающие усложнения, для отображение данных AAPS (ГК с трендом, IOB, COB и т. д.).

Кроме того, усложнения служат ** ярлыками ** для функций AAPS. Нажав на них вы можете открывать меню и диалогоовые окна, связанные с AAPS (в зависимости от типа усложнения и конфигурации).

![Усложнения_на_Циферблатах](../images/Watchface_Complications_On_Watchfaces.png)

### Типы усложнений (дополнительных функций)

Приложение AAPS Wear обеспечивает только необработанные данные в соответствии с заданными форматами. Решение о том, где и как отображать усложнения, включая их макет, границу, цвет и шрифт, зависит от авторов стороннего циферблата. Из многих доступных типов усложнений Wear AAPS использует:

* ` SHORT TEXT `-Содержит две строки текста, по 7 символов каждый, иногда именуется значением и меткой. Обычно отображаетя внутри круга или небольшой таблетки - один под другим, или сбоку друг от друга. Это очень ограниченное размерами усложнение. AAPS пытается удалить ненужные символы чтобы уместить информацию: округляет значения, удаляет начальные и хвостовые нули из значений и т. д.
* `ДЛИННЫЙ ТЕКСТ` - содержит две строки текста, около 20 знаков в каждой. Обычно выводится внутри прямоугольника или длинной таблетки-один ниже другого. Он используется для более детальной информации в виде текста.
* `ВРЕМЯ В ЦЕЛЕВОМ ДИАПАЗОНЕ`-используется для значений из предопределенного диапазона, например, в процентах. Он содержит иконку, ярлык и обычно отображается в виде круга с достигнутыми значениями.
* ` КРУПНОЕ ИЗОБРАЖЕНИЕ`-пользовательское фоновое изображение, которое можно использовать (при поддержке циферблатом) в качестве фона.

### Настройка усложнений (дополнительных функций)

Чтобы добавить дополнительные функции на циферблат, настройте его долгим нажатием на значок шестеренки внизу. В зависимости от конфигурации нажмите на соответствующее место на экране или войдите в меню настройки циферблата для настройки усложнений. Усложнения AAPS сгруппированы в меню AAPS.

При настройке усложнений на циферблате, Wear OS показывает и фильтрует список усложнений, которые могут быть помещены в выбранное место на экране. Если в списке не удается найти конкретные усложнения, то, вероятно, это связано с отсутствием достаточного места.

### Усложнения, предоставляемые AAPS

AndroidAPS обеспечивает следующие усложнения:

![AAPS_Список_усложнений](../images/Watchface_Complications_List.png)

* ** BR, CoB & IoB ** (` КРАТКИЙ ТЕКСТ `, открывается через * Меню *): Отображает * Скорость базального инсулина* на первой строке, * Активные углеводы* и * Активный инсулин * на второй.
* ** Глюкоза крови ** (` КРАТКИЙ ТЕКСТ`, открывает * Меню *): Отображает * Кровь глюкозы * и * trend * стрелка на первой строке и * возраст измерений * и * дельта * на второй строке.
* **Акт Угл CoB & Акт инс IoB ** (` КРАТКИЙ ТЕКСТ `, открывается через * Меню *): Отображает * Активные углеводы COB * на первой строке и *Активный инсулин* на второй.
* **Акт Угл CoB Подробно ** (` КРАТКИЙ ТЕКСТ `, открывается через * Мастер *): Отображает актуальные * Активные углеводы COB * на первой строке и планируемые (e-Углеводы) на второй.
* ** Значок CoB ** (`КРАТКИЙ ТЕКСТ`, открывает * Wizard *): Отображает значение *Активные углеводы* со статичной иконкой.
* **Подробно** (` ПОЛНЫЙ ТЕКСТ `, открывает * Меню *): Содержит большую часть данных одновременно: * Глюкозу крови * и * тренд *, * дельту ГК* и * время от измерения * в первой строке. На второй строке * Активные углеводы *, *Активный инсулин * and * Базальную скорость *.
* ** Полный статус (перевернут) ** (`ДЛИННЫЙ ТЕКСТ `, открывается через * Меню *): те же данные, что и для стандартного * Полного состояние *, но текст перевернут. Может быть использован в циферблатах, которые игнорируют одну из двух строк `ДЛИННОГО ТЕКСТА`
* ** IOB Подробно ** (` КРАТКИЙ ТЕКСТ `, открывается через *Болюс*): Отображает суммарный * Активный инсулин IOB * на первой строке и разделение * IOB * на * Болюсный* и * Базальный* на второй.
* ** Значок IoB ** (`КРАТКИЙ ТЕКСТ`, открывается через * Болюс *): Отображает величину *Активных углеводов IOB* со статичной иконкой.
* ** Загрузчик/батарея телефона ** (`ДИАПАЗОН ВЕЛИЧИН `, открывает * Состояние *): Показывает процент батареи с телефона с AAPS (загрузчика). Выводится в виде процентной шкалы с значком батареи, отражающий сообщаемые значения. Он обновляется не в режиме реального времени, а наряду с изменением других важных данных AAPS (обычно: каждые ~ 5 минут с новым значением * гликемии *).

Кроме того, существуют три усложнения типа ` КРУПНОЕ ИЗОБРАЖЕНИЕ `: ** Темные обои **, ** Серые обои ** и ** Светлые обои**, являющиеся статическим фоном.

### Параметры, связанные с усложнениями

* **Действия при шлепке по значку усложнений** (по умолчанию ` Default `): определяет, какой диалог открывается при нажатии на усложнение: 
    * * По умолчанию*: действия, связанные с типом усложнения * (см. список выше) *
    * * Меню *: главное меню AAPS
    * *мастер*: болюс мастер - калькулятор болюса
    * * Болюс *: прямой ввод величины болюса
    * * eCarb *: диалоговое окно конфигурации eCarb
    * * Состояние *: подменю состояния
    * * Отсутствует *: Отключает действие по шлепку для усложнений AAPS
* **Unicode в усложнениях** (по умолчанию - `Вкл`): в положении `Вкл`, будут использоваться символы Unicode для таких величин как `Δ` суммарное изменение `⁞` вертикальный точечный разделитель или `⎍` символ базальной скорости. Отрисовка их зависит от шрифта, который специфичен для каждого циферблата. Эта опция позволяет при необходимости отключать символы Unicode (` Выкл `)- если шрифт, используемый циферблатом, их не поддерживает-чтобы избежать ошибок графики.

## Wear OS Tiles

Wear OS Tiles provide easy access to users' information and actions to get things done. The tiles are only available on Android smartwatches running on Wear Os version 2.0 and higher.

Tiles allow you to quickly access actions on the AAPS application without going through the watch face menu. The tiles are optional and can be added and configured by the user.

The tiles are used "next to" any watch face. To access a tile, when enabled, swipe right to left on your watch face to show them.

Please note; that the tiles do not hold the actual state of the AAPS phone app and will only make a request, which has to be confirmed on the watch before it is applied.

## How to add Tiles

Before using the tiles, you have to switch on "Control from Watch" in the "Wear OS" settings of Android APS.

![Wear phone preferences enabled](../images/wear_phone_preferences.jpg)

Depending on your Wear OS version, brand and smartphone there are two ways of enabling the tiles:

1. On your watch, from your watch face; 
    * Swipe right to left till you reach the "+ Add tiles" 
    * Select one of the tiles.
2. On your phone open the companion app for your watch. 
    * For Samsung open "Galaxy Wearable", or for other brands "Wear OS"
    * In the click on the section "Tiles", followed by "+ Add" button
    * Find the AAPS tile you like to add by selecting it. ![Wear phone add tile](../images/wear_companion_app_add_tile.png) The order of the tiles can be changed by dragging and dropping

The content of the tiles can be customized by long-pressing a tile and clicking the "Edit" or "gear icon" button.

### APS(Actions) Tile

The action tile can hold 1 to 4 user-defined action buttons. To configure, long-press the tile, which will show the configuration options. Similar actions are also available through the standard watch menu.

Actions supported in the Action tile can request the AAPS phone app for:

* **Calc**; do a bolus calculation, based on carb input and optional a percentage [1]
* **Insulin**; request insulin delivery by entering the unit of insulin
* **Treatment**; request both insulin delivery and add carbs
* **Carbs**; add (extended) carbs
* **TempT**; set a custom temporary target and duration

![Wear action tile, sample calculator](../images/wear_actions.png)

[1] Via, the Wear OS menu, set the "Calculator Percentage" option to "ON" to show the percentage input in the bolus calculator. The default percentage is based on the phone settings in the"Overview" section ["Deliver this part of the bolus wizard result %"](Config-Builder.html#advanced-settings) When the user does not provide a percentage, the default value from the phone is used. Configure the other parameters for the bolus calculator in the phone app via "Preferences" "Wizard Settings".

### AAPS(Temp Target) Tile

The Temp Target Tile can request a temporary target based on AAPS phone presets. Configure preset time and targets through the phone app setting by going to "Preferences", "Overview", ["Default Temp-Targets"](Config-Builder.html#default-temp-targets) and set the duration and targets for each preset. Configure the visible actions on the tile through the tile settings. Long press the tile to show the configuration options and select 1 to 4 options:

* **Activity**; for sport
* **Hypo**; to raise the target during hypo treatment
* **Eating soon**; to lower the target to raise the insulin on board
* **Manual**; set a custom temporary target and duration
* **Cancel**; to stop the current temporary target

![Wear actions tile edit](../images/wear_tile_tempt_edit.png)

### AAPS(QuickWizard)Tile

The QuickWizard tile can hold 1 to 4 quick wizard action buttons, defined with the phone app[2]. See [QuickWizard](Config-Builder.html#quickwizard-settings). You can set standard meals (carbs and calculation method for the bolus) to be displayed on the tile depending on the time of the day. Ideal for the most common meals/snacks you eat during the day. You can specify if the quick wizard buttons will show on the phone, watch, or both. Please note that the phone can show only one quick wizard button at a time. The quick wizard setup also can specify a custom percentage of the insulin for the bolus. The custom percentage enables you to vary, for example, snack at 120%, slow absorbing breakfast 80% and hypo treatment sugar snack at 0%

![Wear actions tile and phone configuration](../images/quickwizard_watch_phone.png)

[2] Wear OS limits tiles update frequency to only once every 30 seconds. When you notice that the changes on your phone are not reflected on the tile, consider; waiting 30 seconds, using the "Resend all data" button from the Wear OS section of AAPS, or removing the tile and adding it again. To change the order of the QuickWizard buttons dragging an item up or down.

## Always on

Long battery life for Android Wear OS smartwatches is a challenge. Some smartwatches get as much as 30 hours before recharging. The display should be switched off for optimal power saving when not in use. Most watches support the “Always on” display.

Since AAPS version 3, we can use a “Simplify UI” during always-on-mode. This UI only contains the blood glucose, direction, and time. This UI is power-optimized with less frequent updates, showing less information and lightening fewer pixels to save power on OLED displays.

The simplified UI mode is available for the watch-faces: AAPS, AAPS V2, Home Big, Digital Style, Steampunk, and Cockpit. The simplified UI is optional and is configured through the watch face settings. (log press the watch face and click “edit” or the gear icon) Select the configuration “Simplify UI" and set it to “Always on” or “Always on and charging”.

### Night-time mode

While charging, it would be helpful if the display could stay “always-on” and show your blood glucose during the night. However, the standard watch-faces are too bright and have too much information, and the details are hard to read with sleepy eyes. Therefore, we added an option for the watch-face to simplify the UI only during charging when set in the configuration.

The simplified UI mode is available for the watch-faces: AAPS, AAPS V2, Home Big, Digital Style, Steampunk, and Cockpit. The simplified UI is optional and is configured through the watch face settings. (log press the watch face and click “edit” or the gear icon) Select the configuration “Simplify UI" and set it to “During charging” or “Always on and charging”

The Android developer options enable your watch to stay awake during charging. To make the developer options available, see https://developer.android.com/training/wearables/get-started/debugging. Set the “Stay awake when charging” to “on” in the developer options”.

Note: not all displays can handle always-on very well. It can cause screen burn-in, especially on the older OLED displays. The watches will generally dim the display to prevent burn-in; please check your owner’s manual, the manufacturing, or the internet for advice.

![Watchface Nightstand](../images/Watchface_nightstand.jpg)

![Simplified UI](../images/Watchface_simplified_ui.png)

### Performance and battery life tips

Wear OS watches are very power-constrained devices. The size of the watch case limits the capacity of the included battery. Even with recent advancements both on hardware and software side, Wear OS watches still require daily charging.

If an experienced battery span is shorter than a day (from dusk to dawn), here are some tips to troubleshoot the issues.

Main battery-demanding areas are:

* Active display with a backlight on (for LED) or in full intensity mode (for OLED)
* Rendering on screen
* Radio communication over Bluetooth

Since we cannot compromise on communication (we need up-to-date data) and want to have the most recent data rendered, most of the optimizations can be done in *display time* area:

* Stock watchfaces are usually better optimized than custom one, downloaded from the store.
* It is better to use watchfaces that limit the amount of rendered data in inactive / dimmed mode.
* Be aware when mixing other Complications, like third party weather widgets, or other - utilizing data from external sources.
* Start with simpler watchfaces. Add one complication at the time and observe how they affect battery life.
* Try to use **Dark** theme for AAPS watchfaces, and [**Matching divider**](#watchface-settings). On OLED devices it will limit the amount of pixels lit and limit burnout.
* Check what performs better on your watch: AAPS stock watchfaces or other watchfaces with AAPS Complications.
* Observe over a few days, with different activity profiles. Most watches activate the display on glancing, movement and other usage-related triggers.
* Check your global system settings that affect performance: notifications, backlight/active display timeout, when GPS is activated.
* Check [list of tested phones and watches](../Getting-Started/Phones#list-of-tested-phones) and [ask community](../Where-To-Go-For-Help/Connect-with-other-users.md) for other users experiences and reported battery lifetime.
* **We cannot guarantee that data displayed on watchface or complication is up-to-date**. In the end, it is up to Wear OS to decide when to update a watchface or a complication. Even when the AAPS app requests update, the System may decide to postpone or ignore updates to conserve battery. When in doubt and low on battery on watch - always double-check with main AAPS app on phone.

## Troubleshooting the wear app:

* Sometimes it helps to re-sync the apps to the watch as it can be a bit slow to do so itself: Android Wear > Cog icon > Watch name > Resync apps.
* Enable ADB debugging in Developer Options (on watch), connect the watch via USB and start the Wear app once in Android Studio.
* If Complications does not update data - check first if AAPS watchfaces work at all.

### Sony Smartwatch 3

* The Sony Smartwach 3 is one of the most popular watches to be used with AAPS.
* К сожалению, осенью 2020 года Google прекратил поддержку устройств с операционной системой OS 1.5. Это приводит к проблемам при использовании Sony SW3 с AndroidAPS 2.7 и более поздними версиями приложения.
* A possible workaround can be found on this [troubleshooting page](../Usage/SonySW3.rst).

## View Nightscout data

If you are using another looping system and want to *view* your looping detail on an Android Wear watch, or want to watch your child's looping, then you can build/download just the NSClient APK. To do this follow the [build APK instructions](../Installing-AndroidAPS/Building-APK.md) selecting the build variant "NSClientRelease". Есть несколько часовых циферблатов на выбор, в которых показывается средняя дельта СК, активный инсулин IOB, действующий временный базал и профили базы и график мониторинга.

# Смарт-часы Pebble

Pebble users can use the [Urchin watchface](https://github.com/mddub/urchin-cgm) to *view* looping data (if uploaded to Nightscout), but you will not be able to interact with AndroidAPS through the watch. You can choose fields to display such as IOB and currently active temp basal rate and predictions. If open looping you can use [IFTTT](https://ifttt.com/) to create an applet that says if Notification received from AndroidAPS then send either SMS or pushover notification.