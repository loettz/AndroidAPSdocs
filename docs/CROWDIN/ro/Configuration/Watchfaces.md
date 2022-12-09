# AAPS pe ceasuri cu Wear OS

Puteţi instala aplicaţia AndroidAPS pe ceasuri **cu Wear OS**. Versiunea de ceas a AAPS vă permite să:

* **afișează datele pe ceas**: utilizând [fețe de ceas personalizate](#aaps-watchfaces) sau pe fețele de ceas standard utilizând [auxiliare](#complications)
* **controlează AAPS pe telefon**: la bolusare, la stabilirea unei ținte temporare etc.

### Înainte de a cumpăra ceas...

* Unele caracteristici precum *auxiliare* necesita Wear OS versiunea 2.0 sau mai nouă pentru a funcționa
* Google redenumit de la *Android Wear 1.x* la *Wear OS* de la versiunea 2.x, asa ca atunci cand spune *Android Wear* ar putea indica versiuni de sistem mai vechi de 1.x
* Dacă descrierea ceasului indică doar compatibilitatea cu *Android* și *iOS* - **nu** înseamnă că rulează pe *Wear OS* - poate fi la fel de bine un alt fel de sistem de operare al unui producător necunoscut **care nu este compatibil cu AAPS!**
* Verifică [lista de telefoane si ceasuri testate ](../Getting-Started/Phones#list-of-tested-phones) ți [cere comunității](../Where-To-Go-For-Help/Connect-with-other-users.md) daca ești nesigur că ceasul tău va fi compatibil

### Construirea versiunii Wear OS pentru AAPS

The Wear OS App of AAPS has been seperated from the AAPS build for the Android mobile. Therefore you have to generate a second signed APK. Select as module "AndroidAPS.wear" and as build variant "fullRelease" and a second apk file for the Wear OS clock is generated when [building the APK](../Installing-AndroidAPS/Building-APK.md) (or "pumpcontrolRelease" which will allow you to just remote control the pump without looping).

From March 2021 you need to sideload AAPS onto the watch, it is no longer accessible via the watch's Google Play Store. You can sideload using [Wear Installer](https://youtu.be/8HsfWPTFGQI) which you will need to install on both your watch and phone. The Wear Installer app can be downloaded from the Google Play Store. The linked video from Malcolm Bryant the developer of Wear Installer gives you detailed instructions to a) download the apk to your mobile b) setup the Android Debugger on the wear c) use Wear Installer on mobile and wear to sideload the AAPS wear app to the mobile. Once you have selected AndroidAPS as your app to upload wear version onto the watch you will be able to use watchfaces and complications and the AAPS controls.

### Configurare pe telefon

În cadrul AndroidAPS, în ConfigBuilder aveţi nevoie de [activare aplicație Wear](../Configuration/Config-Builder#wear).

## Controlează AAPS de pe Ceas

AndroidAPS este proiectat să poată fi *controlat* de ceasuri Android Wear. Dacă doriţi să bolusați etc. de pe ceas, în "Setari Wear", trebuie să activaţi "Control de pe Ceas".

Următoarele funcţii pot fi activate de la ceas:

* setarea unei ţinte temporare
* folosirea unui calculatorul pentru bolus (variabilele de calcul pot fi definite in [setări](../Configuration/Config-Builder#wear) pe telefon)
* administrare eCarbs
* administrare un bolus (insulină + carbohidrați)
* setări ceas
* stare 
    * verificați starea pompei pe ecranul acesteia
    * verificare starea loop
    * verificare şi modificare profil, CPP (Profil Circadian procentual = shift time + procentaj)
    * arată TDD (Doza totală zilnică = bolus + bazală pe zi)

## Fețe de ceas AAPS

Există mai multe fețe de ceas din care puteți alege, fețe ce afișează deviația medie, IOB, RBT-ul activ și profilurile bazale + graficul citirilor de glicemie.

Asigurați-vă că notificările din AndroidAPS nu sunt blocate pe ceas. Confirmarea acțiunii (e.f. bolus, țintă temporară) este solicitată printr-o notificare, ce va trebui aruncată de pe ecran și bifată.

Pentru a ajunge mai rapid la meniul AAPS, apăsați de două ori rapid pe valoarea glicemiei. Cu o apăsare dublă pe curba glicemiei, puteți schimba scala timpului..

## Fețe de ceas disponibile

![Fețe de ceas disponibile](../images/Watchface_Types.png)

### Față nouă de ceas pentru AndroidAPS 2,8

![Față de ceas format Digital](../images/Watchface_DigitalStyle.png)

* Culoarea, liniile şi cadranul sunt configurabile în meniul de setare pe semnul de cog al meniului de selectare al cadranului ceasului.

## Fețe de ceas AAPSv2 - Legendă

![Legendă față de ceas AndroidAPSv2](../images/Watchface_Legend.png)

A - timp de la ultima activare a loop

B - Citire CGM

C - minute de la ultima citire CGM

D - modificare în comparaţie cu ultima citire a CGM (în mmol sau mg/dl)

E - variația medie a citirilor CGM din ultimele 15 minute

F - bateria telefonului

G - rata bazală (indicată în U/h în timpul ratei standard şi în % în timpul TBR)

H-BGI (interacţiunea glicemiei) -> gradul în care glicemia "ar trebui" să fie în creştere sau scădere în funcţie doar de activitatea insulinei.

I - carbohidrati (carbohidrati la bord | e-carbohidrati in viitor)

J - insulină la bord (de la bolus | de la bazală)

## Accesarea meniului principal al AAPS

Pentru a accesa meniul principal al AAPS, puteţi utiliza următoarele opţiuni:

* apăsaţi de două ori pe valoarea glicemiei
* selectați pictograma AAPS în meniul de aplicaţii al ceasului
* apăsaţi pe auxiliare AAPS (dacă este configurat pentru meniu)

## Setări (în ceas)

Pentru a accesa setările pentru fețe de ceas, intrați in meniul principal AAPS, glisaţi in sus şi selectaţi "Settings".

Pictograma cu steaua umplută este pentru starea activată (**On**), iar pictograma cu stea goală indică faptul că setarea este dezactivată (**Off**):

![Setări pornit/oprit](../images/Watchface_Settings_On_Off.png)

### Parametrii AAPS insoțitor

* **Vibrare la Bolus** (implicit `On`):
* **Unități pentru Acțiuni** (implicit `mg/dl`): dacă este **On** unitatea de măsură este `mg/dl`, dacă este **Off** unitatea de măsură folosită este `mmol/l`. Folosit la setarea unui TT din ceas.

### Setări fețe de ceas

* **Arată date** (implicit `Off`): notă, datele nu sunt disponibile pe toate fețele ceas
* **Arată IOB** (implicit `On`): Afișează sau nu valoarea IOB (setarea pentru valoarea detaliată este în parametrii de wear din AAPS)
* **Arată COB** (implicit `On`): Afișează sau nu valoarea COB
* **Arată Variația** (implicit `On`): Afișează sau nu variația glicemiei din ultimele 5 minute
* **Afișează Variația medie** (implicit `On`): Afişează sau nu variaţia medie glicemiei din ultimele 15 minute
* **Afișare bateria Telefonului** (implicit `On`): Baterie telefon în %. Roşu dacă e sub 30%.
* **Afișare baterie dispozitiv** (implicit `Off`): Bateria dispozitivului este o sinteză a baterilor din telefon, pompă și senzor (în general, cea mai mică dintre cele 3 valori)
* **Afişează Rata Bazală** (implicit `On`): Afişare sau nu a ratei bazale curente (în U/h sau în % dacă TBR)
* **Arată starea Loop** (implicit `On`): arată câte minute au trecut de la ultima buclă activă (săgeţile din jurul valorii devin roşii dacă este peste 15').
* **Afişează Glicemia** (implicit `On`): Afişează sau nu ultima valoare a glicemiei
* **Arată Săgeata de Direcție** (implicit `On`): Afișează sau nu săgeata tendinței glicemiei
* **Arată Vechime** (implicit `On`): arată numărul de minute de la ultima citire.
* **Fundal** (implicit `On`): Puteţi comuta de pe fundal negru pe fundal alb (cu excepţia fețelor de ceas Cockpit şi Steampunk)
* **Evidențiere Bazale** (implicit `Off`): Îmbunătățirea vizibilității ratei bazalelor și bazalelor temporare
* **Potrivire separator** (implicit `Off`): Pentru AAPS, AAPSv2 şi AAPS (Mare) față de ceas, arată contrastul fundalului pentru separator (**Off**) sau potrivește separatorul cu culoarea fundalului (**On**)
* **Grafic Interval de Timp** (implicit `3 ore`): puteți selecta în sub-meniu intervalul maxim de timp al graficului între 1 oră și 5 ore.

### Setări Interfaţă Utilizator

* **Design de intrare**: cu acest parametru, poți selecta poziția butoanelor "+" și "-" atunci când introduci comenzi pentru AAPS (TT, Insulină, Carbs...)

![Opţiuni pentru design de intrare](../images/Watchface_InputDesign.png)

### Parametri specifici pentru fețe de ceas

#### Fața de ceas Steampunk

* **Granularitate Variație** (implicit `Mediu`)

![Indicator_Steampunk](../images/Watchface_Steampunk_Gauge.png)

#### Cadran FațaCeas

* **Marime caractere** (implicit `Off`): Crește dimensiunea textului pentru a îmbunătăți vizibilitatea
* **Istoric cu cercuri** (implicit`Off`): Vizualizare grafică istoric glicemie cu inele gri în interiorul inelului verde al orei
* **Istoric cu cerc luminos** (implicit `On`): cercul de istoric este mai discret cu un gri mai inchis
* **Animații** (implicit `On`): Când este activat și suportat de ceas și nu e în modul rezolutie mica pentru economisirea energiei, cadranul ceasului va fi animat

### Setări comenzi

* **Asistent în Meniu** (implicit `On`): Permite în meniul principal să se introducă Carbohidrați și să se seteze Bolus din ceas
* **Meniu amorsare** (implicit`Off`): Permite Amorsare/Umplere de pe ceas
* **Țintă unică** (implicit `On`):
    
    * `On`: ai setat o singură valoare pentru TT
    * `Off`: ai setat ținta inferioara și superioară pentru TT

* **Asistent Procentaj** (implicit `Off`): Se permite corecţia bolus din asistent (valoarea introdusă în procente înainte de notificarea de confirmare)

## Auxiliare

*Auxiliare* este un termen de la producătorii tradiționali de ceasuri, care descrie adăugarea pe fața principală a ceasului - o altă fereastră sau cadran mai mic (cu data, ziua săptămânii, faza lunii, etc.). Wear OS 2.0 permite diverșilor furnizori de date, cum ar fi vremea, notificările, contoarele de fitness şi altele - să fie adăugate la orice feţe de ceas care suporta auxiliare.

Aplicaţia AAPS Wear OS suportă auxiliare de la versiunea `2.6`şi permite oricărei fețe de ceas al unei terţe părţi care suportă auxiliare să fie configurate pentru a afişa datele asociate cu AAPS (glicemia și tendinţa, IOB, COB, etc.).

Auxiliarele servesc de asemenea ca **scurtătură** la funcții AAPS. Apăsând pe ele puteți deschide meniurile și dialogurile legate de AAPS (în funcție de tipul de auxiliare și configurație).

![Auxiliare_Pe_Ceasuri](../images/Watchface_Complications_On_Watchfaces.png)

### Tipuri de Auxiliare

Aplicaţia AAPS Wear OS furnizează numai date brute, conform formatelor predefinite. Depinde de dezvoltatorul feței de ceas să decidă unde și cum să afișeze auxiliarele, inclusiv modul de prezentare, margine, culoare și tip caracter. Din multele tipuri disponibile de auxiliare ale Wear OS, AAPS utilizează:

* `TEXT SCURT ` -Conţine două linii de text, 7 caractere fiecare, denumite uneori valoare şi etichetă. De obicei, redat în interiorul unui cadran sau a unei mici buline - unul sub altul, sau lateral unul de altul. Este un auxiliar foarte limitat ca spaţiu. AAPS încearcă să înlăture caracterele care nu sunt necesare pentru a se potrivi: prin rotunjirea valorilor, înlăturarea zerourilor de la începutul şi sfârşitul valorilor, etc.
* `TEXT LUNG` - Conține două linii de text, aproximativ 20 de caractere fiecare. De obicei, redat în interiorul unui dreptunghi sau unui cadran lung - unul sub altul. Este folosit pentru mai multe detalii şi stări.
* `VALOARE INTERVAL` -Folosit pentru valori din intervalul predefinit, ca un procentaj. Conţine pictogramă, etichetă şi este de obicei redată ca un cadran de progres.
* `IMAGINE MARE` -Imagine personalizată care poate fi folosita (atunci cand este acceptată de ceas) ca fundal.

### Configurare Auxiliare

Pentru a adăuga auxiliare la faţa de ceas, configuraţi-o printr-o apăsare lungă şi făcând clic pe roata dințata de mai jos. În funcție de modul specific în care se configurează o față de ceas - fie apăsați pe înlocuitori fie intrați in meniul de configurare a fețelor de ceas pentru auxiliare. Auxiliarele AAPS sunt grupate în meniul AAPS.

Când configurați auxiliare pe ceas, Wear OS va prezenta și va filtra lista de auxiliare care se pot potrivi în locul selectat pe ceas. Dacă anumite auxiliare nu pot fi găsite în listă, este probabil din cauza faptului că acel tip nu poate fi utilizat pentru locul respectiv.

### Auxiliare furnizate de AAPS

AndroidAPS oferă următoarele auxiliare:

![AAPS_Listă_Auxiliare](../images/Watchface_Complications_List.png)

* **BR, CoB & IoB** (`TEXT SCURT`, deschide *Menu*): Afişează *Rata Bazală* pe prima linie şi *Carbohidrați la Bord* şi *Insulină la Bord* pe linia a doua.
* **Glicemia** (`TEXT SCURT`, deschide *Menu*): Afișează valoarea *Glicemiei* și săgeata de *tendință* pe prima linie iar pe linia a doua *măsurători durată* și *Variația Glicemiei*.
* **CoB & IoB** (`TEXT SCURT`, deschide*Menu*): Afișează *Carbohidrați la Bord* în prima linie și *Insulină la Bord* în a doua linie.
* **CoB Detaliat** (`TEXT SCURT`, deschide *Wizard*): Afișează în prima linie *Carbohidrații la Bord* activi și în a doua linie Carbohidrații planificați (viitori, eCarbs).
* **Iconiță CoB** (`TEXT SCURT`, deschide *Wizard*): Afișează o iconiță statică cu valoarea *Carbohidrați la Bord*.
* **Stare Completă** (`TEXT LUNG`, deschide *Menu*): Arată majoritatea datelor deodată: valoarea *glicemiei* și săgeata *tendinței*, *variația glicemiei* și *vechimea măsurătorii* pe prima linie. Pe linia a doua linie *Carbohidrați la Bord*, *Insulină la Bord* și *Rata bazală*.
* **Stare completă (inversat)** (`TEXT LUNG`, deschide *Menu*): Aceleaşi date ca și la *Stare completă*, dar liniile sunt inversate între ele. Poate fi folosit în fețele de ceas care ignoră una din cele două linii în `TEXT LUNG`
* **IoB Detaliat** (`TEXT SCURT`, deschide *Bolus*): Afișează *Insulina la Bord* totală în prima linie și *IoB* defalcat pentru *Bolus* și *Bazală* în linia a doua.
* **Iconiță IoB** (`TEXT SCURT`, deschide *Bolus*): Afișează valoarea *Insulinei la Bord* printr-o iconiță statică.
* **Baterie Telefon/Uploader** (`VALOARE INTERVAL`, deschide *Status*): Afișează în procente bateria telefonului cu AAPS (uploader), așa cum este raportat de AAPS. Prezentat ca un indicator în procente cu o iconiță de baterie care afișează valoarea raportată. Este posibil să nu se actualizeze în timp real, doar atunci când apar alte modificări importante de date AAPS (de obicei: la fiecare ~ 5 minute cu noua valoare a *glicemiei*).

În plus, există trei auxiliare `IMAGINE MARE` tip: **fundal întunecat**, **fundal gri** și **fundal deschis**, afișează imaginea de fundal statică AAPS.

### Setări legate de Auxiliare

* **Acţiuni pentru auxiliare** (implicit `Default`): Decide ce dialog se deschide când utilizatorul apasă pe auxiliare: 
    * *Default*: actiune specifică tipului de auxiliar *(vezi lista de mai sus)*
    * *Menu*: Meniu principal AAPS
    * *Wizard*: asistent bolusare - calculator pentru bolus
    * *Bolus*: introducere directă a valorii bolus
    * *eCarb*: dialog de configurare eCarb
    * *Status*: submeniul de stare
    * *None*: Dezactivează acțiunea de atingere a auxiliarelor AAPS
* **Unicode in auxiliare** (implicit `On`): Când e `On`, auxiliarele vor folosi caractere Unicode pentru simboluri ca `Δ` Delta, `⁞` separator vertical din puncte sau `⎍` simbol pentru Rata Bazală. Afișarea lor depinde de tipul caracterului, și asta poate fi foarte specific. Această opţiune permite comutarea simbolurilor Unicode `Off` dacă este necesar - când caracterul utilizat de către faţa de ceas personalizată nu suportă acele simboluri - pentru a evita erorile grafice.

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
* Unfortunately Google dropped support for wear OS 1.5 devices in fall 2020. This leads to problems when using Sony SW3 with AndroidAPS 2.7 and above.
* A possible workaround can be found on this [troubleshooting page](../Usage/SonySW3.rst).

## View Nightscout data

If you are using another looping system and want to *view* your looping detail on an Android Wear watch, or want to watch your child's looping, then you can build/download just the NSClient APK. To do this follow the [build APK instructions](../Installing-AndroidAPS/Building-APK.md) selecting the build variant "NSClientRelease". Există mai multe fețe de ceas din care puteți alege, fețe ce afișează deviația medie, IOB, RBT-ul activ și profilurile bazale + graficul citirilor de glicemie.

# Pebble

Pebble users can use the [Urchin watchface](https://github.com/mddub/urchin-cgm) to *view* looping data (if uploaded to Nightscout), but you will not be able to interact with AndroidAPS through the watch. You can choose fields to display such as IOB and currently active temp basal rate and predictions. If open looping you can use [IFTTT](https://ifttt.com/) to create an applet that says if Notification received from AndroidAPS then send either SMS or pushover notification.