Component Overview 
**************************************************
AndroidAPS is not just a (self-built) application, it is just one of several modules of your closed loop system. Before deciding for components, it would be a good idea to have a look at the `component setup <../index.html#component-setup>`_, too.
   
.. imagen:: ../images/modules.png
  :alt: Components overview

.. note:: 
   **AVISO DE SEGURIDAD IMPORTANTE**

   La base de las características de seguridad de AndroidAPS discutidas en esta documentación se basan en las características de seguridad del hardware utilizado para construir su sistema. Es importante que sólo utilice una bomba de insulina y una bomba de insulina y MCG aprobados por la FDA o CE, para cerrar un lazo de dosificación de insulina automatizado. Las modificaciones de hardware o software a estos componentes pueden causar una dosificación inesperada de la insulina, causando un riesgo significativo para el usuario. If you find or get offered broken, modified or self-made insulin pumps or CGM receivers, *do not use* these for creating an AndroidAPS system.

   Además, es igualmente importante utilizar los suministros originales, como los insertadores, las canulas y los recipientes de insulina aprobados por el fabricante para su uso con la bomba o MCG. El uso de suministros no probados o modificados puede provocar inexactitud del MCG y errores de dosificación de la insulina. Insulina es muy peligrosa cuando se malinterpreta-por favor, no juegas con tu vida hackeando con tus suministros.
   
   Por último pero no por ello menos importante, no hay que tomar inhibidores SGLT-2 (gliflozins) ya que reducen incalculablemente los niveles de azúcar en sangre.  La combinación con un sistema que reduce las tasas basales para aumentar la BG es especialmente peligrosa, ya que debido al gliflozin este aumento en BG podría no suceder y podría derivar en un peligroso estado de falta de insulina.

Módulos necesarios
==================================================
Algoritmo de dosificación individual bueno para su tratamiento con diabetes
----------------------------------------------------------
A pesar de que esto no es algo para crear o comprar, este es el "módulo" que probablemente se subestime mas pero es esencial. Cuando dejas que un algoritmo ayude a manejar tu diabetes, necesita saber los ajustes correctos para no cometer errores severos.
Incluso si aún le faltan otros módulos, ya puede verificar y adaptar su 'perfil' en colaboración con su equipo de diabetes. 
La mayoría de los loopers utilizan el BR circadiano, ISF y CR, que adaptan la sensibilidad de la insulina hormonal durante el día.

El perfil incluye

* BR (Tasas basales)
* ISF (factor de sensibilidad a la insulina) es su unidad de glucosa en sangre por unidad de insulina
* CR (carb ratio) is grams carbohydrate per one unit insulin
* DIA (duración de la actuación de la insulina).

Sin uso de inhibidores de SGLT-2
--------------------------------------------------
Los inhibidores de la SGLT-2, también llamados gliflozinas, inhiben la reabsorción de la glucosa en el riñón. A medida que incalculablemente reducen los niveles de azúcar en la sangre, NO DEBE tomarlos mientras use un sistema de circuito cerrado como AndroidAPS! ¡ Habrá un riesgo enorme de cetoacidosis o de una hipoglucemia! La combinación de este medicamento con un sistema que reduce las tasas basales con el fin de aumentar el BG es especialmente peligroso ya que debido a la gliflozina este aumento en BG podría no suceder y puede ocurrir un estado peligroso de falta de insulina.

Teléfono
--------------------------------------------------
The current version of AndroidAPS requires an Android smartphone with Google Android 8.0 or above. So if you are thinking about a new phone, Android 8.1 is recommended at a minimum but optimally choose Android 9 or 10.
Users are strongly encouraged to keep their build of AndroidAPS up to date for safety reason, however for users unable to use a device with a minimum version of Android 8.0, AndroidAPS version 2.6.1.4, suitable for older Android versions, remains available from the `old repository. <https://github.com/miloskozak/androidaps>`_

Users are creating a `list of tested phones and watches <https://docs.google.com/spreadsheets/d/1gZAsN6f0gv6tkgy9EBsYl0BQNhna0RDqA9QGycAqCQc/edit?usp=sharing>`_

