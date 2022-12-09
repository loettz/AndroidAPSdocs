# Medtronic Pompaları

AAPS sürücüsü, G ile biten (530G, 600 serisi [630G, 640G, 670G], 700 serisi [770G, 780G] vb.) tüm modellerde ve daha yeni modellerde çalışmaz.

Aşağıdaki modeli ve yazılımı belirtilen pompa kombinasyonları uyumludur:

- 512/712 (herhangi bir pompa yazılımı sürümü)
- 515/715 (herhangi bir pompa yazılımı sürümü)
- 522/722 (herhangi bir pompa yazılımı sürümü)
- 523/723 (pompa yazılımı 2.4A veya altı)
- 554/754 AB sürümü (pompa yazılımı 2.6A veya altı)
- 554/754 Kanada sürümü (pompa yazılımı 2.7A veya altı)

[OpenAPS dokümantasyonu](https://openaps.readthedocs.io/en/latest/docs/Gear%20Up/pump.html#how-to-check-pump-firmware-check-for-absence-of-pc-connect) veya [Döngü Dokümantasyonunda](https://loopkit.github.io/loopdocs/build/step3/#medtronic-pump-firmware) pompalardaki yazılım versiyonunu nasıl öğreneceğinizi bulabilirsiniz.

## Donanım ve yazılım gereksinimleri

- **Telefon:** Medtronic sürücüsü, Bluetooth bağlantılarını destekleyen herhangi bir android telefonla çalışmalıdır. **ÖNEMLİ: Telefon üreticilerinin Bluetooth uygulamaları değişebileceği için her bir telefon modelinin davranış biçimi farklı olabilir. Örneğin, bazı telefonlar Bluetooth'u etkinleştirmeyi/devre dışı bırakmayı farklı şekilde ele alacaktır. Bu, AndroidAPS'in Rileylink cihazına yeniden bağlanması gerektiğinde kullanıcı deneyimini etkileyebilir.**
- **RileyLink Uyumlu Cihaz:** Android telefonlar, iletişimi yönetmek için ayrı bir cihaz olmadan Medtronic pompalarıyla iletişim kuramaz. Bu cihaz, Bluetooth aracılığıyla telefonunuzla ve uyumlu bir radyo bağlantısı aracılığıyla pompanızla bağlantı kuracaktır. Bu tür ilk cihaza Rileylink adı verildi, ancak artık ek işlevsellik sunabilen başka seçenekler de mevcuttur.
    
    - Rileylink'i [getrileylink.org](https://getrileylink.org/product/rileylink916) adresinde bulabilirsiniz.
    - Orangelink, [getrileylink.org](https://getrileylink.org/product/orangelink) adresinde
    - Emalink (birkaç model opsiyonuyla) [github.com](https://github.com/sks01/EmaLink) adresinde
    - Gnarl (Kendin yap araçlarına ihtiyacınız olacak) detaylar için [github.com](https://github.com/ecc1/gnarl) adresine başvurabilirsiniz.

Çeşitli Rileylink uyumlu cihazlar için karşılaştırma tablosunu [getrileylink.org](https://getrileylink.org/rileylink- Compatible-hardware-comparison-chart) adresinde bulabilirsiniz.

## Pompa Konfigürasyonu

AndroidAPS'in uzaktan komut gönderebilmesi için pompada aşağıdaki ayarların yapılandırılması gerekir. Medtronic 715'te değişikliği yapmak için gerekli adımlar, her ayar için parantez içinde gösterilmiştir. Adımlar, pompa tipine ve/veya pompa yazılım sürümüne göre değişebilir.

- **Pompada uzak modu etkinleştir** Pompada Act'ye basın ve Yardımcı Programlar (Utilities) -> Uzak Seçenekler'e (Remote Options) gidin, Açık'ı (ON) seçin ve sonraki ekranda Kimlik Ekle'yi (Add ID) yapın ve 1111111 gibi herhangi bir rastgele kimlik ekleyin. Pompanın uzaktan iletişim beklemesi için Remote ID listesinde en az bir ID olmalıdır.
- **Maks Bazal Ayarla** (Pompada Act'e basın ve Bazal'a gidin ve ardından Maks Bazal Oranı seçin) Örnek olarak, bu değeri maksimum standart bazal oranınızın dört katına ayarlamak %400 Geçici Bazal Oranına izin verir. Pompa tarafından izin verilen maksimum değer saatte 34,9 ünitedir.
- **Maks Bolus Ayarla** (Pompada sırasıyla Act ve Bolus'a basın ve ardından Maks Bolus'u seçin) Buradaki değer pompanın kabul edeceği en büyük bolustur. Pompa tarafından izin verilen maksimum değer 25'tir.
- **Profili Standart olarak ayarlayın**. (Pompada Act'ye basın ve Bazal'a gidin ve ardından bazal modelinizi seçin) AndroidAPS telefonunuzdaki farklı profilleri yöneteceğinden pompanın yalnızca bir profile ihtiyacı olacaktır. Başka bazal modeli gerekli değildir.
- **Geçici Bazal Oranı türünü ayarlayın** (Pompada ACT'ye basın ve Bazal'a ve ardından Geçici Bazal Türü'ne gidin). Mutlak'ı (Absolute) seçin (Yüzdeyi değil).

## Telefonun/AndroidAPS'in Medtronic Yapılandırması

- **RileyLink uyumlu cihazı telefonunuzdaki Bluetooth menüsüyle eşleştirmeyin.** Telefonunuzdaki Bluetooth menüsü aracılığıyla eşleştirme, aşağıdaki talimatları uygularken AndroidAPS'in Rileylink Uyumlu cihazınızı görmesini engeller. 
- Telefonunuzda otomatik ekran döndürmeyi devre dışı bırakın. Belirli cihazlarda otomatik ekran döndürme, Bluetooth oturumlarının yeniden başlamasına neden olur ve bu da Medtronic pompanız için sorunlara neden olabilir. 
- AndroidAPS'de Medtronic pompanızı yapılandırmanın iki yolu vardır: 

1. Yeni bir kurulumun parçası olarak kurulum sihirbazını kullanma
2. Konfigürasyon Ayarları'nda pompa seçimi sekmesinde Medtronic seçeneğinin yanındaki dişli simgesini tıklayarak

Medtronic pompanızı kurulum sihirbazıyla yapılandırırken, Bluetooth sorunları nedeniyle kurulumu tamamlamanız engellenebilir (örn. pompaya başarılı bir şekilde bağlanamayabilirsiniz.) Böyle bir durumda, yapılandırmayı tamamlamak ve 2. seçeneği kullanarak daha fazla sorun giderebilmek için ilk önce sanal pompa seçeneğini seçmelisiniz.

![Medtronic Ayarları](../images/Medtronic01a.png)

AndroidAPS'i medtronic pompanızla çalışacak şekilde ayarlarken aşağıdaki öğeleri ayarlamanız gerekir: (yukarıdaki resme bakın)

- **Pompa Seri Numarası**: Pompanızın arkasında yer alır ve SN ile başlar. Alfabetik karakterler olmadan yalnızca görünen 6 rakamı girmelisiniz (ör. 123456).
- **Pompa Tipi**: Kullandığınız pompa modeli (ör. 522). 
- **Pompa Frekansı**: Pompanızın ilk dağıtıldığı yere bağlı olarak iki seçenek vardır. Hangi seçeneği seçeceğinizden emin değilseniz lütfen [SSS](../Configuration/MedtronicPump#faq)'i kontrol edin): 
    - ABD & Kanada için (NA-CA) kullanılan frekans 916 Mhz
    - Dünya çapında (WW) kullanılan frekans 868 Mhz'dir.
- **Pompadaki Maks Bazal (Ü/s)**: Bunun, pompanızda ayarlanan değerle eşleşmesi gerekir (yukarıdaki pompa konfigürasyonuna bakın). Bu ayar AndroidAPS'in bazal oranınız aracılığıyla ne kadar insülin iletebileceğini belirleyeceğinden dikkatli bir şekilde seçilmelidir. Bu değer maksimum geçici bazal oranını etkin bir şekilde ayarlayacaktır. Örnek olarak, bu değeri maksimum standart bazal oranınızın dört katına ayarlamak %400 Geçici Bazal Oranına izin verir. Pompa tarafından izin verilen maksimum değer saatte 34,9 ünitedir.
- **Pompadaki Maks Bolus (Ü)** (bir saat içinde): Bunun, pompanızda ayarlanan değerle eşleşmesi gerekir (yukarıdaki pompa konfigürasyonuna bakın). Bu ayar AndroidAPS'in bir seferde ne kadar bolus insülin iletebileceğini belirlediğinden dikkatlice düşünülmelidir.
- **Bolus göndermeden önceki bekleme süresi (sn)**: Bolus verildikten sonra, komut gerçekten pompaya gönderilmeden önce geçen saniye sayısı. Bu süre, bir bolus komutunun yanlışlıkla gönderilmesi durumunda kullanıcının bolusu iptal etmesine olanak tanır. AndroidAPS üzerinden başlatılan bir bolusu iptal etmek mümkün değildir. Halihazırda başlamış bir bolusu iptal etmenin tek yolu, pompayı manuel olarak askıya almak ve ardından devam ettirmektir.
- **Medtronic Kodlama**: Medtronic kodlamasının gerçekleştirilip gerçekleştirilmediğini belirler. Donanım kodlamasının seçilmesi (Rileylink uyumlu cihaz tarafından gerçekleştirilir) tercih edilir çünkü bu daha az veri gönderilmesine neden olur. Yazılım kodlamasının seçilmesi (AndroidAPS tarafından gerçekleştirilir), sık bağlantı kesilmesi durumunda yardımcı olabilir. Rileylink cihazlarında yazılım sürümü 0.x ise bu ayar yok sayılır.
- **Pil Türü (Güç Görünümü)**: Kalan pil gücü seviyesini doğru bir şekilde belirlemek için kullanımda olan AAA pil tipini seçmelisiniz. Basit görünüm dışında bir değer seçildiğinde, AndroidAPS hesaplanan pil yüzdesi seviyesini ve voltajı görüntüler. Aşağıdaki seçenekler mevcuttur:
    
    - Seçilmedi (Basit görünüm)
    - Alkali (Genişletilmiş görünüm)
    - Lityum (Genişletilmiş görünüm)
    - NiZn (Genişletilmiş görünüm)
    - NiMH (Genişletilmiş görünüm)
- **Bolus/Tedavilerde Hata Ayıklama**: Gereksinimlere göre Açın veya Kapatın.

- **RileyLink Yapılandırması**: Bu seçenek, Rileylink uyumlu cihazınızı bulmanızı ve eşleştirmenizi sağlar. Bu yapılandırma yardımıyla, yakındaki Rileylink uyumlu cihazları ve sinyal gücünü görüp seçebilirsiniz.
- **Taramayı Kullan** Rileylink Uyumlu cihazlarınızla bağlantı kurmadan önce Bluetooth taramasını etkinleştirir. Bu seçenek cihazla bağlantınızın güvenilirliğini artırabilir.
- **OrangeLink/EmaLink/DiaLink tarafından bildirilen pil düzeyini göster** Bu özellik yalnızca EmaLink veya OrangeLink gibi daha yeni cihazlarda desteklenir. Değerler, AnroidAPS'deki Medtronic sekmesinde gösterilecektir. 
- **Sık kullanılan Geçici Bazalları ayarla** Varsayılan olarak Medtronic pompaları, geçici bir bazal oranın etkin olduğu saatte bip sesi çıkarır. Bu seçeneğin etkinleştirilmesi, bip sesini bastırmak için saat değişiminde geçici bir bazal kesintiye uğratılarak duyulan bip sayısının azaltılmasına yardımcı olabilir.

## MEDTRONIC (MDT) Sekmesi

![MDT Sekmesi](../images/Medtronic02.png) AndroidAPS, bir Medtronic pompası kullanacak şekilde yapılandırıldığında, ekranın üst kısmında bir MDT sekmesi gösterilecektir. Bu sekme, Medtronic'e özgü bazı eylemlerle birlikte mevcut pompa durumu bilgilerini görüntüler.

- **RileyLink Durumu**: Telefonunuz ve Rileylink uyumlu cihaz arasındaki bağlantının mevcut durumu. Bu satır her zaman "Bağlı" olarak görünmelidir. Diğer herhangi bir durum, kullanıcı müdahalesini gerektirebilir. 
- **RileyLink Pili**: EmaLink veya OrangeLink cihazınızın mevcut pil seviyesi. Medtronic Pompa Yapılandırma menüsünde "OrangeLink/EmaLink/DiaLink cihazı tarafından bildirilen pil seviyesini göster" seçimine bağlıdır.
- **Pompa Durumu**: Pompa bağlantısının mevcut durumu. Pompa sürekli bağlı olmayacağından, burada genellikle uyku simgesi görünecektir. "Uyanıyor" da dahil olmak üzere AndroidAPS bir komut iletmeye çalışırken "Saat Alınıyor", "GBO Ayarla" gibi diğer olası pompa komutlarını da burada bulabilirsiniz. 
- **Pil**: Medtronic Pompa Yapılandırma menüsünde Pil Tipi (Güç Görünümü) için seçilen değere göre pil durumunu gösterir. 
- **Son bağlantı**: Son başarılı pompa bağlantısının ne kadar önce gerçekleştiği.
- **Son Bolus**: Son başarılı bolusun ne kadar süre önce verildiği.
- **Temel Bazal Oranı**: Aktif Profilinizde şu anda pompada çalışan temel bazal orandır.
- **Geçici Bazal**: Şu anda saatte 0 ünite de olabilen teslim edilen geçici bazal.
- **Rezervuar**: Rezervuarda ne kadar insülin olduğu gösterir.(saatte bir güncellenir).
- **Hatalar**: Sorun varsa hata dizesi (çoğunlukla yapılandırmada hata olup olmadığını gösterir).

Ekranın altında üç buton vardır:

- **Yenile**: Pompanın mevcut durumunu yenilemek içindir. Bu buton komple veri yenilediğinden (geçmişi al, zamanı al/ayarla, profil al, pil durumunu al, vb.) yalnızca bağlantı uzun bir süre boyunca kopmuşsa kullanılmalıdır.
- **Pompa Geçmişi**: Pompa geçmişini gösterir ([aşağıya](../Configuration/MedtronicPump#pump-history) bakın)
- **RL Stats**: RL Durumunu Gösterir ([aşağıya](../Configuration/MedtronicPump#rl-status-rileylink-status) bakın)

## Pompa geçmişi

![Pompa Geçmişi İletişim Kutusu](../images/Medtronic03.png)

Pompa geçmişi her 5 dakikada bir alınır ve yerel olarak saklanır. Yalnızca 24 saatlik geçmiş değerler depolanır. Gerektiğinde pompa davranışını görmenin bir yoludur. Depolanan öğeler yalnızca AndroidAPS ile ilgili olanlardır ve ilgisi olmayan bir yapılandırma işlevi içermez.

## RL Durumu (RileyLink Durumu)

![RileyLink Durumu - Ayarları](../images/Medtronic04.png) ![RileyLink Durumu - Geçmişi](../images/Medtronic05.png)

RL Durumu iletişim kutusunda iki sekme bulunur:

- **Ayarlar**: RileyLink ile ilgili ayarları gösterir: Yapılandırılmış Adres, Bağlı Cihaz, Bağlantı Durumu, Bağlantı Hatası ve RileyLink yazılımı sürümleri. Cihaz Tipi her zaman Medtronic Pompa, Model kullandığınız model, Seri numarası konfigüre edilmiş seri numarası, Pompa Frekansı hangi frekansı kullandığınızı gösterir. Son Frekans en son kullanılan frekanstır.
- **Geçmiş**: İletişim geçmişini gösterir. RileyLink satırları, RileyLink için durum değişikliklerini, Medtronic satırları ise pompaya hangi komutların gönderildiğini gösterir.

## Eylemler

Medtronic sürücüsü kullanıldığında, Eylemler Sekmesine iki buton eklenir:

- **Uyan ve Ayarla** - AndroidAPS'in pompanıza uzun bir süre boyunca bağlanmaması durumunda (5 dakikada bir bağlanmalıdır) bu buton ile zorlayabilirsiniz. Bu buton pompanız tarafından kullanılan tüm olası radyo frekanslarını arayarak pompanızla iletişim kurmaya çalışacaktır. Başarılı bir bağlantı yapılması durumunda, başarılı frekans varsayılan olarak ayarlanacaktır. 
- **RileyLink Yapılandırmasını Sıfırla** - RileyLink uyumlu cihazınızı sıfırlarsanız, cihazın yeniden yapılandırılabilmesi için bu eylemi kullanmanız gerekebilir (frekans ayarı, frekans tipi ayarı, yapılandırılmış kodlama).

## Önemli notlar

### OpenAPS kullanıcıları

OpenAPS kullanıcıları, Medtronic pompa ile AndroidAPS'in OpenAPS'den tamamen farklı bir yaklaşım kullandığını unutmamalıdır. AndroidAPS'i kullanmak ve pompayla etkileşim kurmanın birincil yöntemi telefonunuzdur. Normal kullanımda pompa menüsünü sadece rezervuar ve set değiştirirken kullanırsınız. Bu, bolusun en azından bir kısmının genellikle hızlı bolus butonları aracılığıyla iletildiği OpenAPS kullanımından farklıdır. Pompanın manuel olarak bolus iletmek için kullanılması durumunda, AndroidAPS aynı anda bir bolus iletmeye çalışırsa sorun yaşayabilirsiniz. Bu gibi durumlarda sorunları önlemek için gerekli kontroller vardır ancak yine de mümkünse bundan kaçınılmalıdır.

### Log kayıtları

Medtronic pompa işlevinizde sorun gidermeniz gerekirse, ekranın sol üst köşesindeki menü simgesini seçin, Bakım ve Günlük Ayarları'nı seçin. Herhangi bir Medtronic sorununu gidermek için Pump, PumpComm, PumpBTComm seçili olmalıdır.

### Medtronic CGM

Medtronic CGM (SGİ) sensörleri şu anda DESTEKLENMEMEKTEDİR.

### Pompanın manuel kullanımı

Pompanızda manuel olarak bolus göndermekten veya GBO'ları ayarlamaktan kaçınmalısınız. Tüm bu komutlar AndroidAPS aracılığıyla yapılmalıdır. Manuel komutların kullanılması durumunda, herhangi bir sorun riskini azaltmak için aralarında en az 3 dakikalık bir gecikme olmalıdır.

### Saat dilimi değişiklikleri ve DST (Yaz Saati Uygulaması) veya Medtronic Pompa ve AndroidAPS ile Seyahat

AndroidAPS, Saat Dilimi değişikliklerini otomatik olarak algılar ve telefonunuz yeni saate geçtiğinde Pompanın saatini günceller.

Doğuya seyahat etmek, şimdiki zamana saat ekleyeceğiniz anlamına gelir (ör. GMT+0'dan GMT+2'ye) herhangi bir çakışma olmayacağından (örneğin aynı saatin iki kez tekrar etmesi mümkün olmayacak) herhangi bir soruna yol açmayacaktır. Bununla birlikte, batıya seyahat etmek, mevcut zamanda geriye gittiğiniz için sorunlara neden olabilir ve bu da hatalı AİNS verileriyle sonuçlanabilir.

Batıya seyahat ederken görülen sorunlar geliştiriciler tarafından biliniyor ve olası bir çözüm üzerinde çalışmalar devam ediyor. Daha fazla ayrıntı için https://github.com/andyrozman/RileyLinkAAPS/issues/145 adresine bakın. Şimdilik lütfen böyle bir sorun ortaya çıkabileceğini unutmayın ve saat dilimlerini değiştirirken dikkatli bir şekilde izleyin.

### Bir GNARL, tam uyumlu Rileylink ile karşılaştırılabilir bir cihaz mıdır?

GNARL kodu, AndroidAPS'de Medtronic sürücüsü tarafından kullanılan tüm işlevleri tam olarak destekler, bu da tamamen uyumlu olduğu anlamına gelir. Uyumlu bir donanım tedarik etmeniz ve ardından GNARL kodunu cihaza yüklemeniz gerekeceğinden, bunun ek çalışma gerektireceğini unutmamak önemlidir.

**Yazılımcı notu:** Lütfen GNARL yazılımının hala deneysel olduğunu, az test edildiğini ve RileyLink kadar güvenli olarak değerlendirilmemesi gerektiğini unutmayın.

## SSS

### RileyLink ve/veya pompa ile bağlantımı kaybedersem ne yapmalıyım?

Bağlantı sorunlarını çözmek için çeşitli seçenekler deneyebilirsiniz.

- Yukarıda ayrıntılı olarak açıklandığı gibi EYLEM sekmesindeki "Uyan ve Ayarla" butonunu kullanın.
- Telefonunuzda Bluetooth'u devre dışı bırakın, 10 saniye bekleyin ve ardından tekrar etkinleştirin. Bu işlem Rileylink cihazını telefona yeniden bağlanmaya zorlayacaktır.
- Rileylink cihazını sıfırlayın. Ardından EYLEM sekmesindeki "Rileylink Yapılandırmasını Sıfırla" butonunu kullanmanız gerekir.
- Kullanıcılar, diğer yöntemlerin olmadığı durumlarda tekrar bağlantı için aşağıdaki adımların etkili olduğunu bulmuşlardır: 
    1. Telefonunuzu yeniden başlatın
    2. *Telefon yeniden başlatılırken* Rileylink cihazınızı yeniden başlatın
    3. AndroidAPS'i açın ve bağlantının geri yüklenmesine izin verin

### Pompamın hangi Frekansı kullandığını nasıl belirleyebilirim?

![Pompa Modeli](../images/Medtronic06.png)

Pompanın arkasında, 3 harfli özel bir kodla birlikte model numaranızın ayrıntılarını veren bir satır bulacaksınız. İlk iki harf frekans tipini, son harf ise rengi belirler. Frekans için olası değerler şunlardır:

- NA - Kuzey Amerika (frekans seçiminde "ABD ve Kanada (916 MHz)" seçeneğini seçmeniz gerekir)
- CA - Kanada (frekans seçiminde "ABD ve Kanada (916 MHz)" seçeneğini seçmeniz gerekir)
- WW - Dünya Çapında (frekans seçiminde "Dünya Çapında (868 Mhz)" seçmeniz gerekir)