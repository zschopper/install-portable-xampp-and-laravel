# Laravel környezet beállítása

## Xampp telepítése (portable)

- Böngészőben megnyitjuk a letöltési oldalt: [ApacheFriends.org](https://sourceforge.net/projects/xampp/files/XAMPP%20Windows/)
- A kiválasztott verzió portable változatát letöltjük. A fájlnév  **xampp-portable-windows-x64-8.#.#-#-VS@@.zip**, ahol a # a verziószám elemeit a @ pedig a bináris fájlok fordításához használt Visual Studio verziószáma. _(Számunkra ez utóbbi irreleváns)_
- A letöltött csomagot kibontjuk a főkönyvtárba. _Nem kell külön xampp mappát létrehozni, az archívumban a fájlok már xampp mappában vannak!_
- A xampp\php\php.ini fájlt megnyitjuk szövegszerkesztővel és megkeressük a ```;extension=zip``` tartalmú sort, és kitöröljük a pontosvesszőt a sor elejéről, majd elmentjük és bezárjuk a fájlt.

## Környezeti változók beállítása

- A xampp php mappáját (....xampp\php) a vágólapra másoljuk
- Belépünk a **Vezérlőpult**ba
- Jobboldalt felül a keresőbe beírjuk **környezeti**
- A Környezeti változók beállítása
- Path elemet kijelölni a listáról
- Szerkesztés gomb
- Új
- Beillesztjük a vágólapról a php mappa útvonalát
- Mentés, OK vagy bezárás a vezérőpult ablakaira

## Composer letöltése, beállítása

- Böngészőben megnyitjuk a [GetComposer.org](https://getcomposer.org/download/)-ot.
- A négysoros php szkriptet kimásoljuk vágólapra
- A parancssorban (cmd) belépünk a xampp\php mappába
- Beillesztjük a vágólapon lévő parancsokat
- Az alábbi kódot bemásoljuk a vágólapra és a parancssorba beillesztve végrehajtjuk:

```
echo @php "%~dp0composer.phar" %* > composer.cmd
```

Ezzel kész is a composer.

## Laravel projekt készítése composerrel

A _composer create-project_ parancsával készített projekteknek csinál külön mappát a composer.
Nem kell külön csinálni.

```
composer create-project laravel/laravel <projektnév>
```

## Laravel projekt klónozása githubról

A _git clone_ is készít mappát a projekt neve alapján.

```
git clone <repository url>
```

- A klónozás elkészülte után be kell lépni a projekt mappába
- az .env.example fájlt át kell másolni .env néven. Intézőből Ctrl+C/Ctrl+V után átnevezni a fájlt, vagy parancssorból a következő paranccsal:

```
copy .env.example .env
```

- a vendor mappa csomagjait a következő paranccsal lehet letölteni:

```
composer install
```

- Az alkalmazás kulcsát a következő paranccsal lehet elkészíttetni:

```
@php artisan key:generate --ansi
```

https://getcomposer.org/Composer-Setup.exe
