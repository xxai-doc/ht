<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

Li rekòmande enstale nodejs, [direnv](https://direnv.net) , [pen an](https://github.com/oven-sh/bun) premye, ak Lè sa a `direnv allow` apre ou fin antre nan anyè a ( [.envrc a](https://github.com/xxai-art/doc/blob/main/.envrc) pral egzekite otomatikman apre ou fin antre nan anyè a).

Siyifikasyon an se: tradiksyon Chinwa an Japonè, Koreyen, Angle, tradiksyon Angle nan tout lòt lang. Si ou vle sèlman sipòte Chinwa ak angle, ou ka jis ekri `zh: en` .

Siyifikasyon an se: tradiksyon Chinwa an Japonè, Koreyen, Angle, tradiksyon Angle nan tout lòt lang. Si ou vle sèlman sipòte Chinwa ak angle, ou ka jis ekri `zh: en` .

* [kòd front-end](https://github.com/xxai-art/web)
* [Pake lang pou sit la an antye](https://github.com/xxai-art/web/tree/main/i18n)
* [Pake lang pou modil login](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Sitwèb Dokimantasyon ki gen plizyè lang](https://github.com/xxai-doc)

Lang pwogramasyon front-end la se [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , ki ajoute kèk karakteristik ki baze sou sentaks coffeescript, gade [./coffee_plus.md](./coffee_plus.md) .

## Entènasyonalizasyon sit entènèt ak dokiman yo

Bati sou 3 pwojè sa yo

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  Sifiks la se `.mdt` , ou ka sèvi ak sentaks ki sanble ak `<+ ./coffee_plus/import.js>` pou fè referans ak dosye ekstèn, epi jenere markdown ak sifiks `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  Tradiksyon Markdown pa pral tradui kòd ak lyen, epi yo pral kache fraz tradui yo. Si yo modifye tradiksyon an men tèks orijinal la pa modifye, egzekite li ankò pa pral ranplase modifikasyon tradiksyon an.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  Fichye lang pou tradui sit wèb `yaml` pwodwi yo.

### Dokiman Tradiksyon Otomatik Enstriksyon

Gade depo kòd [xxai-art/doc](https://github.com/xxai-art/doc)

Li rekòmande enstale nodejs, [direnv](https://direnv.net) , [pen an](https://github.com/oven-sh/bun) premye, ak Lè sa a `direnv allow` apre ou fin antre nan anyè a ( [.envrc a](https://github.com/xxai-art/doc/blob/main/.envrc) pral egzekite otomatikman apre ou fin antre nan anyè a).

Pou evite gwo baz kòd tradui nan dè santèn de lang, mwen te kreye yon baz kòd separe pou chak lang ak kreye yon òganizasyon pou estoke baz kòd la.

Mete varyab anviwònman an `GITHUB_ACCESS_TOKEN` ak Lè sa a, kouri [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) pral otomatikman kreye repozitwa kòd la.

Natirèlman, ou ka tou mete l 'nan yon baz kòd.

Referans script tradiksyon [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

Kòd script la entèprete jan sa a:

[bunx](https://bun.sh/docs/cli/bunx) se yon ranplasman pou npx, ki se pi vit. Natirèlman, si ou pa gen pen enstale, ou ka itilize `npx` pito.

`bunx mdt zh` rann `.mdt` nan anyè zh kòm `.md` , gade 2 fichye ki lye anba a

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` se kòd debaz pou tradiksyon (si ou gen sèlman `nodejs` enstale, men `bun` ak `direnv` pa enstale, ou ka kouri tou `npx i18n` pou tradui).

Li pral analize [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) , konfigirasyon `i18n.yml` nan dokiman sa a se jan sa a:

```
en:
zh: ja ko en
```

Siyifikasyon an se: tradiksyon Chinwa an Japonè, Koreyen, Angle, tradiksyon Angle nan tout lòt lang. Si ou vle sèlman sipòte Chinwa ak angle, ou ka jis ekri `zh: en` .

Dènye a se [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , ki ekstrè kontni ki genyen ant tit prensipal la ak premye soustit `README.md` chak lang pou jenere yon antre `README.md` . Kòd la trè senp, ou ka gade li tèt ou.

Google API itilize pou tradiksyon gratis. Si ou pa kapab jwenn aksè nan Google, tanpri konfigirasyon epi mete yon proxy, tankou:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Script tradiksyon an pral jenere yon kachèt tradui nan anyè `.i18n` , tanpri tcheke li ak `git status` epi ajoute li nan repozitwa kòd la pou evite tradiksyon repete.

Tanpri kouri `bunx i18n` chak fwa ou modifye tradiksyon an pou mete ajou kachèt la.

Si tèks orijinal la ak tradiksyon an modifye an menm tan, kachèt la pral konfonn, kidonk si ou vle modifye, ou ka sèlman modifye youn, epi kouri `bunx i18n` pou mete ajou kachèt la.
