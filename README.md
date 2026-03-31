# SQLodevzdat
1. Zranitelnost ověřena za pomocí máčknutí uvozovek, na což server reagoval: SQL Chyba: unrecognized token: "'"

2.Struktura a tudíž počet sloupců sem si ověřil za pomoci řádku ' ORDER BY x-- kdy x bylo zvyšující se číslo od 1(1;2;3 a případně by to šlo i dále). Po x=3 mi stránka hodila error, což znamená, že byly pouze 2 sloupce. názvy tabulek jsem vyhledal za pomoci řádku: ' UNION SELECT 1, name FROM sqlite_master WHERE type='table' AND name NOT LIKE 'sqlite_%'-- tím mi to vypsalo potřebné názvy hned vedle volně dostupných údajů 

3. Payload vedoucí k odemknutí dat byl ' UNION SELECT key, value FROM config--

4.  cesta vedla skrze zjištění sestavení databáze po zjištění jmen tabulek a následném použití comandu ' UNION SELECT 1, sql FROM sqlite_master WHERE type='table' AND name='config'-- díky čemu mi databáze vypsala zbytek toho, co jsem potřeboval abych mohl použít payload

5. vlajka: FLAG{Sql_Un1on_M4st3r_S0SE}

