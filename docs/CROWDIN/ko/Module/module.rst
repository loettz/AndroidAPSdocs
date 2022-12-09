Component Overview 
**************************************************
AndroidAPS is not just a (self-built) application, it is just one of several modules of your closed loop system. Before deciding for components, it would be a good idea to have a look at the `component setup <../index.html#component-setup>`_, too.
   
.. 이미지::. /images/modules.png
  :alt: Components overview

.. 참고:: 
   ** 중요 안전 수칙 **

   이 문서에 설명된 AndroidAPS 안전 기능의 기초는 시스템 구축에 사용되는 하드웨어의 안전 기능에 기반을 두고 있습니다. 인슐린 자동 주입 시스템을 사용할 시에는 완벽하게 작동한다고 증명하는 테스트와 FDA 또는 CE 승인을 받은 인슐린 펌프과 CGM만을 사용하는 것이 매우 중요합니다. 이러한 구성요소에 대한 하드웨어 또는 소프트웨어의 변형은 예기치 않은 인슐린 투약을 야기하여 사용자에게 상당한 위험을 초래할 수 있습니다. 손상되었거나 변형하였거나 자체 제작된 인슐린 펌프 또는 CGM 수신기를 찾거나 제공하는 받은 경우 Android APS 시스템을 만들 때에는 * 절대 사용하면 안됩니다.*

   또한, 펌프 또는 CGM을 사용할 때에는 원래 공급되는 물품 즉 제조업자에 의해 승인된 삽입기, 캐뉼러 및 인슐린 용기만을 사용하는 것이 매우 중요합니다. 검증이 되지 않고 변형된 물품을 사용하는 경우에는 CGM의 부정확성과 인슐린의 투약 오류가 발생할 수 있습니다. 인슐린은 남용되면 매우 위험하니 물품들을 해킹하여 사용하는 것과 같이 본인의 목숨을 가지고 노는 행위와 같은 행동들은 삼가해주시기 바랍니다.
   
   마지막으로는  계산할 수 없을 정도로 혈당을 낮추기 때문에 SGLT-2 억제제 (글 리플로 진)을 절대 사용하면 안된다.  혈당을 올리기 위해 기저양(basal rate)을 낮추는 시스템과 병행하는 것은 글 리폴로 진으로 인해 매우 위헙합니다. 오히려 혈당이 오르지 않을 수 있으며 인슐린 부족의 위험한 상태까지 올 수 있습니다.

필요한 모듈
==================================================
당뇨병 관리에 적합하게 개발된 개별 복용량 알고리즘
----------------------------------------------------------
이 모듈은 만들거나 구입되는 것이 아니지만 아마도 과소 평과되고 있는 가장 중요하지만 '모듈'일 것 입니다. 알고리즘이 당뇨병을 관리하는데 심각한 실수를 하지 않고 도움이 되기 위해서는 올바른 설정을 알아야 합니다.
다른 모듈이 없는 경우에도 '프로파일'을 직접 확인하고 조정할 수 있습니다. 
대부분의 loop 사용자들은 하루 동안의 호로몬 인슐린 감도 조정에 있어 24 시간 주기의 BR, ISF 및 CR을 사용합니다.

이 프로파일이 포함하는 부분은

* BR (Basal rates)
* ISF (인슐린 민감도) 는 1단위 인슐린당 떨어지는 혈당의 수치를 의미한다
* CR (carb ratio) is grams carbohydrate per one unit insulin
* DIA (인슐린 작용의 지속 시간)

SGLT-2 억제제의 미사용
--------------------------------------------------
글 리플로 진이라고도하는 SGLT2 억제제는 신장에서 포도당의 재 흡수를 억제하여 혈당을 낮추는 약물입니다. 이 억제제는 혈당을 계산할 수 없을 정도로 낮출 수 있기 때문에 절대로 AndroidAPS와 같은 closed loop 시스템과 병행하시면 안됩니다. 케톤산증이나 저혈당의 위험이 아주 큽니다. 혈당을 올리기 위해 기저양(basal rate) 을 낮추는 시스템과 병행하는 것은 글 리폴로 진으로 인해 매우 위헙합니다. 오히려 혈당이 오르지 않을 수 있으며 인슐린 부족의 위험한 상태까지 올 수 있습니다.

핸드폰
--------------------------------------------------
The current version of AndroidAPS requires an Android smartphone with Google Android 8.0 or above. So if you are thinking about a new phone, Android 8.1 is recommended at a minimum but optimally choose Android 9 or 10.
Users are strongly encouraged to keep their build of AndroidAPS up to date for safety reason, however for users unable to use a device with a minimum version of Android 8.0, AndroidAPS version 2.6.1.4, suitable for older Android versions, remains available from the `old repository. <https://github.com/miloskozak/androidaps>`_

