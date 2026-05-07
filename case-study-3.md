📊 Case Study 03 — Advanced Filtering in Excel
🎯 Cíl projektu

Cílem této mini case study bylo procvičit:

jednoduché filtrování
rozšířený filtr
logické podmínky AND / OR
export filtrovaných dat
výpočtová kritéria
práci s unikátními hodnotami
databázové myšlení při práci s daty

📁 Dataset
Tabulka zaměstnanců
ID	Jméno	Oddělení	Město	Věk	Plat
1001	Novák	IT	Praha	28	65000
1002	Svoboda	Finance	Brno	41	72000
1003	Dvořák	IT	Brno	37	81000
1004	Král	HR	Ostrava	33	54000
1005	Procházka	IT	Praha	45	92000
1006	Marek	Sales	Brno	29	47000
1007	Černý	Finance	Praha	39	76000
1008	Beneš	IT	Ostrava	31	69000

✅ Procvičené scénáře

1️⃣ Jednoduchý filtr
Zadání

Filtrovat zaměstnance podle:

města
věku
oddělení
výše platu
Použití
textové filtry
číselné filtry
vlastní podmínky
kaskádové filtrování
Příklad
Filtr:
Město = Praha
Výsledek
Jméno	Oddělení	Plat
Novák	IT	65000
Procházka	IT	92000
Černý	Finance	76000

2️⃣ Rozšířený filtr — AND logika
Zadání

Vyfiltrovat zaměstnance:

Oddělení = IT
AND
Město = Brno
AND
Věk > 35
Oblast kritérií
Oddělení	Město	Věk
IT	Brno	>35
Výsledek
Jméno	Oddělení	Město	Věk	Plat
Dvořák	IT	Brno	37	81000

3️⃣ Rozšířený filtr — OR logika
Zadání

Vyfiltrovat zaměstnance:

Město = Praha
OR
Plat > 70000
Oblast kritérií
Město	Plat
Praha	
	>70000
Výsledek
Jméno	Město	Plat
Novák	Praha	65000
Svoboda	Brno	72000
Dvořák	Brno	81000
Procházka	Praha	92000
Černý	Praha	76000

4️⃣ Výpočtová kritéria
Zadání

Filtrovat zaměstnance s:

nadprůměrným platem
nejvyšším platem
nejnižším věkem

🔹 Nadprůměrný plat
Kritérium
=[@Plat]>PRŮMĚR(Tabulka1[Plat])
Průměrný plat
69500
Výsledek
Jméno	Plat
Svoboda	72000
Dvořák	81000
Procházka	92000
Černý	76000

🔹 Nejvyšší plat
Kritérium
=[@Plat]=MAX(Tabulka1[Plat])
Výsledek
Jméno	Plat
Procházka	92000

🔹 Nejnižší věk
Kritérium
=[@Věk]=MIN(Tabulka1[Věk])
Výsledek
Jméno	Věk
Novák	28

5️⃣ Export výsledků
Použití

Možnost:

Kopírovat jinam
Výsledek

Filtrovaná data byla exportována:

na samostatný list
bez přepsání zdrojových dat
s možností další analýzy

6️⃣ Unikátní hodnoty
Použití

Možnost:

Bez duplicitních záznamů
Výsledek
Unikátní města
Město
Praha
Brno
Ostrava

🧠 Co jsem se naučil
rozdíl mezi jednoduchým a rozšířeným filtrem
logiku AND / OR v Excelu
práci s oblastí kritérií
databázový přístup k filtrování dat
podobnost s SQL (WHERE, OR, AND, DISTINCT)
práci s dynamickými kritérii pomocí vzorců
export filtrovaných dat bez zásahu do zdroje

🛠 Použité funkce a nástroje
Filtr
Rozšířený filtr
PRŮMĚR()
MAX()
MIN()
Bez duplicitních záznamů
Excel Tables (Ctrl + T)
🔗 SQL mindset
AND logika
SELECT *
FROM employees
WHERE oddeleni = 'IT'
  AND mesto = 'Brno'
  AND vek > 35;
OR logika
SELECT *
FROM employees
WHERE mesto = 'Praha'
   OR plat > 70000;
DISTINCT logika
SELECT DISTINCT mesto
FROM employees;

🚀 Výsledek

Tato case study simulovala základní analytickou práci s HR daty a ukázala, jak lze v Excelu vytvářet pokročilé datové výběry bez použití SQL nebo databáze.

Hlavní přínos:

filtrace → logika → výběr dat → export → analytický insight

Tento princip je velmi podobný práci:

v SQL
v Power BI
v databázových systémech
v HR reportingu
v business analytice
