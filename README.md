# Vision
## Proč
Průběh a příprava turnaje byla doposud řešena manuálně a většina informací se muselo manuálně zadávat z papíru do dokumentů.
## Co
Je třeba vytvořit webovou aplikaci pro zápis utkání, správu týmů a systém pro usnadnění chodu turnaje.
Při posledním turnaji, se musely zípisy utkání nosit do klubovny pro následné zapsaní do tabulek a to výrazně zdelšilo a znepříjemnilo průběh turnaje.
## Kdo
- Nepřihlášený uživatel
  - Bude si moct prohlídnout průběh celého turnaje, jako například, statistiky a zápasy
- Pořadatel (zapisovatel)
  - Nebude dále používat papírové zápisy, ale přejde na online zápis
  - Ulehčí se tím jak samotný zápis tak i chod turnaje a nebude třeba čekat na výsledky než budou doneseny pro ruční zápis do systému
- Trenér
  - Bude si moct spravovat info o svém týmu a hráčích
  - Bude mít stále po ruce časy a místa zápasů
- Správce systému
  - V případě nějaké chyby bude mít správce možnost upravit a nebo dopsat data
  - Bude mít možnost spravovat celý chod turnaje
## Kdy
Systém najde využití, když budou chtít kluby a pořadatelé turnaje ulehčit a zpřehlednit chod celého turnaje
## Jak
Projekt bude realizován pomocí Agile metodologie, konkrétně skrze framework Scrum. Tento přístup umožní flexibilní a iterativní vývoj, kde každý sprint přináší konkrétní výsledky a produkty.

