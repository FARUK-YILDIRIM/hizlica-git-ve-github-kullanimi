#  Hızlıca Git & Github Kullanımı
Git ve Github kullanmaya yeni başlayan kişiler için oluşturulmuş hızlı rehber. Kişilerin hızlıca Git hakkında fikir sahibi olup kullanmaya başlamaları hedeflenerek hazırlanmıştır. 

## Git Nedir?
Git, yazılım geliştirme süreçlerinde kullanılan, hız odaklı, dağıtık çalışan bir sürüm kontrol ve kaynak kod yönetim sistemidir. [bkz. wiki](https://www.wikiwand.com/en/Git)

## GitHub Nedir?
GitHub, sürüm kontrol sistemi olarak Git kullanan yazılım geliştirme projeleri için web tabanlı bir depolama servisidir. [bkz. wiki](https://www.wikiwand.com/tr/GitHub)

## Nasıl Kullanırız?
Öncelikle Git kullanmak için GitHub’a üye olmanız gerekmez.  Bilgisayarınıza kurulum yaptıktan sonra istediğiniz alanda Git kullanmaya başlayabilirsiniz. [Kurulum Dosyaları](https://git-scm.com/downloads) & [Github Docs](https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github/set-up-git)

Kurulum tamamlandıktan sonra ` git init `  komutu ile çalışmak istediğiniz her projede giti kullanabilirsiniz.  İsterseniz daha sonra projenizi Github’a yükleyebilirsiniz. 

## Komutlara Giriş
En çok kullanılan ve sorulan komutlar aşağıda açıklanmıştır. (\*) ibaresi ile ilgili dökümana bağlantı verilmiştir. Tüm dökümanları incelemek için **[Docs](https://git-scm.com/docs/)** tıklayın.

`git init .`  komutu ile projenize Giti eklersiniz. Bu işlemden sonra klasörün içerisinde .git adında **(gizli)** bir dosya olacak.  Kullandığınız terminal türüne göre **dosya-adı git:(master)** şeklinde bir ibare belirecek. [*](https://git-scm.com/docs/git-init)

*master  branch olarak adlandırılmaktadır. Bu yazıda branch kullanımından bahsedilmedi. Her hangi bir değişiklik yapmadan bu şekilde kullanabilirsiniz.* [*](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/about-branches)

`git add .`  yaptığınız değişiklikleri dizine ekler. [*](https://git-scm.com/docs/git-add)  

`git status`  dizinin o anki durumu gösterir. Hangi dosyalarda işlem yapıldı vs. [*](https://git-scm.com/docs/git-status)

`git commit`  yaptığınız değişiklikleri kaydeder.  `-m` parametresi ile yapılan işlem hakkında bilgi verebilirsiniz. [*](https://git-scm.com/docs/git-commit)

**Ör:** Diyelimki projenize bir kütüphane eklediniz bunu `git add .` komutu ile dizine ekledikten sonra  `git commit -m “Kütüphane eklendi.”` komutunu kullanarak yaptığınız değişiklikleri  kaydedebilirsiniz. 

`git log`   commit kayıtlarını gösterir. Daha sonra bu kayıtlara geri dönmek veya inceleme yapmak için commit atarken yaptığınız iş ile alakalı anlamlı mesajlar yazmanız önemlidir. [*](https://git-scm.com/docs/git-log)

`git  diff`  dizinde kalem kalem yapılan değişiklileri gösterir. [*](https://git-scm.com/docs/git-diff) Ben VSCode üzerinde **GitLens** eklentisini kullanıyorum tavsiye ederim. 

### Github ile Kullanım

Localde oluşturduğunuz projenizi Github’a yüklemek için önce repository(depo) oluşturmanız gerek. [*](https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github/create-a-repo)  

Daha sonra ilgili projenizde   `git remote add origin https://github.com/username/repository.git`  komutu ile Github ile çalışmaya başlayabilirsiniz.

`git remote -v`   projenin hangi uzak depoya bağlı olduğuna bakabilirsiniz.

Eğer uzak depo adresini değiştirmek isterseniz  `git remote set-url origin https://github.com/username/new-repository.git`  komutu ile değiştirebilirsiniz. 

`git push`   dosyalarınızı uzak depoya yükler. [*](https://git-scm.com/docs/git-push)  Bu komut ile yükleme işlemi başarısız  olursa `git push -f`  parametresi ile reponun içersindeki her şeyi  silip kendi dosyalarınızı yükleyebilirsiniz. 

*Repoyu oluştururken otomatik olarak eklemesini istediğiniz dosyalar (ex: README) varsa bu hata çıkabilir.*

#### README  Nedir?

Projeniz hakkında açıklama yapacağınız dosya. [*](https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/about-readmes)

#### .gitignore Nedir?

Github’a göndermek istemediğiniz dosya/klasör varsa .gitignore içinde belirtiyorsunuz. Push işleminde bu dosyalar Github’a yüklenmiyor.  

*Özel bilgilerinizin bulunduğu dosyaları veya pakelerin oluşturduğu dosyaları buraya ekleyebilirsiniz.*

#### Değişiklikleri Geri Almak

Bir durumdan ötürü geçmiş kodlara dönmek isterseniz. `git log` komutu ile dönmek istediğiniz commitin değerini alıp (ex:3f23ecdf139d6bcf44e3420e5c359a680a381024)
`git reset —hard 3f23ecdf139d6bcf44e3420e5c359a680a381024`  komutu ile bu işlemi gerçekleştirebilirsiniz. 
`git push -f` komutu ile GitHub üzerinde de değişiklikler geri alınacaktır. 


## Alias ile Kullanım
 Sürekli kullandığınız komutlar için kısa yollar oluşturabilirsiniz.  Burada git config üzerinden alias kullanımı yapmadım. [*](https://www.git-scm.com/book/en/v2/Git-Basics-Git-Aliases)  ZSH kullandığım için kodları `.zshrc` üzerine yazdım.  Bu şekilde kendinize özel kodlar oluşturup  terminale ekleyip kullanabilirsiniz. 

```bash
alias gia=“git add .”
alias gis=“git status”
alias gil=“git log”
gic(){
    git commit -m “$1”
}
giac(){
    gia && git commit -m “$1”
}
gif(){
    if [ “$1” = “” ]; then
        echo “Usege: gif param1: \”Commit Message\” param2(optional): \”your_branch_name\” \n Ex: gif \”my commit\”“;
    elif [ -n “$2” ]; then
        gia && git commit -m “$1” && git push origin “$2”
    else
        gia && git commit -m “$1” && git push
    fi
}
```


Burada  `gif “ilgili mesaj” `   komutunu kullanarak  Github’a commit attırıyorum.  Aslında arka planda ;
```
git add .  
git commit -m “ilgili mesaj”
git push
```

Komutları çalışıyor. 
Git komutlarını bellirli bir süre kullanıp aşina olduktan sonra alias kullanmanızı tavsiye ederim.