Para registrar un teléfono o un reloj que no está ya listado en la hoja de cálculo, por favor rellene la `forma <https://docs.google.com/forms/d/e/1FAIpQLScvmuqLTZ7MizuFBoTyVCZXuDb__jnQawEvMYtnnT9RGY6QUw/viewform>`_.

Cualquier problema con la hoja de cálculo por favor envíe un correo electrónico a `hardware@androidaps.org <mailto:hardware@androidaps.org>`_, cualquier donación de los modelos de teléfono/reloj que aún necesitan pruebas por favor envíe un correo electrónico a `donations@androidaps.org <mailto:hardware@androidaps.org>`_.

Bomba de insulina
--------------------------------------------------
AndroidAPS **actualmente** funciona con 

* `Accu-Chek Combo <../Configuration/Accu-Chek-Combo-Pump.html>`_ (additionally needed: Ruffy app, LineageOS or Android 8.1 on your phone)
* `Accu-Chek Insight <../Configuration/Accu-Chek-Insight-Pump.html>`_ 
* `DanaR <../Configuration/DanaR-Insulin-Pump.html>`_ 
* `Dana-i/RS <../Configuration/DanaRS-Insulin-Pump.html>`_
* `some old Medtronic pumps <../Configuration/MedtronicPump.html>`_ from upcoming version 2.4 (`additional communication device <../Module/module.html#additional-communication-device>`__ needed)
* `Omnipod Eros <../Configuration/OmnipodEros.html>`_ (`additional communication device <../Module/module.html#additional-communication-device>`__ needed)
* `Omnipod DASH <../Configuration/OmnipodDASH.html>`_ 

If no additional communication device  is mentioned the communication betweeen insulin pump and AndroidAPS is based on the integrated bluetooth stack of Android without the need of an additional communication device to translate the communnication protocol.

**Otras bombas** que pueden tener el potencial de trabajar con AndroidAPS se listan en la página `Futuras (posibles) Bombas <../Getting-Started/Future-possible-Pump-Drivers.html>`_.

Si necesitas **comprar privadamente** una bomba entonces puedes encontrar varios distribuidores en `esta hoja de cálculo <https://drive.google.com/open?id=1CRfmmjA-0h_9nkRViP3J9FyflT9eu-a8HeMrhrKzKz0>`_, por favor comparta los detalles suyos si no aparecen en la lista.

Additional communication device
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
For old medtronic pumps an additional communication device (besides your phone) is needed to "translate" the radio signal from pump to bluetooth. Make sure to choose the correct version depending on your pump.

* |OrangeLink|  `OrangeLink Website <https://getrileylink.org/product/orangelink>`_    
* |RileyLink| `433MHz RileyLink <https://getrileylink.org/product/rileylink433>`__
* |EmaLink|  `Emalink Website <https://github.com/sks01/EmaLink>`__ - `Contact Info <mailto:getemalink@gmail.com>`__  
* |DiaLink|  DiaLink - `Contact Info <mailto:Boshetyn@ukr.net>`__     
* |LoopLink|  `LoopLink Website <https://www.getlooplink.org/>`__ - `Contact Info <https://jameswedding.substack.com/>`__ - Untested

**Entonces, ¿cuál es la mejor bomba para lazos cerrados con AndroidAPS?**

El Combo, el Insight y los Medtronics más antiguos son bombas sólidas y loopeables. Además el Combo tiene la ventaja de más tipos de equipos de infusión entre los que escoger teniendo el estándar luer lock. Y la batería es una común que puedes comprar en cualquier gasolinera, tienda de conveniencia 24 horas y si realmente necesitas una, Usted puede robar/tomarlo prestado del mando a distancia en la habitación del hotel ;-).

The advantages of the DanaR/RS and Dana-i vs. la Combo como la bomba de elección, sin embargo, son:

