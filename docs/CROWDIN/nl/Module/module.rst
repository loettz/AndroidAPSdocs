Component Overview 
**************************************************
AndroidAPS is not just a (self-built) application, it is just one of several modules of your closed loop system. Voordat je kiest welke onderdelen je wilt gebruiken, is het goed om eens te kijken naar de `Onderdelen instellen <../index.html#onderdelen-instellen>`_ sectie.
   
.. image:: ../images/modules.png
  :alt: Components overview

.. note:: 
   **VOOR JE EIGEN VEILIGHEID**

   De veiligheidsfuncties die in AndroidAPS zitten, maken gebruik van ingebouwde veiligheidsmaatregelen van de hardware componenten waaruit jouw systeem bestaat. Het is daarom van cruciaal belang dat je alleen een volledig functionerende FDA of CE goedgekeurde insulinepomp en CGM gebruikt voor het bouwen van jouw eigen closed loop. Gebruik alleen insulinepompen en CGMs die in deze handleiding beschreven staan, waarvoor de AndroidAPS software is geschreven en getest. Hardware of software wijzigingen aan deze componenten kunnen voor onverwachte uitkomsten zorgen (denk aan het ongewenst afgeven van insuline), waardoor de gebruiker een aanzienlijk risico loopt. Als je een insulinepomp of CGM-ontvanger vindt/koopt/krijgt die een defect heeft, zelfgemaakt is, of op welke manier dan ook veranderd is, GEBRUIK DEZE NIET voor het maken van een AndroidAPS-systeem.

   Daarnaast is het belangrijk om alleen originele verbruiksartikelen te gebruiken, zoals infuussets, inschiethulpen en reservoirs die door de fabrikant zijn goedgekeurd voor gebruik met jouw pomp of CGM. Door het gebruik van niet-originele, niet-geteste verbruiksmaterialen kunnen CGM metingen onnauwkeurig worden en/of fouten optreden in de insulinedosering. Insuline is zeer gevaarlijk wanneer het verkeerd wordt gedoseerd - speel alstublieft niet met je leven door jouw hulpmiddelen aan te passen.
   
   Tensotte een belangrijke opmerking: je mag géén SGLT-2 inhibitors (glifozines) gebruiken wanneer je loopt. Omdat deze medicatie ook de bloedsuiker verlaagt.  Deze medicatie in combinatie met een systeem dat de basale insuline verlaagt om BG te verhogen is bijzonder gevaarlijk, omdat deze stijging in BG mogelijk niet zal gebeuren en daardoor een gevaarlijk gebrek aan insuline kan ontstaan.

Benodigde onderdelen
==================================================
Correcte insulineprofiel instellingen voor jouw diabetesbehandeling
----------------------------------------------------------
Dit is misschien niet het eerste waar je aan denkt bij een 'onderdeel'. Toch is het waarschijnlijk het meest belangrijke onderdeel van jouw closed loop. Wanneer je de behandeling van jouw diabetes overlaat aan een algoritme, dan is het cruciaal dat je dit algoritme de juiste instellingen geeft. Anders kunnen er grote fouten optreden in de beslissingen die het algoritme neemt.
Wanneer je de andere onderdelen van jouw closed loop nog niet bij elkaar hebt, dan kun je de tussenliggende tijd benutten om, samen met jouw behandelaars, jouw instellingen te perfectioneren. 
De meeste loopers maken gebruik van basaalstanden, ISF en KH ratios die zijn aangepast aan een variërende insulinegevoeligheid gedurende de dag (zgn. circadiaans ritme).

Het profiel bevat

* Basaalstanden
* ISF (Insuline Sensitivity Factor). De insuline gevoeligheidsfactor is hoeveel jouw bloedglucosespiegel daalt per eenheid insuline
* CR (carb ratio) is grams carbohydrate per one unit insulin
* DIA (Duur van Insuline Activiteit)

Geen gebruik van SGLT-2-remmers
--------------------------------------------------
SGLT-2 remmers, ook wel glifozines genoemd, remmen de herabsorptie van glucose in de nieren. Omdat ze de bloedsuikerspiegel verlagen met een voor het algoritme niet-berekenbare hoeveelheid, mag je ze ABSOLUUT NIET gebruiken wanneer je een closed loop systeem zoals AndroidAPS gebruikt! Dit vanwege het zeer grote risico op ketoacidose en/of ernstige hypo's. Deze medicatie in combinatie met een systeem dat de basale insuline verlaagt om BG te verhogen is bijzonder gevaarlijk, omdat er een gevaarlijk gebrek aan insuline kan ontstaan.

