가장 중요한 안전 유의사항
**************************************************

** 인공 췌장을 구축하기로 결정하면, 보안과 안전에 대해 생각하고 사용자의 모든 적용이 가져오는 영향을 이해하는 것이 항상 중요합니다 **

포괄적인 정보
==================================================

* AndroidAPS은 당뇨병을 관리함에 있어서 도움을 주는 도구일 뿐이며, 이는 설치한 뒤 잊고 있어도 되는 완전한 자동화 시스템이 아닙니다.
* AndroidAPS가 절대로 실수하지 않을 것이라고 생각하지 마십시오. This device is taking control of your insulin delivery: Watch it all the time, understand how it works, and learn how to interpret its actions.
* 폰이 한 번 연결되면 펌프에 무엇이든지 지시할 수 있다는 사실을 기억하십시오. AndroidAPS 전용으로 폰을 사용하고, 아이가 사용하는 경우에는 AndroidAPS와 필수적인 통신만을 사용합니다. 사용자의 시스템을 방해할 수 있는 트로이 목마, 바이러스 또는 로봇과 같은 악성 소프트웨어를 가져올 수 있는 불필요한 앱이나 게임(!!!)을 설치하지 마십시오.
* 구글이나 휴대기기 제조사에서 제공하는 모든보안패치를 업데이트하시기 바랍니다.
* closed loop 시스템을 사용하는 것으로 관리 방법을 변경할 때는 당뇨병 관련 습관들을 변경해야 할 수도 있습니다. 예를 들어, AndroidAPS가 인슐린 주입을 미리 감소시켜줌에 따라 저혈당 간식이 적게 필요했다고 일부 사용자들은 보고하였습니다.  
   
SMS 통신기
==================================================

* AndroidAPS는 문자 메세지를 통해 아이의 폰을 원격으로 조정할 수 있게 해줍니다. SMS 통신기를 활성화 했다면, 원격 명령어를 사용하기 위해 설정된 폰(부모폰)을 도난 맞을 수도 있다는 사실에 항상 유념하셔야 합니다. 따라서 최소한 PIN 코드 이상의 보안으로 폰을 보호하십시오.
* Bolus 또는 프로파일 변경 등의 원격 명령들이 수행된 경우, AndroidAPS 역시 문자 메시지로 알려줄 것입니다. 수신 폰 중 하나가 도난 당할 경우를 대비하여, 적어도 2개 이상의 다른 폰에 확인 문자 메시지가 전송되도록 설정하는 것을 권장합니다.

AndroidAPS can also be used by blind people
===========================================

On Android devices TalkBack is part of the operating system. It is a program for screen orientation via voice output. With TalkBack you can operate your smartphone as well as AndroidAPS blind.

We users create the AndroidAPS app ourselves with Android Studio. Many use Microsoft Windows for this purpose, where there is the Screenreader analogous to TalkBack. Since Android Studio is a Java application, the "Java Access Bridge" component must be enabled in the Control Panel. Otherwise, the screen reader of the PC will not speak in Android Studio.

To do this, please proceed as follows:  

* Press WINDOWSTASTE and enter "Control Panel" in the search field, open with Enter. It opens: "All Control Panel Items". 
* Press the letter C to get to "Center for Ease of Use", open with Enter.  
* Then open "Use computer without a screen" with Enter. 
* There, at the bottom, you will find the checkbox "Enable Java Access Bridge", select it. 
* Done, just close the window! The screen reader should work now.

.. 참고:: 
   ** 중요 안전 수칙 **

   이 문서에 설명된 AndroidAPS 안전 기능의 기초는 시스템 구축에 사용되는 하드웨어의 안전 기능에 기반을 두고 있습니다. 자동화된 인슐린 주입 시스템의 closing loop을 사용할 경우, 완벽하게 작동하는 FDA 또는 CE 승인을 받은 검증된 인슐린 펌프와 CGM만 사용하는 것이 매우 중요합니다. 이러한 구성 요소에 대한 하드웨어 또는 소프트웨어의 변형은 예기치 않은 인슐린 주입을 야기하여 사용자에게 큰 위험을 초래할 수 있습니다. 손상 또는 변형되었거나 자체 제작된 인슐린 펌프 또는 CGM 수신기를 찾거나 제공하는 받은 경우, 이들은 AndroidAPS 시스템 구축을 위해 *절대 사용하면 안됩니다.*

   또한, 펌프 또는 CGM을 사용할 때에는 원래 공급되는 물품 즉 제조업자에 의해 승인된 삽입기, 캐뉼러 및 인슐린 용기만을 사용하는 것이 매우 중요합니다. 검증이 되지 않았거나 조작된 제품을 사용하는 경우에는 CGM이 부정확하거나 인슐린 주입 오류가 발생할 수 있습니다. 인슐린이 잘못 주입되면 매우 위험하오니 제품을 해킹하여 사용자의 생명으로 장난치지 않도록 하십시오.

   마지막으로 또 하나 중요한 것은 SGLT-2 억제제(글리플로진)가 계산할 수 없을 정도로 혈당 수치를 낮추기 때문에 절대 사용하면 안된다는 것입니다.  혈당을 올리기 위해 basal 양을 낮추는 시스템과 함께 사용 시, 글리플로진으로 인해 혈당이 오르지 않을 것이며 인슐린 부족의 위험한 상태까지 갈 수 있기 때문에 매우 위험합니다.
