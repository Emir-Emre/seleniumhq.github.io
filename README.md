[![GitHub Actions](https://github.com/seleniumhq/seleniumhq.github.io/workflows/Publish%20Selenium%20Site/badge.svg)](https://github.com/SeleniumHQ/seleniumhq.github.io/actions?query=workflow%3A%22Publish+Selenium+Site%22)

<a href="https://selenium.dev"><img src="https://selenium.dev/images/selenium_logo_square_green.png" width="200" alt="Selenium"/></a>

# Selenium Sitesi ve Dökümantasyonu

Bu, resmi Selenium [web sitesini](https://selenium.dev) oluşturmak ve yayınlamak için kullanılan depodur.

## Hızlı başlangıç

Siteyi oluşturmak ve işlemek için [Hugo](https://gohugo.io/) ve [Docsy theme](https://www.docsy.dev/)
kullanıyoruz. Bu sitede çalışmak için  Hugo ikilisinin genişletilmiş Sass/SCSS versiyonuna ihtiyacınız olacak. Hugo 0.83.1 veya üstünü kullanmanızı öneririz.

Bunun yerel olarak çalışması ve üzerinde çalışması için gereken adımlar:

- Docsy`den [Hugo Yükleme](https://www.docsy.dev/docs/getting-started/#install-hugo) talimatlarını izleyin
- Bu depoyu klonla
- Çalıştır `git submodule update --init --recursive`
- Çalıştır `cd website_and_docs`
- Çalıştır `hugo server`

Tam bir katkı klavuzu [contributing](https://selenium.dev/documentation/about/contributing/) de görülebilir.

## Nasıl katılırım?

Lütfen https://selenium.dev/getinvolved/ adresinde bulunan tüm bilgileri kontrol edin.

## Selenyum Site ve Dokümantasyon sorumluları için
### Site ve dokümanlar nasıl oluşturulur?

GitHub eylemleri, her bir PR ve korumalı daldaki her commit için çalışır. Düzenli CI yürütme,
commit`in çalıştığını doğrulamak için siteyi Hugo ile birlikte oluşturacaktır. Bu adımların açıklaması eylemler yapılandırma dosyasında görülebilir, [biri PR test etmek için](./.github/workflows/test.yml), ve 
[biri siteyi dağıtmak için](./.github/workflows/deploy.yml)

### Site ve dokümanlar nasıl dağıtılır?
`dev` dalında gerçekleşen her CI yürütmesinden sonra, komut [build-site.sh](./build-site.sh) 
dağıtım için yürütülür. Bu komut dosyası commit mesajındaki `[deploy site]`dizesini kontrol eder.

Commit mesajı bu dizeyi içeriyorsa ve commit `dev` içindeyse, siteyi oluşturmak ve dağıtmak için bir 
[GitHub eylemi](./.github/workflows/deploy.yml) tetiklenir. 
Site ve dokümanlar oluşturulacak ve değişiklikler,  [Selenium-CI](https://github.com/selenium-ci/) kullanıcısı tarafından `publish` şubeye commit edilecek.

*Dikkate alınması gereken önemli nokta sitenin kaynak dosyalarının `dev` dizininde olmasıdır ve dağıtılan dosyalar `publish`şubesine gönderilir.*

Site GitHub sayfaları kullanılarak dağıtılır ve bunun yapılandırması repo [ayarlarında](https://github.com/SeleniumHQ/seleniumhq.github.io/settings) görülebilir (eğer bir maintainer`san bağlantıya erişebilmelisin).

Selenium.dev etki alanı https://www.gandi.net/en adresinde yönetilir,eğer erişme ihtiyacınız varsa  size bu konuda yardımcı olabilecek 
[PLC](https://www.selenium.dev/structure/#plc) veya [TLC](https://www.selenium.dev/structure/#tlc) üyelerinden herhangi birine ulaşın.


Herhangi bir nedenle alan yönlendirmesini yeniden ayarlamanız gerekirse, bu  [klavuzu](http://spector.io/how-to-set-up-github-pages-with-a-custom-domain-on-gandi/) izledik
ancak bir etki alanının GitHub sayfalarına nasıl yönlendirileceğini gösteren herhangi bir öğretici/kılavuz yapılmalıdır.   
 


