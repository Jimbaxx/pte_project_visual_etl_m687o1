---
project_id: 2026-LG-02
supervisor: Gergely LABORCI
tags: [typescript, svelte, tauri, etl, desktop]
status: draft
---
# Projekt outline

## Cél
Lokális-első vizuális ETL alkalmazás, amelyben a felhasználó csomópontokból álló irányított gráfként épít fel, futtat és exportál adatfeldolgozási folyamatot, a forrásadat helyi gépen tartásával.

## Probléma
Helyi fájlokból és API-kból érkező adatot gyakran kell tisztítani, összefésülni, transzformálni és exportálni, mielőtt más rendszerben használható lenne.

## Hatókör (kötelező mag)
- Drag and drop vászon irányított élekkel
- Források: CSV, JSON, XML, API
- Adatstruktúrák: skalár, skalártömb, objektum, objektumtömb; sémafelismerés mintasorokból
- Node-ok: szűrő, mezőkivetítés/átnevezés, join/merge közös kulccsal, csoportosítás (összeg, átlag, darab)
- Egyedi JS/TS node izolált sandboxban
- DAG végrehajtás topológiai sorrendben, többbemenetes node-oknál minden bemenet megvárásával
- Node-onkénti előnézet, exportálható eredmény, érthető hibaüzenetek (típusütközés, hibás konfiguráció, kör)
- 50–100 ezer soros fájl feldolgozása összeomlás nélkül

## Nem hatókör (egyelőre)
<!-- TODO: priorizálás után. Jelöltek: workflow mentés/verziózás, adatbázis-források, sablonok, hitelesítési/licencszerver -->

## Kutatási kérdések
1. Sandbox-megoldások összehasonlítása és a választott izoláció indoklása korlátokkal
2. Adattípus- és sémamodell, port-kompatibilitás, hiányzó/hibás értékek
3. Végrehajtó függőségi, ütemezési és hibaszemantikája (aszinkron, többbemenetes node-ok)
4. Nagy fájlok stratégiája memória- és teljesítménykorlátokkal

## Technológia
Strict TypeScript, Svelte 5 (SvelteKit), Svelvet vagy saját SVG/canvas szerkesztő, Tauri desktop app vagy SvelteKit + Bun PoC.

## Kockázatok
<!-- TODO -->