# Funkční specifikace
## Use case diagram
![Use case diagram (1)](https://github.com/user-attachments/assets/8a3af26c-5956-48c4-aec1-099126b2648b)

## Scénaře
- ### 1. scénář
  - Název: Trenér přidá do nového hráče
  - Aktéři: Trenér
  - Vstupní podmínky:
    - Trenér je přihlášený
  - Spouštěč:
    - Trenér stikne tláčitko pro spřávu hráčů
  - Úspěšný scénář:
    - Trenér přejde na stránku pro správu týmu
      - Načtení informací o týmu
    - Trenér vybere možnost pro správu hráčů
      - Načtení hráčů
    - Trenér klikne na tlačítko pro přidání nového hráče
      - Zobrazení formuláře
    - Trenér vyplní potřebné údaje
    - Trenér potvrdí přidání hráče
      - Validace formuláře
    - Přidání hráče do systému
    - Přidání hráče do týmu
    - Zobrazení potvrzení
- ### 2. scénář
  - Název: Zapisovatel zaznamená průběh zápasu
  - Aktéři: Zapisovatel
  - Vstupní podmínky:
     - Zapisovatel je přihlášený
     - Zápas, který má být zaznamenán, existuje v systému a je ve stavu msNone a nebo msPending
  - Spouštěč:
      - Zapisovatel klikne na tlačítko pro kontrolu a začátek zápasu.
  - Úspěšný scénář: 
      - Zapisovatel přejde na stránku pro seznam zápasů.
        - Načtou se zápasy
      - Zapisovatel vyhledá požadovaný zápas pomocí filtru (např. podle čísla utkání)
        - Zobrazí se podrobnosti o zápasu
      - Zapisovatel klikne na tlačítko pro zápis utkání
        - Zobrazí se formulář pro zápis utkání
      - Zapisovatel zaznamená góly, fauly a případné poznámky
      - Po vypršení časomíry zapisovatel zkontroluje data a uloží zápas
        - Uloží se údaje o zápasu
        - Změní se stav utkání na msDone
- ### 3. scénář
  - Název: Trenér hlasuje o nejlepším hráči turnaje
  - Aktéři: Trenér
  - Vstupní podmínky:
    - Trenér je přihlášený
    - Hlasovací okno je otevřené (systém umožňuje hlasování)
  - Spouštěč:
    - Trenér klikne na tlačítko pro hlasování o nejlepšího hráče
  - Úspěšný scénář:
    - Trenér přejde na stránku pro hlasování
    - Vybere možnost pro hlasování o nejlepšího hráče
      - Zobrazí se seznam hráčů
    - Trenér vybere svého favorita ze seznamu
    - Trenér odešle hlas
      - Zkontroluje se zda trenér již nehlasoval
    - Zaznamenání hlasu
    - Systém zobrazí potvrzení o úspešném hlasování.
## Aktivitní diagramy
  - ### 1. scénář
![Blank diagram](https://github.com/user-attachments/assets/4c111fd9-c757-4f25-b7cc-b02d96c37fc8)
  - ### 2. scénář
![Blank diagram (2)](https://github.com/user-attachments/assets/81c20129-2576-4344-b7f8-3f284775b4d8)
  - ### 3. scénář
![Blank diagram (3)](https://github.com/user-attachments/assets/26218cb5-23f7-452d-9305-1e60b263b5c8)
# Technická specifikace
## Konceptuální doménový model
![domain_model](https://github.com/user-attachments/assets/b1b3a7f5-8dc3-4416-9ae0-cf449d942048)
## Odhad počtu uživatelů současně pracujících se systémem
|Kategorie uživatelů|Počet současně pracujících uživatelů (peak)|Průměr současně aktivních uživatelů|
|-------------------|--------------------------------------------|----------------------------------|
|Admin              |2                                           |1                                 |
|Recorder           |7                                           |5                                 |
|Coach              |15                                          |7                                 |
|Spectator          |100                                         |30                                |
## Typy interakcí uživatelů současně pracujících se systémem
### Nejčastější interakce:
- Zapisování průběhu zápasu (Recorder):
  - Operace: Vytváření záznamů (Event) a aktualizace zápasu.
  - Náročnost:
    - Výpočetní: Nízká – pouze zápis nových dat.
    - I/O: Vysoká – časté zapisování do databáze během zápasu.
- Prohlížení statistik (Spectators):
  - Operace: Dotazy na statistiky týmů, hráčů, zápasů.
  - Náročnost:
    - Výpočetní: Střední – agregace dat, případně filtrování.
    - I/O: Střední – mnoho paralelních čtení z databáze.
- Správa uživatelů a dat (Admin):
  - Operace: Vytváření/úprava týmů, zápasů, uživatelů.
  - Náročnost:
    - Výpočetní: Nízká – většina operací jsou jednoduché CRUD akce.
    - I/O: Nízká – minimální počet záznamů.
- Hlasování o nejlepším hráči (Coach):
  - Operace: Zápis hlasu do systému.
  - Náročnost:
    - Výpočetní: Nízká – validace jednoho hlasu.
    - I/O: Nízká – zápis malého objemu dat.
### Technologie
- Frontend:
  - React.js
    - V budoucnu možnost rozšíření na mobilní aplikaci (React Native)
- Backend:
  - ASP.NET Core (C#) 
- Databáze:
  - MySQL
- Hostování:
  - Oracle Cloud Free Tier pro backend a databázi a případně i frontend
- Cílové platformy:
  - Web: Primární platforma (prohlížeče).
  - Mobile: Možnost responsivního designu nebo budoucího rozšíření na mobilní aplikaci.
  - Desktop: Nepotřebné, protože web pokryje potřeby uživatelů.
# Wireframes
## Přihlášení
![wireframe_login](https://github.com/user-attachments/assets/00db6335-e747-4254-9489-a401f9a97dac)
## Týmy v kategorii
![wireframe_tymy](https://github.com/user-attachments/assets/a8006499-2722-47ea-b012-469a52db7b60)
## Zápis utkání
![wireframe_zapis](https://github.com/user-attachments/assets/45234020-e298-4aa0-9b92-4af5f22cb854)
# Domain model
## Class diagram
![class_diagram (2)](https://github.com/user-attachments/assets/e4ba2d04-c99e-4619-8bfb-7274e615c15f)
## Sekvenční diagramy
### 1. Přihlášení a přidělení tokenu
![Use case diagram (2)](https://github.com/user-attachments/assets/245858fe-e9b9-44e2-a68a-e6d64567bde9)
### 2. Vytvoření nového zápasu
![Use case diagram (3)](https://github.com/user-attachments/assets/713a159f-928f-4e04-9e47-b53805ef42ec)
### 3. Vytvoření a přidání hráče do týmu
![Use case diagram (4)](https://github.com/user-attachments/assets/aa13edd3-06be-45bb-9d4f-48837ebb48cf)
## Design patterns
V systému momentálně používám:
  - Table module
  - Table Data Gateway (dá se brát i jako Mapper)
  - Identity field

Dodatečně by se dalo ještě přidat Service Layer a Unit of Work pro složitější transakce a ušetření posílaní dat na server.
# Architecture
## Diagram component
### 1. Celý systém
V tomto diagramu komponent jsem zaznačil celý systém jak by měl fungovat a jednotlivé komunikace mezi komponenty. Přidal jsem i Services pro složitější byznys logiku.
![Use case diagram (5)](https://github.com/user-attachments/assets/a606060e-2c0f-478f-a619-f17dcc681eac)
### 2. Přidání hráče do týmu
Tady v tomto diagramu jsem popsal přímo daný use case pro přidání hráče do týmu.
![Use case diagram (6)](https://github.com/user-attachments/assets/f17b5fba-753c-4b71-9102-d433d5494d44)

