# Top Down Racing – globális scoreboard

## Fájlok
- `index.html` – a játék és a globális Top 10 ranglista
- `supabase_setup.sql` – adatbázistábla és hozzáférési szabályok

## 1. Supabase projekt
1. Nyisd meg a https://supabase.com oldalt, és hozz létre egy ingyenes projektet.
2. A projektben nyisd meg az **SQL Editor** részt.
3. Másold be a `supabase_setup.sql` teljes tartalmát, majd futtasd le.
4. A projekt **Settings / API** (vagy Connect) részén keresd meg a Project URL-t és a publikus `anon` / `publishable` kulcsot.

## 2. HTML beállítása
Nyisd meg az `index.html` fájlt, keresd meg a két sort a `SUPABASE_URL` és `SUPABASE_ANON_KEY` változókkal, és illeszd be a saját projekted adatait:
- `SUPABASE_URL`: a Supabase Project URL
- `SUPABASE_ANON_KEY`: a publikus anon/publishable kulcs

A böngészőbe kizárólag a publikus kulcs kerülhet. **A service_role / secret kulcsot soha ne másold a HTML-be vagy GitHubra.**

## 3. GitHub Pages
1. Töltsd fel az `index.html` fájlt a repository gyökérkönyvtárába.
2. A GitHub repositoryban nyisd meg: **Settings → Pages**.
3. A Build and deployment résznél válaszd a **Deploy from a branch** lehetőséget.
4. Branch: `main`, folder: `/ (root)`, majd Save.
5. A GitHub Pages által megadott címen megjelenik a játék.

## Fontos biztonsági megjegyzés
Ez egy egyszerű, publikus, bejelentkezés nélküli ranglista. A böngészőből érkező pontszámot bárki módosíthatja, és automatizált beküldésekkel vissza is lehet élni. Az RLS szabályok korlátozzák az elérhető műveleteket és az adattartományt, de **nem igazolják, hogy a pontszámot valóban a játékban érték el**. Komoly, csalásálló ranglistához szerveroldali pontszám-ellenőrzésre (például Supabase Edge Function), beküldési korlátozásra és lehetőleg felhasználói azonosításra van szükség.