사용자들이 테스트된 핸드폰과 스마트워치 목록을 작성하고 있으며<https://docs.google.com/spreadsheets/d/1gZAsN6f0gv6tkgy9EBsYl0BQNhna0RDqA9QGycAqCQc/edit?usp=sharing>`_에서 확인하실 수 있습니다.

시트에 기록되어 있지 않은 핸드폰 혹은 시계를 추가하기 위해서는 <https://docs.google.com/forms/d/e/1FAIpQLScvmuqLTZ7MizuFBoTyVCZXuDb__jnQawEvMYtnnT9RGY6QUw/viewform>`_에서 신청서를 작성해주시기 바랍니다.

시트에 문제가 있는 경우에는 `hardware@androidaps.org <mailto:hardware@androidaps.org>`_으로 메일을 보내주시바랍니다. 핸드폰/시계를 기부하시는 경우에는 테스트가 필요함으로 `donations@androidaps.org <mailto:hardware@androidaps.org>`_으로 메일 보내주시기 바랍니다.

인슐린 펌프
--------------------------------------------------
안드로이드APS는 **현재** 아래의 펌프와 호환됩니다. 

* `Accu-Chek Combo <../Configuration/Accu-Chek-Combo-Pump.html>`_ (additionally needed: Ruffy app, LineageOS or Android 8.1 on your phone)
* `Accu-Chek Insight <../Configuration/Accu-Chek-Insight-Pump.html>`_ 
* `DanaR <../Configuration/DanaR-Insulin-Pump.html>`_ 
* `Dana-i/RS <../Configuration/DanaRS-Insulin-Pump.html>`_
* `some old Medtronic pumps <../Configuration/MedtronicPump.html>`_ from upcoming version 2.4 (`additional communication device <../Module/module.html#additional-communication-device>`__ needed)
* `Omnipod Eros <../Configuration/OmnipodEros.html>`_ (`additional communication device <../Module/module.html#additional-communication-device>`__ needed)
* `Omnipod DASH <../Configuration/OmnipodDASH.html>`_ 

If no additional communication device  is mentioned the communication betweeen insulin pump and AndroidAPS is based on the integrated bluetooth stack of Android without the need of an additional communication device to translate the communnication protocol.

AndroidAPS와 호환될 수 있는 가능성이 있는 **그외 펌프**는 <../Getting-Started/Future-possible-Pump-Drivers.html>`_ 페이지 '미래(가능한) 펌프'에 목록이 나와있습니다.

만약 **개인적으로 구매**를 해야하는 경우에는 다양한 업자의 정보를 '이 스프레드시트<https://drive.google.com/open?id=1CRfmmjA-0h_9nkRViP3J9FyflT9eu-a8HeMrhrKzKz0>`_'에서 찾을 수 있습니다. 만약 본인의 구매경로가 목록에 없는 경우에는 세부사항을 공유 부탁 드리겠습니다.

Additional communication device
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
For old medtronic pumps an additional communication device (besides your phone) is needed to "translate" the radio signal from pump to bluetooth. Make sure to choose the correct version depending on your pump.

* |OrangeLink|  `OrangeLink Website <https://getrileylink.org/product/orangelink>`_    
* |RileyLink| `433MHz RileyLink <https://getrileylink.org/product/rileylink433>`__
* |EmaLink|  `Emalink Website <https://github.com/sks01/EmaLink>`__ - `Contact Info <mailto:getemalink@gmail.com>`__  
* |DiaLink|  DiaLink - `Contact Info <mailto:Boshetyn@ukr.net>`__     
* |LoopLink|  `LoopLink Website <https://www.getlooplink.org/>`__ - `Contact Info <https://jameswedding.substack.com/>`__ - Untested

** 그래서 어떤 펌프가 AndroidAPS의 최적된 펌프일까요?**

콤보, 인사이트와 오래된 메드트로닉 펌프가 견고한 펌프이며 Loop사용이 가능합니다. 콤보는 표준 루어 잠금을 가지고 있기 때문에 많은 주입 세트 유형들을 선택할 수 있는 장점이 있습니다. 그리고 표준 배터리를 사용하기 때문에 편리하게 주요소, 24시간 편의점에서 구매가 가능하며 정말 급한 경우에 호텔 리모컨에서 잠깐 빌리는 것도 가능합니다 ;-).

The advantages of the DanaR/RS and Dana-i vs. 콤보의 장점들은 다음과 같습니다.

