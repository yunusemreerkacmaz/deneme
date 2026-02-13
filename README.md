# Git


```
git config -- global user.name “Yunus Emre Erkaçmaz”
```
+  *kullanıcı adı oluşturmayı sağlar.Tüm oluşturduğun git işlemlerinde bu isim görünür ve örneğin Modalife hesabına girdin bir repoya commit atarsan Yunus Emre Erkaçmaz diye görünür.*



``` 
git config user.name
```
+  *kullanıcı adını görüntüleme*



```
git config - - global user. email yee@gmail.com
```
+ *email oluşturmayı sağlar.Tüm oluşturduğun git işlemlerinde bu email görünür ve örneğin Modalife hesabına girdin bir repoya commit atarsan bu email görünür.*

  
```
git config user.email				
```
+ *email görüntülemeyi sağlar*


```
 git config --global core.editor "code --wait”			
```
+  *default editor ekleme(vscode için)*

  

```
git status						
```
+  *git durumu hakkında bilgi verir bulunan klasörde. Git kurulumu bilgisi verir*


```
git init
```
+ *bulunan klasörde yeni bir git işlemi başlatır.ama öncesinde git status ile kontrol et içinde oluşturulmuşsa ve tekrar git init yaparsan karışıklık olur*

  

 # Terminal
 
```
ls -la
```  
+ *gizli dosyaları gösterir*

  
```
  rm dosya_adı
```
+ *dosyaları siler*

       				

```
rm -rf klasör_adı
```
+ *klasörleri siler*
+ *Tüm dosyları gez -r(recursive -özyinelemeli)*
+ *Zorlayarak sil -f(force)*

  

```
touch dosya adı
```
+ *dosya oluşturur*



```
git add dosya_adı
```
+ *dosya git ‘e eklendi*

```
git add .
```
+ *değişikliklerin tamamı seçildi*


										
```
git commit -m “ilk mesaj oluşturuldu”
```
+ *commit işlemi yapıldı.*



```
touch .gitignore
```
+ *bir tane gitignore dosyası oluşturuldu içine dosya adını yazınca commit’ten çıkarıyor commit sayısı azalıyor*


```
git log
```
+ *commit’leri gösterir commitler fazla ise aşağı ve yukarı oklar ile kaydırılıp bakılabilir uzun log var dan çıkmak için “q” harfine basmak yeterli*


`(Head -> Master)`
+ *git log yazdığında üstte bunu yazar head olayı git içerisinde son commit’i gösterir master ise branch adını gösterir*



# NOT

“GitHub gitignore templates” diye arat kendi sayfasında tüm dillerin yer aldığı default gitignore dosyaları var (Reactjs’yi göremeyebilirsin Node’yi alman lazım)


```
git branch
```
+ *Tüm branch’leri listeler “ * ” işareti hangisinin üzerindeyse bulunduğun branch’i gösterir*



```
git branch branch_adı
```
+ *yeni bir branch oluşturma*


```
git switch branch_adı
```
+ *dönmek istediğin branch adı. Git log yazdığında şöyle görünür(HEAD -> gittiğin_branch_adı, master) son commit hem gittiğin branch adında hemde master da ama sonrasında yaparsan sadece (HEAD -> gitttiğin_branch_adı) gösterilir*

  

```
git merge birleştirmek_istediğin_branch_adı
```
+ *iki branch’i birleştirmek istersen yapmak gerekenler.Ama birleştirmeden önce hangi branch ‘in içindeysen onun içinden devam eder. Bir dosya açılır o dosyanın içine en üstüne commit mesajını yazıp kaydedebilirsin*


```
git branch -d  branch_adı
```
+ *branch silme işlemi ama silmek için başka bir branch’e geçmen gerekir*


```
git branch -D branch_adı
```
+ *branch adını siler zorla ama silmek için başka bir branch’e geçmen gerekir*



```
git stash
```
+ *branch değiştirirken değişiklikleri stash adlı olan yere ekler*



```
git stash pop
```
+ *stash den veriyi geri çeker*



```
git stash list
```
+ *stash verilerini listeler ( stash@{0} …. , stash@{1}…., stash@{2}….)*



```
git stash apply  stash@{0}
```
+ *seçtiğin bir stash verisini geri getirmeyi sağlar sağlar.stash{1} verisini geri getirir.*



```
git stash clear	
```
+ *bütün stashleri siler*