Telefoon
--------------------------------------------------
Voor de huidige versie van AndroidAPS is een Android smartphone nodig met Google Android 8.0 of hoger. Dus als je denkt over een nieuwe telefoon, dan raden we aan om op zijn minst voor Android 8.1 te gaan maar liever Android 9 of 10.
Gebruikers worden met klem geadviseerd om hun AndroidAPS om veiligheidsredenen up-to-date te houden. Maar voor gebruikers die geen telefoon hebben met minimaal Android 8, is versie 2.6.1.4 van AndroidAPS nog beschikbaar vanuit de 'oude' repository, deze is geschikt voor telefoons met Android 7 of lager je vindt hem `hier <https://github.com/miloskozak/androidaps>`_

Gebruikers houden een `lijst van geteste telefoons en smartwatches <https://docs.google.com/spreadsheets/d/1gZAsN6f0gv6tkgy9EBsYl0BQNhna0RDqA9QGycAqCQc/edit?usp=sharing>`_ bij.

Om een telefoon of horloge toe te voegen aan de lijst kun je dit `formulier <https://docs.google.com/forms/d/e/1FAIpQLScvmuqLTZ7MizuFBoTyVCZXuDb__jnQawEvMYtnnT9RGY6QUw/viewform>`_ invullen.

Bij eventuele problemen met de spreadsheet stuur een e-mail naar `hardware@androidaps.org <mailto:hardware@androidaps.org>`_, voor eventuele donaties van telefoon/smartwatch modellen die nog getest moeten worden kun je een e-mail sturen naar `donations@androidaps.org <mailto:hardware@androidaps.org>`_.

Insulinepomp
--------------------------------------------------
AndroidAPS werkt momenteel met 

* `Accu-Chek Combo <../Configuration/Accu-Chek-Combo-Pump.html>`_ (additionally needed: Ruffy app, LineageOS or Android 8.1 on your phone)
* `Accu-Chek Insight <../Configuration/Accu-Chek-Insight-Pump.html>`_ 
* `DanaR <../Configuration/DanaR-Insulin-Pump.html>`_ 
* `Dana-i/RS <../Configuration/DanaRS-Insulin-Pump.html>`_
* `some old Medtronic pumps <../Configuration/MedtronicPump.html>`_ from upcoming version 2.4 (`additional communication device <../Module/module.html#additional-communication-device>`__ needed)
* `Omnipod Eros <../Configuration/OmnipodEros.html>`_ (`additional communication device <../Module/module.html#additional-communication-device>`__ needed)
* `Omnipod DASH <../Configuration/OmnipodDASH.html>`_ 

If no additional communication device  is mentioned the communication betweeen insulin pump and AndroidAPS is based on the integrated bluetooth stack of Android without the need of an additional communication device to translate the communnication protocol.

**Andere pompen** die mogelijk in de toekomst geschikt zullen zijn vind je op de `Mogelijk toekomstige insulinepompen <../Getting-Started/Future-possible-Pump-Drivers.html>`_ pagina.

Als je een pomp **particulier wilt kopen** dan is hier een overzicht van verschillende distributeurs in `deze spreadsheet <https://drive.google.com/open?id=1CRfmmjA-0h_9nkRViP3J9FyflT9eu-a8HeMrhrKzKz0>`_, eventuele aanvullingen op deze lijst zijn welkom.

Extra communicatie apparaatje (Link)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
For old medtronic pumps an additional communication device (besides your phone) is needed to "translate" the radio signal from pump to bluetooth. Zorg ervoor dat je de juiste versie kiest, afhankelijk van jouw pomp.

* |OrangeLink|  `OrangeLink Website <https://getrileylink.org/product/orangelink>`_    
* |RileyLink| `433MHz RileyLink <https://getrileylink.org/product/rileylink433>`__
* |EmaLink|  `Emalink Website <https://github.com/sks01/EmaLink>`__ - `Contact Info <mailto:getemalink@gmail.com>`__  
* |DiaLink|  DiaLink - `Contact Info <mailto:Boshetyn@ukr.net>`__     
* |LoopLink|  `LoopLink Website <https://www.getlooplink.org/>`__ - `Contact Info <https://jameswedding.substack.com/>`__ - Untested

**Dus wat is de beste pomp om te loopen met AndroidAPS?**

De Combo, de Insight en de oudere Medtronics zijn goede pompen en loopbaar. De Combo heeft ook als voordeel dat er veel meer keuze is in infuussets, aangezien hij een standaard luer-lock aansluiting heeft. Er gaat een normale batterij in, die je bij een tankstation of supermarkt kunt kopen en mocht het echt nodig zijn, kunt je hem altijd nog stelen/lenen van de afstandsbediening in een hotelkamer ;-).