- The Dana pumps connect to almost any phone with Android >= 5.1 without the need to flash lineage. If your phone breaks you usually can find easily any phone that works with the Dana pumps as quick replacement... no así con la Combo. (esto puede cambiar en el futuro cuando Android 8.1 sea más popular)
- Initial pairing is simpler with the Dana-i/RS. Pero esto se realiza normalmente solo una vez, por lo que solo impacta si quieres probar nuevas características con bombas diferentes.
- Hasta ahora Combo funciona con análisis de pantalla. En general funciona bien pero es lento. Para lazo cerrado eso no es crucial puesto que trabaja en segundo plano, sin embargo, usa más tiempo la conexión bluetooth aumentando la probabilidad de fallo de conexión, lo cual no es fácil si te lejas del móvil mientras pones un bolo y cocinas. Aún hay mucho más tiempo que necesitas para estar conectado más tiempo en el que la conexión BT podría romperse, lo cual no es tan fácil si te alejas de tu teléfono mientras se dan bolos y se cocina. 
- The Combo vibrates on the end of TBRs, the DanaR vibrates (or beeps) on SMB. Por la noche, preferirás usar TBR sobre SMB.  The Dana-i/RS is configurable that it does neither beep or vibrate.
- Reading the history on the Dana-i/RS in a few seconds with carbs makes it possible to switch phones easily while offline and continue looping as soon a soon as some CGM values are in.
- Todas las bombas AndroidAPS compatibles son waterproof. Aunque solo la Dana es tiene garantizado waterproof debido a su sellado en el compartimento de la batería y el reservorio. 

Fuentes de datos de glucemia (BG)
--------------------------------------------------
Esta es sólo una breve descripción general de todos los MCGs/FGM compatibles con AndroidAPS. For further details, look `here <../Configuration/BG-Source.html>`_. Solo una breve sugerencia: si puedes visualizar tus datos de glucosa en la aplicación xDrip+ o en el sitio web de Nightscout, puedes elegir xDrip+ (o Nightscout con la conexión web) como fuente BG en AAPS.

* `Dexcom G6 <../Hardware/DexcomG6.html>`_: BOYDA is recommended as of version 3.0 (see `release notes <../Installing-AndroidAPS/Releasenotes.html#important-hints>`_ for details). xDrip+ must be at least version 2022.01.14 or newer
* `Dexcom G5 <../Hardware/DexcomG5.html>`_: Se trabaja con app xDrip+ 'o app parchada Dexcom
* `Dexcom G4 <../Hardware/DexcomG4.html>`_: Estos sensores son bastante antiguos, pero puede encontrar instrucciones sobre cómo usarlos con la aplicación xDrip+
* `Libre 2 <../Hardware/Libre2.html>`_: Funciona con xDrip+ (no se necesita ningún transmisor), pero tienes que construir tu propia aplicación parchada.
* `Libre 1 <../Hardware/Libre1.html>`_: Usted necesita un transmisor como Bluecon o MiaoMiao para (construir o comprar) y app xDrip+
* `Eversense <../Hardware/Eversense.html>`_: funciona sólo en combinación con la app ESEL y la Eversense-App parchada (no funciona con Dana RS y LineageOS, pero DanaRS y Android o Combinado y el Linaje OS funcionan bien)
* `Enlite (MM640G/MM630G) <../Hardware/MM640g.html>`_: quite complicated with a lot of extra stuff


Nightscout
--------------------------------------------------
Nightscout es una aplicación web de código abierto que puede registrar y visualizar los datos de MCG y los datos de AndroidAPS y crea informes. You can find more information on the `website of the Nightscout project <http://nightscout.github.io/>`_. You can create your own `Nightscout website <https://nightscout.github.io/nightscout/new_user/>`_, use the semi-automated Nightscout setup on `zehn.be <https://ns.10be.de/en/index.html>`_ or host it on your own server (this is for IT experts).

Nightscout es independiente de los otros módulos. Lo necesitará para cumplir el Objetivo 1.

Additional information on how to configure Nightscout for use with AndroidAPS can be found `here <../Installing-AndroidAPS/Nightscout.html>`__.