```
git restore dosya_adı.txt
```
+ *dosyayı en son commit ettiğiniz hale dönüştürür değişiklikler kaybolur yani bir önceki commit’e kadar olan kısmdaki değişiklikleri kaldırır*


```
git restore --staged dosya_adi.js
```
+ *seçilen dosyayı stage den çıkarmayı sağlar yani git add dosya_adi.js  işleminin tersi*



```
git checkout commit_numarası
```
+ *seçilen commit’i geri almayı sağlar. Commit numarasını git log da commit yazısı karşısında görebilirsin ardından git branch yazdığında * (HEAD detached at 1a6fcd9) ve master branchlerini gösterebilirsin head şuan hiçbirşeyi göstermiyor.Aslında önceki commitlerde neler yaptın geçmişe dönüp seyahat edip kodlarını görmeni sağlar.*


```
git reset commit_numarası
```
+ *seçilen commit numarasına kadar olan commitleri geriden sırasıyla silmeye başlar ama değişiklik vs code’a yansımaz.örneğin commitler 1,2,3,4,5,6 olsun 3 yazarsan 4,5,6 silinir ve 4,5,6 ya ait olan commitler silinmez*


```
git reset - - hard commit_numarası
```
+ *seçilen commit numarasına kadar olan commitleri zorlayarak geriden sırasıyla silmeye başlar ama o commitlere ait olan değişiklikleri de siler örneğin commitler 1,2,3,4,5,6 olsun 3 yazarsan 4,5,6 silinir ve 4,5,6 ya ait olan commitler de silinir*


```
git revert son_commit_numarası
```
+ *commit numarasını sırasıyla sil “This Revert commit a123…” yazar ama hemen altında a123 commitini de gösterir.sen bir öncekine geç bu sefer o commiti revert et ulaşmak istediğin commit’e kadar yaz.revert ettikçe verileri de silinir*

  

```
git diff
```
+ *değişiklikler gösterilir “ + ” ile gösterilenler eklenen “ - “ ile gösterilenler silinenlerdir a,b,c… bunları kendisi ekliyor a dosyanın ilk hali b değişiklik 1 , c değişiklik 2 vs … @@ yanındaki sayılar (satır başlangıcı,kaç satır veri alındığını) gösteri + ve eksi önemsiz diğer bilglerde önemsiz*



```
git diff HEAD
```
+ *HEAD’ın olduğu yerdeki değişiklikler gösterilir genelde head son committe yer alır o yüzden genelde son commit değişikliklerini gösterir*



```
git diff sonraki_commit önceki_commit
```
+ *iki commit arasındaki değişiklikleri gösterir eğer iki commit arasında boşluğu kabul etmezse : koy*



```
git diff branch_1 branch_2
```
+ *iki branch arasındaki değişiklileri gösterir*




```
git rebase master
```
+ *master’ı bulunduğum branch’e taşıdı yani tüm commit ip gibi dizildi,log temizlemek için ve tarihini yeniden yazmak için kullanabilirsin ama tehlikeli biraz sıralama şöyle olur  master_commit_1,master_commit_2,feature_commit_1,feature_commit_2 vs..*
+ 


---



# NOT

Örneğin A dosyası master da ve new_Branch diye bir branch açsaydım sonra new_Branch içinde A doyasının içindeki verileri değiştirseydim yada silseydim ama master da değiştirmeseydim yada silmeseydim veya yeni şeyler ekleseydim conflict oluşacaktı 

Eğer master da hiçbirşey yapmazsan ve başka bir branch de değişiklik yaparsan sonra branch teki değişiklikleri master’a direkt ekleyebilirsin bunda conflict oluşmaz (Fast Forwarding)


---

# Github

Star bir projeyi star yaparsan dönüp bakmak için kullanabilirsin ve o kişiyi beğenmeyi sağlar favorilemek ve like bir arada gibi düşün

Üstte Explore diye bir menü var orada farklı repoları gezip göresbilirsin

Herhangi birinin projesine girdikten sonra orda issues kısmı var filters yazan yerde is :issue is:open yazan yerdeki is:open silersen ve sadece is :issue  kalırsa kapanmış olan sıkıntıları görüntülersin ve o sıkıntılara tıklayıp yorum yapabilirsin



```
git push -u origin master
```
+ *Github’a kodları göndermeyi sağlıyor origin girhub taki repo url’sine denk geliyor örneğin origin = https :// GitHub/yunusemre/newRepo.git ifade eder*



