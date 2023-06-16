<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

Veb sayt kodunun bir hissəsi açıq mənbədir, tərcüməni optimallaşdırmağa kömək etmək üçün xoş gəlmisiniz.

## ön kod

* [ön kod](https://github.com/xxai-art/web)
* [Bütövlükdə sayt üçün dil paketləri](https://github.com/xxai-art/web/tree/main/i18n)
* [Giriş modulları üçün dil paketləri](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Veb saytının çoxdilli sənədləri](https://github.com/xxai-doc)

Front-end proqramlaşdırma dili [@w5/coffee_plus-](http://npmjs.com/@w5/coffee_plus) dur ki, bu da coffeescript sintaksisinə əsaslanan bəzi funksiyalar əlavə edir, bax [./coffee_plus.md](./coffee_plus.md) .

## Veb saytların və sənədlərin beynəlmiləlləşdirilməsi

Aşağıdakı 3 layihə üzərində qurun

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  Suffiks `.mdt` dir, siz xarici fayllara istinad etmək üçün `<+ ./coffee_plus/import.js>` ilə oxşar sintaksisdən istifadə edə və `.md` şəkilçisi ilə işarələmə yarada bilərsiniz.

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  Markdown tərcüməsi kodları və keçidləri tərcümə etməyəcək və tərcümə edilmiş cümlələri yaddaşda saxlayacaq. Tərcümə dəyişdirilibsə, lakin orijinal mətn dəyişdirilməyibsə, onun yenidən icrası tərcümənin dəyişdirilməsinin üzərinə yazılmayacaq.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  `yaml` tərəfindən yaradılan veb saytları tərcümə etmək üçün dil faylları.

### Sənədlərin Tərcümə Avtomatlaşdırılması Təlimatları

[xxai-art/doc](https://github.com/xxai-art/doc) deposuna baxın

Əvvəlcə nodejs, [direnv](https://direnv.net) və [bun](https://github.com/oven-sh/bun) quraşdırmaq, sonra isə kataloqa daxil olduqdan sonra `direnv allow` proqramını işə salmaq tövsiyə olunur.

Həddindən artıq böyük anbarların yüzlərlə dilə çevrilməməsi üçün hər dil üçün ayrıca kod anbarı yaratdım və bu anbarı saxlamaq üçün bir təşkilat yaratdım.

`GITHUB_ACCESS_TOKEN` mühit dəyişəninin qurulması və sonra [create.github.coffee proqramının](https://github.com/xxai-art/doc/blob/main/create.github.coffee) işə salınması anbarı avtomatik yaradacaq.

Təbii ki, onu anbara da qoya bilərsiniz.

Tərcümə skriptinə istinad [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

Skript kodu aşağıdakı kimi şərh olunur:

[bunx](https://bun.sh/docs/cli/bunx) daha sürətli olan npx-in əvəzidir. Əlbəttə ki, əgər sizdə bun quraşdırılmayıbsa, onun yerinə `npx` istifadə edə bilərsiniz.

`bunx mdt zh` `.mdt` -ni zh kataloqunda `.md` kimi göstərir, aşağıdakı 2 əlaqəli fayla baxın

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` tərcümə üçün əsas koddur (yalnız `nodejs` quraşdırılıbsa, lakin `bun` və `direnv` quraşdırılmayıbsa, tərcümə etmək üçün `npx i18n` də işlədə bilərsiniz).

O, [i18n.yml-i](https://github.com/xxai-art/doc/blob/main/i18n.yml) təhlil edəcək, bu sənəddə `i18n.yml` konfiqurasiyası aşağıdakı kimidir:

```
en:
zh: ja ko en
```

Mənası: Çin dilindən Yapon, Koreya, İngilis dilinə tərcümə, bütün digər dillərə ingiliscə tərcümə. Yalnız Çin və İngilis dilini dəstəkləmək istəyirsinizsə, sadəcə olaraq `zh: en` yaza bilərsiniz.

Sonuncu [gen.README.coffee-](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) dir, o, `README.md` girişini yaratmaq üçün hər bir dilin `README.md` -nin əsas başlığı və ilk altyazısı arasında məzmunu çıxarır. Kod çox sadədir, özünüz baxa bilərsiniz.

Google API pulsuz tərcümə üçün istifadə olunur. Google-a daxil ola bilmirsinizsə, lütfən, proksi konfiqurasiya edin və quraşdırın, məsələn:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Tərcümə skripti `.i18n` qovluğunda tərcümə keşini yaradacaq, lütfən onu `git status` ilə yoxlayın və təkrar tərcümələrin qarşısını almaq üçün kod anbarına əlavə edin.
