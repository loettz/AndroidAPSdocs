# Profil değiştirme

Genel olarak profillerle ilgili dokümantasyon [Konfigürasyon ayarları - profil](../Configuration/Config-Builder#profile) adresinde bulunabilir.

AAPS'nizi başlatırken ve profilinizi seçerken, sıfır süreli (daha sonra açıklanacak) bir "Profil değiştirme" olayı yapmanız gerekecektir. Bunu yaparak AAPS, profillerin geçmişini izlemeye başlar ve her yeni profil değişikliği, NS'de profilin içeriğini değiştirseniz bile başka bir "Profil değiştirme" gerektirir. Güncellenen profil hemen AAPS'e gönderilir, ancak bu değişiklikleri kullanmaya başlamak için aynı profili tekrar değiştirmeniz gerekir.

Dahili olarak AAPS, profilin başlangıç tarihi ve süresi ile anlık görüntüsünü oluşturur ve seçilen süre içinde kullanır.

* Süre olarak sıfır sonsuz anlamına gelir. Bu profil, yeni "Profil değiştirme"ye kadar geçerlidir.
* x dakika süre, bu profilin x dakika kullanımı anlamına gelir. Bu süreden sonra "Profil değiştirme", önceki geçerli profile geri döner.

Profilinizi "yerel profil" sekmesinde düzenlediyseniz, profili orada etkinleştirebilirsiniz, bu da örtülü bir profil geçişi yapar.

Profil değiştirme yapmak için, AndroidAPS'nin ana ekranında profilinizin adına (aşağıdaki resimde "03/11' e ayarlanmış") uzun basın.

![Profil değişimi yapmak](../images/ProfileSwitch_HowTo.png)

"Profil değiştirme" içinde, daha önce Sirkadiyen Yüzde Profilinin parçası olan iki ek değişiklik seçebilirsiniz:

## Yüzde

* Bu değer, tüm parametrelere aynı yüzdeyi uygular. 
* %130'a ayarlarsanız (yani %30 daha fazla insülin direnciniz var demektir), bazal oranı %30 artıracaktır. Ayrıca İDF ve KİO'yu da buna göre düşürür (bu örnekte 1,3'e bölün).
  
  ![Örnek profil değişim yüzdesi](../images/ProfileSwitchPercentage.png)

* Pompaya gönderilecek ve ardından varsayılan bazal oran olacaktır.

* Döngü algoritması (açık veya kapalı), seçilen yüzde profili üzerinde çalışmaya devam edecektir. Böylece, örneğin hormon döngüsünün farklı aşamaları için ayrı yüzde profilleri oluşturulabilir.

## Zaman kaydırma

![Profil değişim yüzdesi ve zaman kayması](../images/ProfileSwitchTimeShift2.png)

* Zaman kaydırma, her şeyi girilen saat değerine göre günün her saatinde hareket ettirir. 
* Bu nedenle, örneğin, gece vardiyalarında çalışırken, saat değerini ne kadar geç/erken yatacağınıza veya ne kadar erken kalkacağınıza göre değiştirebilirsiniz.
* Profil ayarlarının mevcut saat ayarlarını nasıl değiştireceği her zaman sorulan bir sorudur. Bu süre ne kadarsa x saat kaydırılmalıdır. Bu nedenle, aşağıdaki örnekte açıklanan talimatların izleyin: 
  * Mevcut zaman: 12:00
  * **Pozitif** zaman kaydırma 
    * 2:00 **+10 s** -> 12:00
    * Pozitif zaman kayması nedeniyle normalde 12:00'de kullanılan ayarlar yerine 2:00'den itibaren olan ayarlar kullanılacaktır.
  * **Negatif** zaman kaydırma 
    * 22:00 **-10 s** -> 12:00
    * Negatif zaman kayması nedeniyle normalde 12:00'de kullanılan ayarlar yerine 22:00 (10 pm) ayarları kullanılacaktır.

![Profil değişimi zaman kaydırma talimatları](../images/ProfileSwitch_PlusMinus2.png)

Profilin anlık görüntülerini alma mekanizması, geçmişe ilişkin çok daha kesin hesaplamalara ve profil değişikliklerini izleme olanağına olanak tanır.

## Profil Hatalarında Sorun Giderme

### 'Geçersiz profil' / 'Bazal Profil saatlere göre ayarlanmadı'

![Bazal saatle uyumlu değil](../images/BasalNotAlignedToHours2.png)

* Saati olmayan bazal oranlarınız veya I:C oranlarınız varsa bu hata mesajları görünecektir. (DanaR ve DanaRS pompaları örneğin yarım saatlik değişiklikleri desteklemez.)
  
  ![Örnek profil saatlere göre ayarlanamadı](../images/ProfileNotAlignedToHours.png)

* Hata mesajında gösterilen tarih ve saati hatırlayın / not edin (yukarıdaki ekran görüntüsünde 26/07/2019 17:45).

* Tedaviler sekmesine gidin
* Profil Değiştirmeyi seçin
* Hata mesajından tarih ve saati bulana kadar kaydırın.
* Kaldır işlevini kullanın.
* Bazen yalnızca bir hatalı profil değiştirme yoktur. Bu durumda diğerlerini de kaldırın.
  
  ![Profil değişimini kaldırma](../images/PSRemove.png)

Alternatif olarak, profil değişimini aşağıda açıklandığı gibi doğrudan mLab'den silebilirsiniz.

### 'NS'den alınan profil değişimi ancak profil yerel olarak mevcut değil'

* İstenen profil Nightscout'tan doğru şekilde eşitlenmedi.
* Profil değişimini silmek için yukarıdaki talimatları izleyin

Alternatif olarak, profil değişimini doğrudan mLab'den silebilirsiniz:

* Mlab koleksiyonunuza gidin
* Profil değiştirme'yi tedavilerde arama yapın
* Hatada belirtilen tarih ve saatteki profil değişimini silin. ![mlab](../images/mLabDeletePS.png)

### 'İES 3 saat çok kısa'

* Profilinizdeki insülin etki süreniz, AndroidAPS'in doğru olacağına inanmadığı bir değerde listeleniyorsa, bu hata mesajı görünecektir. 
* [Doğru İES'i seçin](https://www.diabettech.com/insulin/why-we-are-regularly-wrong-in-the-duration-of-insulin-action-dia-times-we-use-and hakkında bilgi edinin -why-it-matters/) ve bunu profilinizde düzenleyin, ardından devam etmek için bir [Profil Değiştirme](../Usage/Profiles) yapın.