# bankbot-mazain

Son yıllarda [Türk bankacılığı](https://github.com/bemre/bankalarbirligi) ve [finansal uygulamalarını](https://github.com/bemre/mobil_sube.apk) hedefleyen farklı zararlı yazılım türlerine karşı mücadele verdik. 
Özellikle son iki yıl içerisinde bankacılık uygulamalarını hedef alan zararlı yazılımların arttığını gözlemleyebilmekteyiz. Yeni tipteki bu zararlı mobil bankacılık uygulamalarının oltalama ve SMS yoluyla gelen mesajlar ile yayıldığı görülmektedir.

Zeus Botnet'inin kaynak kodlarının herkese açılması gibi Bankbot ya da Mazain adı verilen zararlı yazılımın komuta kontröl ve istemcisinin de kaynak kodlarının çeşitli forumlarda ve web sitelerinde yayılması, bankbot'un ve türevlerinin hızlıca çoğalmasına sebep olmuştur. Android cihazları hedef alan bu yazılımın ve PHP ile geliştirilen C&C sunucusuna ait Panel çeşitli sitelerde görülebilmektedir.

Bunlardan bazıları:
- hxxp://nora.biz/index.php?threads/Пишем-android-бота-с-нуля.1425/

![nora-biz](https://i.imgur.com/2fSvySQ.jpg)

hxxps://forum.exploit.in/index.php?s=52f9e19ea5173f0ea43855edabafff41&showtopic=113555
![exploit-in](https://i.imgur.com/PQGe1qi.jpg)

hxxp://a0007517.xsph.ru/threads/pishem-svoj-android-botnet-s-nulja.6/ 
![Darklub](https://i.imgur.com/YZWYpD8.jpg)

Zararlı yazılımın komuta merkezi küçük bir koda sahip ve bu kod ile kendisine bağlanacak android bot'ların yönetilmesini sağlamaktadır. özellikle bankacılık uygulamaların olmazsa olmazı olan OTP mesajlarının elde etmek için kurbanların SMS içerikleri panel vasıtasıyla çalınmaktadır.

![Botnet C&C Source Code](https://i.imgur.com/2TB4KGJ.png)

Halihazırda oldukça fazla C&C sunucusu aktif olarak çalıştığı görülmektedir.

![screenshot of C&C server](https://i.imgur.com/LCG2uhs.jpg)

C&C sunucusu olarak hizmet veren sunucuları büyük bir çoğunluğu [.gdn TLD](https://en.wikipedia.org/wiki/.gdn) & geri kalanı ise [.pw TLD](https://en.wikipedia.org/wiki/.gdn) üzerinde hizmet vermektedir.
![other domains of C&C domain owner](https://i.imgur.com/BV2KEj4.png)

C&C sunucusu olarak kullanılan domainler:
 - ifc3yb3rs3cur1tych0.pw
 - 1nj3ct10n.gdn 
 - r0n4ld4.gdn
 - t4l1sc4.gdn 
 - trolitrader.pw
 - bigbustown.pw
 - ch4pr6.gdn
 - n0309.gdn
 - tr4f0.pw
 - t1lk1.gdn
 - b46.gdn
 - ...
 Bu liste diğer domainlerin de eklenmesiyle güncellenecektir.
 
Domain'lerin sahibi olan kişi aynı zamanda değişik zamanlarda farklı tipteki oltalama saldırıları için kullanılan domain'lere de sahip olan kişi olarak öne çıkmaktadır.

Bu domainler ise:
 - hxxp://e-trafikcezasiodemesi.net
 - hxxp://guvenliktrafikcezasiodemeyeri.com
 - hxxp://jethgsyukle.com  
  
  ![enter image description here](https://i.imgur.com/TYRH3iW.png)

Daha önceleri kullanılan domainlerden bazıları:
![C&C servers search engine result](https://i.imgur.com/z1DYYC0.png) 

![C&C server google cache](https://i.imgur.com/ttZXQi0.png)

![C&C server google cache](https://i.imgur.com/4F01ycp.png)

Aşağıda belirtilen siteleri android cihaz ile ziyaret ettiğiniz vakit bahsedilen bankbot zararlı yazılımın yüklenmesi için sizi ayrı bir siteye yönlendirmektedir..

 - hxxp://ircforumlari.net
 - hxxp://filmindirsene.net
 
![IRC forumlari](https://i.imgur.com/aXCyPWO.png)  

![FilmIndirsene](https://i.imgur.com/msw9FsV.png)

Bu siteleri android üzerinde kullanılabilen bir tarayıcıya ait bilgileri kullanarak ya da android cihazlar ile ziyaret ettiğiniz vakit kısa link ile belirtilen ve zararlı yazılımı kurulması için talimat veren bir sayfa karşımıza çıkmaktadır.

***Devam edebilmek için Android Flash Player gerekiyor.***

![FilmIndirseneSource](https://i.imgur.com/FFoc9Mc.png)

- hxxp://dogrulama.link  
Bu site URL kısaltma servisi olarak kullanılmakta hem de sahte Flash Player uygulmasını üzerinde barındırmaktadır.

Sitede bulunan sahte FlashPlayer.apk dosyası ve internet üzerinde bulunan diğer bankbot zararlısına ait SHA256 hash bilgileri şu şekildedir:
- 62ca7b73563f946df01d65447694874c45d432583f265fad11b8645903b6b099
- 3bf02ae481375452b34a6bd1cdc9777cabe28a5e7979e3c0bdaab5026dd8231d
- 6b93f837286da072f1ec7d5f5e049491d76d4d6ecc1784e1fadc1b29f4853a13
- d8b28dbcc9b0856c1b7aa79efae7ad292071c4f459c591de38d695e5788264d1
- bd194432a12c35ae6ae8a82fa18f9ecac3eb6e90c5ff8330d20d19e85a782958
- e0da58da1884d22cc4f6dfdc2e1da6c6bfe2b90194b86f57f9fc01b411abe8de 

Kaynak kodlardan görülebildiği üzere bazı sınıf isimleri ve hata ayıklama mesajları Türkçe olarak yazılmıştır:
![Decompiled APK](https://i.imgur.com/6Gc60Pq.png)

Ayrıca bazı Rusça ifadeler de yer almaktadır.Zararlının orijinalinin rus forumlarında duyurulduğu yukarıdaki ekran görüntülerinden de görülebilmektedir.

![enter image description here](https://i.imgur.com/pnXFZkr.png)
ПРОВЕРКА! & Запрос USSD выполнен

sahtep flashplayer.apk uygulaması android cihaza yüklendikten sonra ilk olarak kullanıcıdan admin haklarına sahip olmak istediğini belirtir bir mesaj göstermektedir.

![Device Admin Privileges](https://i.imgur.com/w8EHlMk.png)
![Device Admin](https://i.imgur.com/U1FX4MJ.png)

Böylece zararlı, komuta sunucusundan gerekli komutları beklemek üzere arka planda çalışmaktadır.

Zararlının ihtiyaç duyduğu diğer izinler:
![permissions](https://i.imgur.com/vDk9PUP.png)
![enter image description here](https://i.imgur.com/XZlGGdM.png)


Zararlının çalıştırdığı android servisleri
![enter image description here](https://i.imgur.com/8HenZbg.png)

BankBot zararlısı C&C vasıtasıyla android cihaz üzerinden aşağıdaki işlemleri gerçekleştirmektedir:

![enter image description here](https://i.imgur.com/7uKtLYH.png)

- Hücresel Bilgi yayını mesajlarını elde etme
![enter image description here](https://i.imgur.com/zY7086o.png)

- Cihaz üzerinde Yöneticii Hakkını elde etme
![enter image description here](https://i.imgur.com/VPqTlY6.png)

- SMS Gönderme
![Send SMS](https://i.imgur.com/yXnn5pk.png)

Zararlı yazılım statham sınıfı ile sistem üzerinde çalışan uygulama listesini almaktadır.
![getting running process list](https://i.imgur.com/kNUNYZZ.png)

![enter image description here](https://i.imgur.com/lCKUE2F.png)

Bankbot, android üzerinde çalışan uygulama listesini elde ettikten sonra bunu kaynak kod içerisinde bulunan liste ile karşılaştırmaktadır.

![enter image description here](https://i.imgur.com/Omfr7Dc.png)

Neredeyse tüm Türk mobil bankacılık uygulamaları bankbot zararlı yazılımından nasibini almaktadır.

İlgili uygulamalar:
 - com.ziraat.ziraatmobil
 - com.ziraat.ziraattablet
 - com.tmobtech.halkbank
 - com.vakifbank.mobile
 - com.pozitron.vakifbank
 - com.akbank.android.apps.akbank_direkt
 - com.akbank.softotp
 - com.akbank.android.apps.akbank_direkt_tablet
 - tr.com.sekerbilisim.mbank
 - com.teb
 - com.pozitron.iscep
 - com.softtech.isbankasi
 - com.ykb.android
 - com.ykb.androidtablet
 - com.tmob.denizbank
 - com.tmob.tabletdeniz
 - com.garanti.cepsubesi
 - biz.mobinex.android.apps.cep_sifrematik
 - com.htsu.hsbcpersonalbanking
 - com.ingbanktr.ingmobil
 - com.magiclick.odeabank
 - com.finansbank.mobile.cepsube
 - finansbank.enpara
 - com.pozitron.albarakaturk
 - com.kuveytturk.mobil


Kaynak koddan gözlemleyebildiğimiz kadarıyla bazı telefon numaraları bloklanmaktadır.

    Toast.makeText((Context)context, (CharSequence)"Giden Aramalar Engellendi.", (int)0).show();

Kaynak kodda bulunan bu numaralar ilgili bankaların telefon bankacılık sistemine erişim için kullanılan numalaralarıdır.

    this.b = arrayList.getStringExtra("incoming_number");

- arrayList = new ArrayList();
- arrayList.add("+9008502200000");
- arrayList.add("+908502200000");
- arrayList.add("+904440000");
- arrayList.add("+9008502220400");
- arrayList.add("+908502220400");
- arrayList.add("+904440400");
- arrayList.add("+9008502220724");
- arrayList.add("+908502220724");
- arrayList.add("+904440724");
- arrayList.add("+9008502222525");
- arrayList.add("+908502222525");
- arrayList.add("+904442525");
- arrayList.add("+9008502227878");
- arrayList.add("+908502227878");
- arrayList.add("+904447878");
- arrayList.add("+9008502000666");
- arrayList.add("+908502000666");
- arrayList.add("+904440832");
- arrayList.add("+9002166353535");
- arrayList.add("+902166353535");
- arrayList.add("+9008507240724");
- arrayList.add("+908507240724");
- arrayList.add("+904440202");
- arrayList.add("+9008502220444");
- arrayList.add("+908502220444");
- arrayList.add("+904440444");
- arrayList.add("+9008502220800");
- arrayList.add("+908502220800");
- arrayList.add("+904440800");
- arrayList.add("+9008502220333");
- arrayList.add("+908502220333");
- arrayList.add("+904440333");
- arrayList.add("+9008502110111");
- arrayList.add("+908502110111");
- arrayList.add("+9008502220600");
- arrayList.add("+908502220600");
- arrayList.add("+904448444");
- arrayList.add("+9002123048444");
- arrayList.add("+902123048444");
- arrayList.add("+9008502220900");
- arrayList.add("+908502220900");
- arrayList.add("+904440900");
- arrayList.add("+9008502223663");
- arrayList.add("+908502223663");
- arrayList.add("+9008502225666");
- arrayList.add("+908502225666");
- arrayList.add("+904445666");
- arrayList.add("+9002166660101");
- arrayList.add("+902166660101");
- arrayList.add("+9008502510123");
- arrayList.add("+908502510123");
- arrayList.add("+9002123541111");
- arrayList.add("+902123541111");
- arrayList.add("08502200000");
- arrayList.add("8502200000");
- arrayList.add("4440000");
- arrayList.add("08502220400");
- arrayList.add("8502220400");
- arrayList.add("4440400");
- arrayList.add("08502220724");
- arrayList.add("8502220724");
- arrayList.add("4440724");
- arrayList.add("08502222525");
- arrayList.add("8502222525");
- arrayList.add("4442525");
- arrayList.add("08502227878");
- arrayList.add("8502227878");
- arrayList.add("4447878");
- arrayList.add("08502000666");
- arrayList.add("8502000666");
- arrayList.add("4440832");
- arrayList.add("02166353535");
- arrayList.add("2166353535");
- arrayList.add("08507240724");
- arrayList.add("8507240724");
- arrayList.add("4440202");
- arrayList.add("08502220444");
- arrayList.add("8502220444");
- arrayList.add("4440444");
- arrayList.add("08502220800");
- arrayList.add("8502220800");
- arrayList.add("4440800");
- arrayList.add("08502220333");
- arrayList.add("8502220333");
- arrayList.add("4440333");
- arrayList.add("08502110111");
- arrayList.add("8502110111");
- arrayList.add("08502220600");
- arrayList.add("8502220600");
- arrayList.add("4448444");
- arrayList.add("02123048444");
- arrayList.add("2123048444");
- arrayList.add("08502220900");
- arrayList.add("8502220900");
- arrayList.add("4440900");
- arrayList.add("08502223663");
- arrayList.add("8502223663");
- arrayList.add("08502225666");
- arrayList.add("8502225666");
- arrayList.add("4445666");
- arrayList.add("02166660101");
- arrayList.add("2166660101");
- arrayList.add("08502510123");
- arrayList.add("8502510123");
- arrayList.add("02123541111");
- arrayList.add("2123541111");

Zararlı yazılımı geliştiren kişinin ya yazılım bilgisinin çok iyi olmaması ya da biraz tembel olduğunu Google aramalarından da çıkabilen şu kod ile görebiliriz.
Birçok kaynakta gözüktüğü üzere telefon aramayı durdurma ya da dinleme için kullanılan kodun aynısı yazılımın içerisinde de birebir kullanılmıştır.
![callblocking](https://i.imgur.com/Qof4Got.png)

Zararlı yazılım ayrıca android kullanıcısından internet bankacılığında kullanılan Hesap/Parola bilgisini elde edebilmek için ilgili bankalar için oluşturulan sahte giriş sayfası hazırlamıştır..
![enter image description here](https://i.imgur.com/7nsoRrT.png)

Kullanıcıyı oltalama sayfasına yönlendirmek için kullanılan kod parçacığı:
![credentialgrab](https://i.imgur.com/olqYTVc.png)

Bankbot zararlısının ve kontrol panelinin kodunun açık olması önümüzdeki günlerde yine birçok kullanıcının hedef alınacağı sonucu bize göstermektedir.
