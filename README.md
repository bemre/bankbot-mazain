# bankbot-mazain

In recent years we've struggled against different types of malware that targeting [Turkish banking](https://github.com/bemre/bankalarbirligi) and [financial institution's apps](https://github.com/bemre/mobil_sube.apk). It has been observed that malicious banking applications have increased over the last two years. Especially on the mobile side, many new types of malicious software has spread via phishing, smishing etc. 

As the spread of Zeus botnet's source code, Bankbot or Maza-in bot and C&C source code is also open sourced and different variants of this bots are spread in underground portals. Entire code of the Android application, as well as the complete C&C panel in PHP is  available in different forums

Some of them:
- hxxp://nora.biz/index.php?threads/Пишем-android-бота-с-нуля.1425/

![nora-biz](https://i.imgur.com/2fSvySQ.jpg)

hxxps://forum.exploit.in/index.php?s=52f9e19ea5173f0ea43855edabafff41&showtopic=113555
![exploit-in](https://i.imgur.com/PQGe1qi.jpg)

hxxp://a0007517.xsph.ru/threads/pishem-svoj-android-botnet-s-nulja.6/ 
![Darklub](https://i.imgur.com/YZWYpD8.jpg)

the software that used in C&C servers has small PHP code. C&C  portal is managing android bots via commands. And it is stealing SMS messages to get OTP.

![Botnet C&C Source Code](https://i.imgur.com/2TB4KGJ.png)

This C&C server basically add bots to panel and catch SMS messages from android phones.
There are lots of active C&C servers in the wild

![screenshot of C&C server](https://i.imgur.com/LCG2uhs.jpg)

Almost all C&C servers are served on domain with .gdn TLD  https://en.wikipedia.org/wiki/.gdn & some of them are  served on domain with .pw TLD
![other domains of C&C domain owner](https://i.imgur.com/BV2KEj4.png)

 Observed domains are:
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
 this list will be updated after other domains has found
 
The person who owns these domains has previously used different domains as serving phishing sites and C&C servers.
 - hxxp://e-trafikcezasiodemesi.net
 - hxxp://guvenliktrafikcezasiodemeyeri.com
 - hxxp://jethgsyukle.com  
  
  ![enter image description here](https://i.imgur.com/TYRH3iW.png)

old ones are:
![C&C servers search engine result](https://i.imgur.com/z1DYYC0.png) 

![C&C server google cache](https://i.imgur.com/ttZXQi0.png)

![C&C server google cache](https://i.imgur.com/4F01ycp.png)

When you visited the following Turkish sites with mobile devices, the site helped spread mentioned android bot.

 - hxxp://ircforumlari.net
 - hxxp://filmindirsene.net
 
![IRC forumlari](https://i.imgur.com/aXCyPWO.png)  

![FilmIndirsene](https://i.imgur.com/msw9FsV.png)

If you visit sites mentioned above with mobile devices or browser with the user-agent strings set as one of the android browsers, site offers to install android application via shortened link. 

***You need to install Flash Player for Android  from the link below so you can visit the site.***

![FilmIndirseneSource](https://i.imgur.com/FFoc9Mc.png)
hxxp://dogrulama.link  site which is serving URL shortening service is hosting fake flash player application. 

SHA256 hashes of FlashPlayer.apk and its variants.
- 62ca7b73563f946df01d65447694874c45d432583f265fad11b8645903b6b099
- 3bf02ae481375452b34a6bd1cdc9777cabe28a5e7979e3c0bdaab5026dd8231d
- 6b93f837286da072f1ec7d5f5e049491d76d4d6ecc1784e1fadc1b29f4853a13
- d8b28dbcc9b0856c1b7aa79efae7ad292071c4f459c591de38d695e5788264d1
- bd194432a12c35ae6ae8a82fa18f9ecac3eb6e90c5ff8330d20d19e85a782958
- e0da58da1884d22cc4f6dfdc2e1da6c6bfe2b90194b86f57f9fc01b411abe8de 

It seems that some of the class names are written in Turkish. 
![Decompiled APK](https://i.imgur.com/6Gc60Pq.png)

and some also Russian (original ones are already found on the Russian forums).

![enter image description here](https://i.imgur.com/pnXFZkr.png)
ПРОВЕРКА! & Запрос USSD выполнен

After installing the flashplayer.apk to phone the malware asks the user to give the device admin privileges for the first time.

![Device Admin Privileges](https://i.imgur.com/w8EHlMk.png)
![Device Admin](https://i.imgur.com/U1FX4MJ.png)


the other permissions that malware want to use are:
![permissions](https://i.imgur.com/vDk9PUP.png)
![enter image description here](https://i.imgur.com/XZlGGdM.png)


Malware has some services to run.
![enter image description here](https://i.imgur.com/8HenZbg.png)

The Trojan can receive the following commands from the C&C:

![enter image description here](https://i.imgur.com/7uKtLYH.png)

- Unstructured Supplementary Service Data request
![enter image description here](https://i.imgur.com/zY7086o.png)

- Request Admin/Root Privileges
![enter image description here](https://i.imgur.com/VPqTlY6.png)

- Send SMS
![Send SMS](https://i.imgur.com/yXnn5pk.png)


Malware scans all running process defined in statham class.
![getting running process list](https://i.imgur.com/kNUNYZZ.png)

![enter image description here](https://i.imgur.com/lCKUE2F.png)

After it has received the all running process list, It Compares to its own list of mobile banking applications.
![enter image description here](https://i.imgur.com/Omfr7Dc.png)

Almost all of the Turkish Mobile Banking and Financial applications  are affected by BankBot malware right now:
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


And also The phone numbers in the source code are blocked by Bankbot. 

    Toast.makeText((Context)context, (CharSequence)"Giden Aramalar Engellendi.", (int)0).show();

Each of these phone numbers is used to access the related bank's phone banking system.

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

The person who developed the malware is likely to be a bit lazy or have little experience in programming.
Various sources on Internet shows that same string used for intercept/blocking outgoing calls.
![callblocking](https://i.imgur.com/Qof4Got.png)

Also C&C server has special login pages for getting credentials from user.
![enter image description here](https://i.imgur.com/7nsoRrT.png)

display phishing window WebView with content downloaded from the link specified in a command.
![credentialgrab](https://i.imgur.com/olqYTVc.png)


We are likely to face many cases this year with the spread of open source malicious mobile banking application.
