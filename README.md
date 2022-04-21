### Interní aplikace evidence brigádníků

- Aplikace navrhnutá pro společnost SGInternational pro evidenci brigádníků
- Základní barevný design vychází z logomanuálu a oficiálního webu SGI
- Veškeré grafické podklady včetně simulované funkčnosti byly vytvořeny v aplikaci Adobe XD společnosti Adobe


# Obecná funkčnost aplikace
- aplikace slouží jako ucelený přihlašovací systém na akce/pracovní události
- každý uživatel má ve svěm profilu nastavené role, které mu umožnují provádět určité interakce se systémem
# Landingpage
- po zadání URL adresy se zobrazí stránka se 2 odkazy, směřující na přímé přihlášení a registraci nového uživatele
![] (https://github.com/pslib-cz/2021l4web-app-mockup-starkoss/blob/main/img/uvod-rozcestnik.png)
## Přihlášení
- po kliknutí na tlačítko přihlásit vyskočí podstránka, která bude požadovat zadáná uživatelského jména a hesla
- pod vstupní kolonkou se bude nacházet odkaz na obnovu zapomeného hesla, které se bude odesílat na e-mailovou adresu, přes které je vedeno přihlášení
## Registrace
- při registraci zadává uživatel tyto údaje:
1. vlastní jméno
2. vlastní příjmení
3. datum narození
	+ DD/MM/RRRR
4. trvalé bydliště
	+ Ulice, č.p., město, PSČ
5. telefon
	+ +420 XXX XXX XXX
6. email
7. heslo
8. heslo znovu
- vedle funkčních kolonek bude kolonka pro nahrání profilové fotografie
# Hlavní stránka
- na hlavní stránce se budou nacházet příspěvky od zaměstnavatele sloužící k předání informací zaměstnancům
## POV - zaměstnanec
- zaměstnanec nemá povolenou interakci s příspěvky
- vidí pouze nadpis, text sdělení a datum přidání
## POV - admin
- admin může po kliknutí na ikonku v pravém horním rohu příspěvku příspěvek editovat
- zbytek vidí stejný jako běžný uživatel
- v pravém dolním rohu se nachází ikonka pro vytvoření nového příspěvku
### Vytvoření a úprava sdělení
- podstránka pro vytváření sdělení se skládá ze 2 funkčních polí
	+ pole pro nadpis textu
	+ samotný text
- pod těmito poly se nachází 3 tlačítka
	+ zelené s uložením úprav/přidáním příspěvku
	+ šedé s funkcí zrušení vytváření/úprav beze změny
	+ červené pro odstranění příspěvku
# Seznam akcí
- v náhledu se bude zobrazovat přehled akcí v šedých blocích
- každý blok bude obsahovat tyto informace:
1. Název události
2. Podrobnější popis události
3. Místo konání události
4. Datum konání události
5. Čas konání události
6. Poznámku od zaměstnavatele
7. Počet obsazených/volných pozic
- body 3 až 7 budou doplněny o piktogram dle návrhu
- v pravém dolním rohu se bude nacházet tlačítko pro rozkliknutí podrobností o akci
## POV - zaměstnanec
- zaměstnanec může pouze prohlížet informace a přejít na detail akce
## POV - admin
- admin má stejný pohled jako zaměstnanec s rozdílem možnosti vytvoření nové události
### Vytvoření nové události
- budou dostupné funkční kolonky dle předchozího zadání v sekci "Seznam akcí"
- body 4. a 5. budou mít v pravém rohu možnost funkčního interakčního kalendáře/hodin
- limit účastníků se nastavuje ve 3 oddělených boxech s možností manipulace s hodnotami pomocí postraních šipek
- limit účastníků nesmí být nikdy nevyplněn, vždy musí být uvedena alespoň 0
- všechny hodnoty, krom bodu 2 a 6 jsou povinné a nezbytné k uložení události.
- vedle nastavení limitů je možné zaškrtnout možnosti 
	+ skrýt limit před uživateli (v takovém případě se nezobrazí v detailu akce)
	+ bez limitu účastníků (v takovém případě políčka zešednou a nepůjde do nich psát)
# Moje akce
- sekce, do kterých se přesune událost po zaškrtnutí možnosti v detailu akce o potvrzení účásti
# Detail akce
- na detailu akce budou viditelné stejné informace jako na výčtu na stránce "Seznam akcí"
- pod tímto bude trojsloupcová buňka ukazující počty volných/obsazených míst
## POV - zaměstnanec
- zaměstnanec uvidí možnost přihlásit se pod určitou skupinou
	+ brigádník
	+ hosteska
	+ supervizor
- zaměstanci jsou tyto role přidělovány adminem v sekci "Profil"
- pokud se zaměstnanec pokusí přihlásit do kategorie, která nekoresponduje s jeho rolí, zobrazí se chybová hláška přes 20 % obrazovky s nápisem informujícím o chybě role
- pokud je akce obsazená, může se zaměstnanec přihlásit jako náhradník
	+ po kliknutí na tuto možnost se v případě uvolnění pozice odešle informativní e-mail o této skutečnosti uživateli
- po kliknutí na přihlášení se na akci jako XXX zmízí tlačítka s přihlášením a objeví se nové
	+ odhlášení z akce (po kliknutí je stále evidován v databázi s označením odhlášený, má možnost se ještě znovu přihlásit)
	+ ohlásit pozdní příchod (vygenerován automatický e-mail nesoucí informace o události, informace o brigádníkovi a následně je na zaměstnanci, aby doplnil míru spoždění, důvod a odeslal vedení)
## POV - admin
- admin nemá možnost přihlášení na akci
- má k dispozici funkční tlačítka
	+ Editovat - přesměruje na stejný formulář jako při tvorbě události nové
	+ Stop/Start přihlášení - může manuálně pozastavit x spustit přihlašování na akci (již přihlášené to neovlivní)
	+ Odstranit - zruší událost, automatický e-mail informuje přihlášené zaměstnance
- admin na detailu vidí seznam již přihlášených uživatelů s možností filtrace jednotlivých sekcí na základě textu v tomto rozsahu:
	+ Příjmení
	+ Jméno
	+ Role (brigádník, hosteska, supervizor - nastvati omezení)
	+ Poslední změna (DD-MM-RRR_HH:MM:SS)
	+ Stav (potvrzeno, zrušeno)
	+ Datum narození (uživatel může být příliš mladý pro tuto akci)
	+ Telefon
- u každého řádku je na jeho konci červené pole s křížkem k odebrání z akce
	+ po kliknutí odešle e-mail s informacemi o akci a o zamítnutí jeho účasti
# Profil
- v sekci profilu může uživatel vizuelně zkontrolovat zadané údaje
## POV - zaměstnanec
- zaměstnanec má možnost po kliknutí na tlačítko editovat upravovat tyto údaje:
	+ Trvalé bydliště
	+ Telefon
	+ Kontaktní e-mail (nikoliv přihlašovací)
	+ profilovou fotografii
- nemůže editovat své role ani vodět role, které mu nebyly přiděleny
## POV - admin
- může editovat všechny informace
- má na výběr ze 4 rolí
	+ brigádník
	+ hosteska
	+ supervizor
	+ admin
- první 3 mohou být aktivní spolu
- admin musí být aktivní vždy samostatně
- role se aktivuje kliknutím na ni (změní barvu ze šedé na barevnou) a následným uložením
- kromě tlačítek na editaci a uložení může pomocí tlačítka smazat odstranit uživatele z datebáze (nastavit dvojité ověření - jse si opravdu jistí, že chcete profil odstranit? - vyskakovací hláška stejně jako výše)
- profil admina nelze odstranit - aby nedošlo k tomu, že nebude žádný admin
# Správa účtů
- přístup pouze admin
- seznam obsahující informace s filtrem stejně jako na detailu akce
	+ Příjmení
	+ Jméno
	+ Role
	+ Datum narození
	+ Telefon
	+ E-mail
	+detail (odkaz na profil zaměstnance s možností úpravy)
- pod seznamem tlačítko s možností vytvoření nového účtu
# Změna hesla
- stránka se 3 funkčními políčky
	+ staré heslo
	+ nové heslo
	+ nové heslo znovu
- stejný model jako přihlášení
# Zapomenuté heslo
- stránka stejného designu jako předchozí
- 1 funkční pole s požadavkem zadání emailu, na který bude zasláno vygenerované dočasné heslo
- tlačítko odeslat
# Header
- v pravé části tlačítko odhlášení a jméno uživatele (Jméno+Příjmení)
# Navigace
- stacionární v levé části obrazovky
- v horní části logo a tlačítko na sbalení do strany
- pod logem oddělovací čára
- 6 položek navigace
- pod tímto kontakt na manažera - email+telefon
# Footer
- vlevo nahlášení problému - email na správce aplikace
- odkaz na web SGI
- v pravém rohu copyright SGI
