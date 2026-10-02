# ByMarian Studio

Oficiální statický web značky na https://bymarianstudio.cz. Prezentace studia, přehled aplikací a rozcestníky podpory a zásad ochrany soukromí.

## Struktura

- `index.html` — úvod, aplikace ve vývoji a kontakt.
- `apps/index.html` — přehled CCM a Trail Manager.
- `support/index.html` — obecná podpora a e-mail.
- `privacy/index.html` — rozcestník budoucích zásad aplikací a informace o webu.
- `assets/styles.css` — společný responzivní vzhled.
- `404.html` — chybová stránka GitHub Pages.
- `CNAME` — vlastní doména `bymarianstudio.cz`.
- `.nojekyll` — publikování bez zpracování Jekyllem.
- `robots.txt`, `sitemap.xml` — podpora indexování.

Pouze HTML a CSS, bez JavaScriptu, npm, buildu, backendu, externích fontů, analytiky a cookies přidaných webem. Hosting může zpracovávat technické údaje o požadavcích.

## Lokální zobrazení

Otevřete `index.html` v prohlížeči. Pro náhled adres jako `/apps/` lze volitelně použít:

```sh
python -m http.server 8000
```

Otevřete http://localhost:8000. Python není závislostí webu. Stránku 404 ověřujte přes HTTP; používá odkazy od kořene webu. Python server ji automaticky nepoužívá pro neexistující cesty.

## GitHub Pages

Vlastník nastaví v GitHub **Settings → Pages** zdroj **Deploy from a branch**, větev `main` a složku `/ (root)`. Není nutný vlastní workflow ani build příkaz. Po zapnutí Pages se změny publikují pushem do `main`.

Doména je připravená v `CNAME`. Vlastník samostatně nastaví DNS u ACTIVE24, ověří doménu a zapne **Enforce HTTPS**, až bude certifikát dostupný. Samotný `CNAME` DNS ani hosting neaktivuje. Metadata a sitemap počítají s finální doménou. Před spuštěním ověřte přesměrování a HTTPS. DNS, Search Console a Play Console nejsou součástí implementace.

## Úpravy obsahu

Upravujte přímo HTML soubory a `assets/styles.css`. Navigace a patička jsou záměrně krátké a kopírované; změny přeneste do všech pěti HTML souborů. Přehled aplikací je na Home i Apps.

## Přidání aplikace

1. Vytvořte například `apps/ccm/index.html` pro stabilní `/apps/ccm/`. Doplňte ověřené informace a skutečný Google Play odkaz.
2. Vytvořte `support/ccm/index.html` pro `/support/ccm/`.
3. Vytvořte `privacy/ccm/index.html` pro `/privacy/ccm/`. Zásady musí odpovídat skutečnému zacházení aplikace s daty.
4. Pro Trail Manager použijte slug `trail-manager`. URL po vložení do Google Play neměňte.
5. Propojte nové stránky z Apps, Support a Privacy. Neodkazujte nepublikované stránky a stav „In development“ změňte až po vydání.
6. Hlubší stránky potřebují cestu ke stylům a hlavní navigaci `../../`. Doplňte vlastní title, description, canonical a Open Graph URL a správné `aria-current`.
7. Publikované URL přidejte do `sitemap.xml`.

Před pushem ověřte odkazy, mobilní i desktopové zobrazení, klávesnici, focus a `git diff --check`. Web nemá animace. Zásady aplikací zatím nejsou publikované a rozcestník je nenahrazuje. Favicon není přidána, aby provizorní grafika nepůsobila jako oficiální logo.