- The Dana pumps connect to almost any phone with Android >= 5.1 without the need to flash lineage. If your phone breaks you usually can find easily any phone that works with the Dana pumps as quick replacement... combo와 연동되는 폰을 찾기는 쉽지 않습니다. (Android 8.1 이상의 폰이 좀 더 대중화되면 바뀔 수도 있습니다)
- Initial pairing is simpler with the Dana-i/RS. 그러나 일반적으로 이 작업은 한 번만 수행되므로 다른 펌프로 새 기능을 테스트하려는 경우에만 영향을줍니다.
- 지금까지 콤보는 스크린 파싱을 통해서 작동합니다. 일반적으로 잘 동작하지만 아주 느립니다. Loop를 실행하기 위해서는 백그라운드에서 작업이 수행되는 것이 훨씬 많으므로 이것은 문제가 되지 않습니다. 블루투스 연결이 끊어졌을 때 다시 연결하기까지 더 긴 시간이 필요하기 때문에 주사 주입 중 핸드폰에서 멀어졌을 경우에 재연결이 쉽지 않습니다. 
- The Combo vibrates on the end of TBRs, the DanaR vibrates (or beeps) on SMB. 야간에는 SMB보다는 TBRs를 더 많이 사용할 것입니다.  The Dana-i/RS is configurable that it does neither beep or vibrate.
- Reading the history on the Dana-i/RS in a few seconds with carbs makes it possible to switch phones easily while offline and continue looping as soon a soon as some CGM values are in.
- AndroidAPS와 연동되는 모든 펌프들은 주입 중 방수가 됩니다. Dana 펌프가 배터리와 주사기 주입 시스템이 모두 봉인되어 "방수 보증"이 되는 유일한 펌프입니다. 

혈당정보
--------------------------------------------------
다음은 AndroidAPS와 호환이 가능한 CGM/ FGM의 짧은 개요입니다. For further details, look `here <../Configuration/BG-Source.html>`_. 짧은 힌트: 만약 혈당 정보가 xdrip 앱 혹은 나이트스카운트 웹에서 보여지고 있는 경우에는 AAPS에서 xdrip (혹은 인터넷이 연결된 상태에서 나이트스카웃) 을 혈당 소스로 선택할수 있습니다.

* `Dexcom G6 <../Hardware/DexcomG6.html>`_: BOYDA is recommended as of version 3.0 (see `release notes <../Installing-AndroidAPS/Releasenotes.html#important-hints>`_ for details). xDrip+ must be at least version 2022.01.14 or newer
* `덱스콤 G5 <../Hardware/DexcomG5.html>`_: xdrip앱이나 패치된 덱스콤앱에서 작동합니다.
* 덱스콤 G4 <../Hardware/DexcomG4.html>`_: 이 센서들은 꽤 오래되었지만, xdrip에서 어떻게 사용하는 방법에 대한 설명을 찾아볼 수 있습니다.
* 리브레 2 <../Hardware/Libre2.html>`_: xdrip+(트란스미터가 필요하지 않음)에서 작동하지만 스스로 패치앱을 빌드해야 합니다.
* `리브레 1 <../Hardware/Libre1.html>`_: Bluecon 혹은 MiaoMaio같은 트란스미터(빌드하거나 만들거나)와 xdrip이 필요합니다.
* `에버센스 <../Hardware/Eversense.html>`_: ESEL앱과 패치된 에버센스 앱에서만 작동합니다. (다나RS와 LineageOS에서는 작동을 하지 않지만 다나RS와 안드로이드 혹은 콤보와 LineageOS에서는 잘 작동합니다.)
* `Enlite (MM640G/MM630G) <../Hardware/MM640g.html>`_: quite complicated with a lot of extra stuff


Nightscout
--------------------------------------------------
나이트스카웃은 CGM 데이터 및 안드로이드APS 데이터를 저장하고 표시하며 보고서를 작성할 수 있는 오픈 소스 웹 애플리케이션이다. You can find more information on the `website of the Nightscout project <http://nightscout.github.io/>`_. You can create your own `Nightscout website <https://nightscout.github.io/nightscout/new_user/>`_, use the semi-automated Nightscout setup on `zehn.be <https://ns.10be.de/en/index.html>`_ or host it on your own server (this is for IT experts).

나이트스카웃은 독립적인 다른 모듈입니다. 목표 1을 이행해주시기 바랍니다.

Additional information on how to configure Nightscout for use with AndroidAPS can be found `here <../Installing-AndroidAPS/Nightscout.html>`__.