The advantages of the DanaR/RS and Dana-i vs. de Combo zijn echter:

- The Dana pumps connect to almost any phone with Android >= 5.1 without the need to flash lineage. If your phone breaks you usually can find easily any phone that works with the Dana pumps as quick replacement... Met de Combo is dat minder makkelijk. (Dit kan veranderen in de toekomst, als Android 8.1 populairder wordt)
- Initial pairing is simpler with the Dana-i/RS. Maar dit doe je meestal eenmalig.
- Tot nu toe werkt de Combo door 'screen parsing': doorsturen wat er op het scherm staat. In het algemeen werkt dit prima, maar het is traag. Bij het loopen merk je dit vaak niet eens omdat alles op de achtergrond werkt. Wel kost het meer tijd, dus je moet langer een Bluetooth verbinding houden tussen telefoon en pomp. Dat kan lastig zijn, bijvoorbeeld wanneer je alvast bolust tijdens het koken, en je al wegloopt terwijl de bolus nog wordt gegeven. 
- The Combo vibrates on the end of TBRs, the DanaR vibrates (or beeps) on SMB. Waarschijnlijk gebruikt de loop 's nachts vaker een TBR dan SMB.  The Dana-i/RS is configurable that it does neither beep or vibrate.
- Reading the history on the Dana-i/RS in a few seconds with carbs makes it possible to switch phones easily while offline and continue looping as soon a soon as some CGM values are in.
- Alle pompen waar AndroidAPS op werkt, zijn waterdicht wanneer ze nieuw zijn. Alleen de Dana pompen zijn ook gegarandeerd waterdicht tijdens gebruik, doordat de ruimtes voor batterij en reservoir volledig afgesealed zijn. 

BG bron
--------------------------------------------------
Dit is slechts een kort overzicht van alle compatibele CGMs/FGM met AndroidAPS. For further details, look `here <../Configuration/BG-Source.html>`_. Even kort samengevat: als je jouw glucosewaardes kunt laten weergeven in de xDrip+ app of op jouw Nightscout site, dan kun je in AAPS als "BG bron" kiezen voor xDrip+ (of voor Nightscout, maar dan heb je wel continu een internetverbinding nodig).

* `Dexcom G6 <../Hardware/DexcomG6.html>`_: BOYDA is recommended as of version 3.0 (see `release notes <../Installing-AndroidAPS/Releasenotes.html#important-hints>`_ for details). xDrip+ must be at least version 2022.01.14 or newer
* `Dexcom G5 <../Hardware/DexcomG5.html>`_: Werkt met xDrip+ app of aangepaste Dexcom app
* `Dexcom G4 <../Hardware/DexcomG4.html>`_: Deze sensors zijn vrij oud, maar er zijn instructies te vinden om hem met de xDrip+ app te gebruiken
* `Libre 2 <../Hardware/Libre2.html>`_: Werkt met xDrip+ (geen zender nodig), maar je moet je eigen gepatchte app bouwen.
* `Libre 1 <../Hardware/Libre1.html>`_: Je hebt een zender nodig, zoals Bubble, Bluecon of MiaoMiao en de xDrip+ app.
* `Eversense <../Hardware/Eversense.html>`_: Werkt tot nu toe alleen in combinatie met ESEL app en een gepatchte Eversense-App (werkt niet met Dana RS en LineageOS, maar DanaRS en Android of Combo en Lineage werken prima)
* ` Enlite (MM640G/MM630G) <../Hardware/MM640g.html>`_: vrij ingewikkeld met veel extra dingen!


Nightscout
--------------------------------------------------
Nightscout is een open source web-applicatie die jouw CGM-gegevens en AndroidAPS gegevens kan opslaan, weergeven en rapporten kan maken. Meer informatie vind je op de `website van het Nightscout project <http://nightscout.github.io/>`_. Je kunt je eigen Nightscout website `maken <https://nightscout.github.io/nightscout/new_user/>`_, gebruik de semi-geautomatiseerde Nightscout setup op `zehn.be <https://ns.10be.de/en/index.html>`_ of host het op jouw eigen server (dit laatste is voor IT experts).

Nightscout werkt onafhankelijk van de andere onderdelen. Je hebt het nodig om voorbij Doel 1 te komen.

Meer informatie over het instellen van Nightscout voor gebruik met AndroidAPS vind je `hier <../Installing-AndroidAPS/Nightscout.html>`__.

