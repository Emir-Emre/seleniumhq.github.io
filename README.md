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
The site and docs will be built, and the changes will be committed to the branch `publish` 
by the user [Selenium-CI](https://github.com/selenium-ci/).

*What is important to take into account is that the source files for the site are in the `dev`
branch, and the files that get deployed are pushed to the `publish` branch.*

The site is deployed using GitHub pages, and the configuration for this can be seen at the
repo [settings](https://github.com/SeleniumHQ/seleniumhq.github.io/settings) (if you are a maintainer
you should be able to access the link).

The selenium.dev domain is managed at https://www.gandi.net/en, if you need access to it, reach out to
any of the [PLC](https://www.selenium.dev/structure/#plc) or [TLC](https://www.selenium.dev/structure/#tlc)
members, who can help you with that.

If for any reason, you need to setup the domain redirection again,
we followed this [guide](http://spector.io/how-to-set-up-github-pages-with-a-custom-domain-on-gandi/),
but any tutorial/guide showing how to redirect a domain to GitHub pages should do.   
 


