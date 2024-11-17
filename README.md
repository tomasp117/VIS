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