```
git push origin master
```
+ *-u(upstream)  bir kere yazdıktan sonra onu kaldırıp direkt gönderebilirsin*




```
git push
```
+ *branch olarak bulunduğu branch’i alır origin birlere yazmıştın direkt gönderdi*




```
git remote
```
+ *bunu terminalde yazarsan sana origin döner bu zaten senin git url yani şu https :// GitHub/yunusemre/newRepo.git*



```
Create Pull Request
```
+ *“ base:master   <— compare : feature “ üstte şöyle bir ibare görürsün feature branch’i içindekileri master’a gönderebilirsin ve sağında Able to merge yazar yani merge edilmeye hazır ve merge için bir metin yazıp Create Pull Request butonuna bas.burasını kodu yöneten kişi görebilir ve 													onay verebilir ve seni bir sonraki aşamaya yönlendiri Merge Pull Request*



```
Merge Pull Request
```
+ *Gelen kodu kendi kodlarınla birleştirmek ister misin ? Ve sana conflict var mı yok mu onu gösterir Eğer onay verirsen bir Confirm Merge yöneldirir.*



```
Confirm Merge
```
+ *bir başlık ve açıklama gelir onları yazıp onaylarsan kodlar merged edildi onayı alırsın ve sana master olamayan sonra “Delete Branch” önceki branch’i silme önerisinde bulunur eğer onu silersen o arlasından “Restore branch” çıkar ona tıklarsan sana sildiğin branch’i geri getirir.*


```
git branch -r
```
+ *sana GitHub’taki branch’leri listeler örneğin (origin/feature, origin/master) gibi. Sakın lakal’deki branch’ler ile karıştırma lokalde sadece git branch yazınca sana lokaldeki branch’leri listeler GitHub’takileri değil. -r zaten remote anlamına geliyor*



```
git push origin --delete branch adı
```
+ *branch’i siler ama silmek için başka bir branch’e geçmen gerekir*



```
git checkout origin branch_adı
```
+ *branch değiştirmeyi sağlar git branch -r yaz branch ismini gör sonra “git checkout origin/master “ yaz branch değişikliği yap*


```
git fetch origin master
```
+ *örneğin github’taki commit’lerin lokale’ göre ilerde olsun git fetch origin master yaparsan ardından git status çalıştırırsan sana 2 commit geridesin uyarısı verir.değişiklikleri getiriyor ama dosyalarımıza müdahale etmiyor.github’ın gerisindeysen yapaman gerekiyor ilerisindeysen de push etmelisin*


```
git pull origin master
```
+ *git pull = git fetch + git merge    değişiklikleri getiriyor ama dosyalarımıza müdahale ediyor değişiklikleri dosyalarında görebilirsin ayrıca bir dosya açılıyor orda bir commit mesajı atmanı bekliyor github’ın gerisindeysen yapman gerekiyor.İlerisindeysen de push etmelisin*


```
git clone url
```
+ *terminalde bunu yazdığında bulunan klasöre dosyaları indirir ardından açıp kullanabilirsin(çok pratik)*



`Fork (bir kod değil)`
+ *Başka birinin projesini alıyor benim hesabıma ekliyor ve  onunla yollarımı ayırıyorum eklediklerim benim repository’mde gözükecek artık demek ama kimden aldığım belli clone öyle değil kimden aldığın belli değil sıfır bir projeymiş gibi.Bir projeyi geliştirip o kişilere göndermek istiyorsan clone kullan fork’u kullanma.Fork yaptığında Conribute(Başka geliştiricinin eklediklerini projemle birleştir),Fetch upstream(Başka geliştiricinin eklediklerini projemle olan değişikliklerini göster) *


```
git clone url
```
+ *terminalde bunu yazdığında bulunan klasöre dosyaları indirir ardından açıp kullanabilirsin(çok pratik)*




```
Collaborators (bir kod değil)
```
+ *private olarak eklenen bir respoitory’i başka birinin görebilmesi için Settings -> Collaborators-> Add people tıkla ordan kişiyi ara bul ve ekle bu bir davet karşı tarafta onaylarsa oluyor(Accept invitation) ve artık puss access yetkisi oluyor private ile çalışmak public ile çalışmaktan kolay*



```
git clone url
```
+ *terminalde bunu yazdığında bulunan klasöre dosyaları indirir ardından açıp kullanabilirsin(çok pratik)*

 
# Terminal çıktısı rengini değiştirme