AAPS -.apk 파일
--------------------------------------------------
기본 구성 요소의 시스템입니다. 앱을 설치하시기 전에는 apk-파일을 직접 빌드하셔야 합니다.(Android앱을 위한 확장파일명) Instructions are  `here <../Installing-AndroidAPS/Building-APK.html>`__.  

선택적 모듈
==================================================
스마트 워치
--------------------------------------------------
안드로이드 웨어 1.x이상의 스마트워치를 선택할 수 있습니다. 대부분의 loop사용자들은 소니 스마트 워치 3 (SWR50) 을 착용합니다. 그 이유는 폰이 범위 밖에 있을 때 덱스컴 G5/G5에서 혈당을 읽어올수 있기 때문입니다. 일부 다른 워치 중에서도 패치 이후에 독립형 수신기로 작동할 수 있습니다. (좀 더 자세한 사항은여기를 `this documentation <https://github.com/NightscoutFoundation/xDrip/wiki/Patching-Android-Wear-devices-for-use-with-the-G5>`_ 참고해주시기 바랍니다.)

사용자들이 테스트된 핸드폰과 시계 목록을 작성하고 있으며<https://docs.google.com/spreadsheets/d/1gZAsN6f0gv6tkgy9EBsYl0BQNhna0RDqA9QGycAqCQc/edit?usp=sharing>`_에서 확인하실 수 있습니다. There are different watchfaces for use with AndroidAPS, which you can find `here <../Configuration/Watchfaces.html>`__.

시트에 기록되어 있지 않은 핸드폰 혹은 시계를 추가하기 위해서는 <https://docs.google.com/forms/d/e/1FAIpQLScvmuqLTZ7MizuFBoTyVCZXuDb__jnQawEvMYtnnT9RGY6QUw/viewform>`_에서 신청서를 작성해주시기 바랍니다.

시트에 문제가 있는 경우에는 `hardware@androidaps.org <mailto:hardware@androidaps.org>`_으로 메일을 보내주시바랍니다. 핸드폰/시계를 기부하시는 경우에는 테스트가 필요함으로 `donations@androidaps.org <mailto:hardware@androidaps.org>`_으로 메일 보내주시기 바랍니다.

xDrip+
--------------------------------------------------
Xdrip앱을 혈당소스로 해야할 필요는 없지만 예시로 사용해볼 수 있습니다. 알림과 혈당이 보여지는 것이 좋습니다. 원하는 만큼의 알림을 설정할 수 있고, 알림의 활성 시간을 구체적으로 설정할 수 있으며 무음모드 또한 무시할 수 있는 기능이 있습니다. Some xDrip+ information can be found `here <../Configuration/xdrip.html>`__. 이 앱에 대한 진행상태가 상당히 빠르기 때문에 문서가 항상 최신으로 업데이트가 되어 있지 않을 수 있음을 유의해주시기 바랍니다.
  
모듈을 대기하는 동안 수행할 작업들
==================================================
Loop를 close하기 위해 모든 모듈을 가져오는데 가끔은 시간이 걸릴 수 있습니다. 하지만 기다리는 동안 이행해야 하는 작업들이 많기 때문에 걱정하지 마시기 바랍니다. It is NECESSARY to check and (where appropriate) adapt basal rates (BR), insulin-carbratio (IC), insulin-sensitivity-factors (ISF) etc. AdroidAPS에 익숙해지기 위해 시스템을 테스트 해보기 위해서는 open loop를 사용해보시는 것이 좋습니다. 이 모드를 사용하면 안드로이드APS가 제공하는 조언들을 수동으로 실행할 수 있습니다.

You can keep on reading through the docs here, get in touch with other loopers online or offline, `read <../Where-To-Go-For-Help/Background-reading.html>`_ documentations or what other loopers write (even if you have to be careful, not everything is correct or good for you to reproduce).

**모두 완료되셨나요?**
AAPS 구성이 모두 완료되었거나(축하드립니다!) 혹은 open loop모드를 사용할 수 있을 정도로 완성 되셨다면 각각 새로운 목표를 이행 및 `하드웨어 <../index.html#component-setup>`_를 설정하시기 전에 `목표 설명 <../Usage/Objectives.html>`_을 먼저 읽어 보시길 추천드립니다.

..
	Image aliases resource for referencing images by name with more positioning flexibility


..
	Hardware and Software Requirements
.. |EmaLink|				image:: ../images/omnipod/EmaLink.png
.. |LoopLink|				image:: ../images/omnipod/LoopLink.png
.. |OrangeLink|			image:: ../images/omnipod/OrangeLink.png		
.. |RileyLink|				image:: ../images/omnipod/RileyLink.png
.. |DiaLink|		      image:: ../images/omnipod/DiaLink.png
