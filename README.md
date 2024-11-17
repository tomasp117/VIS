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
- viz. lucid chart
## Scénaře
- ### 1. scénář
  - Název: Trenér přidá do nového hráče
  - Aktéři: Trenér
  - Vstupní podmínky:
    - Trenér je přihlášený
  - Spouštěč:
    - Trenér stikne tláčitko "Spravovat hráče"
  - Úspěšný scénář:
    - Trenér se přihlásí do systému
    - Přihlášovací údaje byly správné
    - Trenér naviguje na stránku "Můj tým".
    - Načtení informací o tůmu
    - Trenér klikne na tlačítko "Spravovat hráče".
    - Načtení hráčů
    - Trenér klikne na tlačítko "Přidat nového hráče".
    - Zobrazení formuláře
    - Trenér vyplní potřebné údaje
    - Trenér klikne na tlačítko "Přidat hráče"
    - Kontrola formuláře
    - Formulář byl správně vyplněn
    - Přidání hráče do systému
    - Přidání hráče do týmu
- ### 2. scénář
- ### 3. scénář