Terminalde klavyeden girdiğin rengi kendin değiştirebilirsin Üstte Terminal -> Ayarlar dan değiştirebilirsin

```
preexec() { echo -ne "\e[32m" }
```
+ *Komut çalışmaya başladığında çıktı rengini değiştirir (32,33…36. —> renkler)*



```
precmd() { echo -ne "\e[0m" }
```
+ *Komut bittiğinde ve yeni satıra geçildiğinde rengi sıfırlar*


---


# GitHub sayfasında yazanlar

Private kullanmak için. Token gerekiyor ve onun içinde  profil -> setttings -> developer settings -> personal access tokens -> tokens(classic) -> generate new token -> token adını yaz ve onayla sonra şifreyi kopyala yoksa bir daha göremezsin 


```
git remote add origin https:// Token@github.com/kullanıcı adı/repo adı.git
```
+ *Yukarıdaki kodu kullanman gerekir ve aradaki @ işaretini unutma*

 
##### Örnek 

modalife@Huseyin-MacBook-Air api % git remote -v

 ###### ekran çıktısı
 
+ mpdks-api       __https://ghp_2jUo6Poidklfjgdjflkgjdlfgjlhfgpofsdfjsdklfjgkjfdk@github.com/ferdi/mpdks-api.git (fetch)__
+ mpdks-api       https://ghp_2jUo6Poidklfjgdjflkgjdlfgjlhfgpofsdfjsdklfjgkjfdk@github.com/ferdi/mpdks-api.git (push)

+ origin  https://github.com/modalifegh/mpdks-web-ui.git (fetch)
+ origin  https://github.com/modalifegh/mpdks-web-ui.git (push)



```
git remote -v
```
+ *Projenin hangi adrese bağlı olduğunu unutursan klasörün içindeyken şunu yaz: Hangi hesaba bağlı olduğunda görünür* 


```
git remote remove origin
```

+ *Projenin GitHub ile bağlantısını kesmiş oluyorsun(connection string olarak düşünebilirsin , origin ismini ben verdim bağlantı adı gibi düşün)* 
+ *Tüm bağlantıyı (hem çekme hem gönderme adreslerini) tamamen koparırsın.*


---

# Yeni Repository oluşturduktan sonra yapılacaklar

+ *Sıfırdan Başlıyorsan (Create a new repository): (origin yazan yere istediğin ismi verebilirsin bağlantı adresinin adı diye düşünebilirsin)*

```
 git init
```

```
git add .
```

```
git commit -m "ilk yukleme"
```



```
git branch -M main
```



```
git remote add origin https://github.com/KULLANICI_ADIN/REPO_ADIN.git
```


```
git push -u origin main
```

---

# Zaten Bir Klasörün Varsa ve Sadece Göndermek İstiyorsan

```
git remote add origin https://github.com/KULLANICI_ADIN/REPO_ADIN.git
```


```
git branch -M main
```


```
git push -u origin main
```
---



```
history | grep git
```
+ *Daha önce hangi komutları yazdığını hatırlamak için terminale şunu yazabilirsin*



```
git remote set-url --add --push origin https://github.com/modalifegh/mpdks-web-ui.git
```
+ *Aynı "origin" ismini kullanarak, kodunuzu tek bir git push komutuyla aynı anda birden fazla uzak depoya (örneğin hem GitHub hem GitLab) göndermenizi sağlar*



+ Neden Kullanılır? (Senaryo)
Diyelim ki bir projeniz var ve bu projeyi hem GitHub'da hem de firmanızın kendi GitLab sunucusunda güncel tutmak istiyorsunuz. Normalde her ikisine ayrı ayrı push yapmanız gerekir:

```
git push github master
```


```
git push gitlab master
```


 ###### Aşağıdaki komutu kullandıktan sonra ise sadece şunu yazmanız yeterli olur


 ```
git push origin master
```


###### Git, bu komutu gördüğünde kodunuzu origin altında kayıtlı olan tüm push URL'lerine sırayla gönderir.

```
git remote set-url --add --push origin https://ghp_2jUo6PoiYs94i0QM43Z@github.com/yunusemreerkacmaz/mpdks-web-ui.git
```
---

```
git remote set-url origin https://yeni-adres.git
```

+ *mevcut olan bir uzak depo adresini (URL) tamamen değiştirmek/güncellemek ise --add veya --push takılarını kullanmana gerek yok.*

 