Archivo AAPS-.apk
--------------------------------------------------
El componente básico del sistema. Antes de instalar la aplicación, tienes que construir el archivo apk (que es la extensión de nombre de archivo para una aplicación Android) primero. Instructions are  `here <../Installing-AndroidAPS/Building-APK.html>`__.  

Módulos opcionales
==================================================
Smartwatches (Relojes inteligentes)
--------------------------------------------------
Puede elegir cualquier smartwatch con Android Wear 1.x y superior. La mayoría de los loopers llevan un Sony Smartwatch 3 (SWR50), ya que es el único reloj que puede obtener lecturas de Dexcom G5/G5 cuando el teléfono está fuera de rango. Some other watches can be patched to work as a standalone receiver as well (see `this documentation <https://github.com/NightscoutFoundation/xDrip/wiki/Patching-Android-Wear-devices-for-use-with-the-G5>`_ for more details).

Users are creating a `list of tested phones and watches <https://docs.google.com/spreadsheets/d/1gZAsN6f0gv6tkgy9EBsYl0BQNhna0RDqA9QGycAqCQc/edit?usp=sharing>`_. There are different watchfaces for use with AndroidAPS, which you can find `here <../Configuration/Watchfaces.html>`__.

Para registrar un teléfono o un reloj que no está ya listado en la hoja de cálculo, por favor rellene la `forma <https://docs.google.com/forms/d/e/1FAIpQLScvmuqLTZ7MizuFBoTyVCZXuDb__jnQawEvMYtnnT9RGY6QUw/viewform>`_.

Cualquier problema con la hoja de cálculo por favor envíe un correo electrónico a `hardware@androidaps.org <mailto:hardware@androidaps.org>`_, cualquier donación de los modelos de teléfono/reloj que aún necesitan pruebas por favor envíe un correo electrónico a `donations@androidaps.org <mailto:hardware@androidaps.org>`_.

xDrip+
--------------------------------------------------
Incluso si no necesitas tener la aplicación xDrip + como fuente de BG, todavía puedes usarla para esto. alarmas o una buena muestra de glucosa en sangre. Puede tener el número de alarmas que desee, especificar la hora en la que la alarma debe estar activa, se puede alterar temporalmente la modalidad silenciosa, etc. Some xDrip+ information can be found `here <../Configuration/xdrip.html>`__. Por favor, tenga en cuenta que las documentaciones de esta aplicación no siempre están al día, ya que su progreso es bastante rápido.
  
Qué hacer mientras se espera a los módulos
==================================================
A veces se tarda un tiempo en obtener todos los módulos para cerrar el lazo. Pero no te preocupes, hay un montón de cosas que puedes hacer mientras esperas. It is NECESSARY to check and (where appropriate) adapt basal rates (BR), insulin-carbratio (IC), insulin-sensitivity-factors (ISF) etc. Y tal vez un lazo abierto puede ser una buena forma de probar el sistema y familiarizarse con AndroidAPS. Usando este modo, AndroidAPS le da consejos de tratamiento que puede ejecutar manualmente.

You can keep on reading through the docs here, get in touch with other loopers online or offline, `read <../Where-To-Go-For-Help/Background-reading.html>`_ documentations or what other loopers write (even if you have to be careful, not everything is correct or good for you to reproduce).

**Hecho?**
Si tiene todos los componentes de AAPS juntos (congratulaciones) o al menos lo suficiente para iniciarse en el modo de bucle abierto, primero debe leer la descripción de `objetivo <../Usage/Objectives.html>`_ antes de cada nuevo objetivo y configurar el `hardware <../index.html#component-setup>`_.

..
	Image aliases resource for referencing images by name with more positioning flexibility


..
	Hardware and Software Requirements
.. |EmaLink|				image:: ../images/omnipod/EmaLink.png
.. |LoopLink|				image:: ../images/omnipod/LoopLink.png
.. |OrangeLink|			image:: ../images/omnipod/OrangeLink.png		
.. |RileyLink|				image:: ../images/omnipod/RileyLink.png
.. |DiaLink|		      image:: ../images/omnipod/DiaLink.png
