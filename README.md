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

### [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

`.mdt` şəkilçisi ilə işarələmə şablonu `<+ ./coffee_plus/import.js>` ilə oxşar sintaksisi olan xarici fayllara istinad edə bilər.

[@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

Markdown tərcüməsi kodları və keçidləri tərcümə etməyəcək və tərcümə edilmiş cümlələri yaddaşda saxlayacaq. Tərcümə dəyişdirilibsə, lakin orijinal mətn dəyişdirilməyibsə, onun yenidən icrası tərcümənin dəyişdirilməsinin üzərinə yazılmayacaq.

[@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

`yaml` tərəfindən yaradılan veb saytları tərcümə etmək üçün dil faylları.