AAPS-.apk-bestand
--------------------------------------------------
De basiscomponent van het systeem. Voordat je de app installeert, moet je eerst het apk-bestand (dat is de bestandsnaam extensie voor een Android app) maken. Instructies staan `hier <../Installing-AndroidAPS/Building-APK.html>`__.  

Optionele onderdelen
==================================================
Smartwatch
--------------------------------------------------
Elke smartwatch met Android Wear 1.x en hoger is geschikt. Sommige loopers dragen een Sony Smartwatch 3 (SWR50) omdat het het enige horloge is dat elke 5 minuten een Dexcom G5/G6 ontvangt zonder de telefoon in de buurt te hebben. Dit wordt "stand alone" ontvanger genoemd. Sommige andere horloges kunnen worden gepatcht om te werken als een stand alone ontvanger (zie `deze documentatie <https://github.com/NightscoutFoundation/xDrip/wiki/Patching-Android-Wear-devices-for-use-with-the-G5>`_ voor meer details).

Gebruikers houden een `lijst van geteste telefoons en smartwatches <https://docs.google.com/spreadsheets/d/1gZAsN6f0gv6tkgy9EBsYl0BQNhna0RDqA9QGycAqCQc/edit?usp=sharing>`_ bij. Er zijn verschillende wijzerplaten voor gebruik met AndroidAPS, deze vind je `hier <../Configuration/Watchfaces.html>`__.

Om een telefoon of horloge toe te voegen aan de lijst kun je dit `formulier <https://docs.google.com/forms/d/e/1FAIpQLScvmuqLTZ7MizuFBoTyVCZXuDb__jnQawEvMYtnnT9RGY6QUw/viewform>`_ invullen.

Bij eventuele problemen met de spreadsheet stuur een e-mail naar `hardware@androidaps.org <mailto:hardware@androidaps.org>`_, voor eventuele donaties van telefoon/smartwatch modellen die nog getest moeten worden kun je een e-mail sturen naar `donations@androidaps.org <mailto:hardware@androidaps.org>`_.

xDrip+
--------------------------------------------------
Zelfs als je de xDrip+ App niet als BG bron nodig hebt, kun je hem nog steeds gebruiken voor bijvoorbeeld alarmen of om jouw bloedglucose te laten weergeven op een smartwatch. Je kunt in xDrip+ zoveel alarmen aanmaken als je wilt, en zelf tijdvakken specificeren wanneer een alarm actief moet zijn, of het alarm toch moet afgaan wanneer de telefoon in 'stille modus' staat, etc. Meer informatie over xDrip+ vind je `hier <../Configuration/xdrip.html>`__. Houd er rekening mee dat de documentatie van deze app niet altijd up-to-date is, aangezien hij zeer regelmatig wordt geupdatet.
  
Wat te doen tijdens het wachten op onderdelen
==================================================
Het duurt soms een tijdje voordat je alle onderdelen voor het maken van een closed loop bij elkaar hebt. Maar geen zorgen, er zijn een heleboel dingen die je kunt doen tijdens het wachten. It is NECESSARY to check and (where appropriate) adapt basal rates (BR), insulin-carbratio (IC), insulin-sensitivity-factors (ISF) etc. AndroidAPS gebruiken in open loop modus kan een goede manier zijn om jouw profielinstellingen te testen en vertrouwd te raken met het syteem. In de open loop modus geeft AndroidAPS behandelingsadviezen die je handmatig moet doorvoeren.

Verder kun je deze documentatie doorlezen, je kunt online of offline contact opnemen met andere loopers. Lees wat `achtergrondinformatie <../Where-To-Go-For-Help/Background-reading.html>`_ of bekijk welke vragen andere loopers stellen in de verschillende Facebook groepen (let hierbij wel op de kwaliteit van andermans suggesties, niet alles wat je leest is verstandig om blindelings na te doen).

** Klaar? **
Als je jouw AAPS onderdelen bij elkaar hebt (gefeliciteerd!) of ten minste genoeg om te beginnen in de open loop modus, lees dan eerst de `Doelen <../Usage/Objectives.html>`_ door en stel je `hardware <../index.html#component-setup>`_ in.

..
	Image aliases resource for referencing images by name with more positioning flexibility


..
	Benodigde hardware en software
.. |EmaLink|				image:: ../images/omnipod/EmaLink.png
.. |LoopLink|				image:: ../images/omnipod/LoopLink.png
.. |OrangeLink|			image:: ../images/omnipod/OrangeLink.png		
.. |RileyLink|				image:: ../images/omnipod/RileyLink.png
.. |DiaLink|		      image:: ../images/omnipod/DiaLink.png
