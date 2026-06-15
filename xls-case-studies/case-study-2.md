📦 Case Study 02 — Inventory Management in Excel

🎯 Cíl projektu

Cílem této mini case study bylo procvičit:
Excel tabulky (Ctrl + T)
filtrování dat
funkci XLOOKUP()
podmíněné výpočty pomocí KDYŽ()
structured references
práci s business logikou
kombinaci více technik v jednom workflow

📁 Dataset
Tabulka produktů
Produkt	Kategorie	Ks	Cena	Hodnota skladu	Status
Notebook HP	IT	12	18500	222000	OK
Myš Logitech	IT	3	450	1350	LOW STOCK
Kancelářská židle	Nábytek	7	3200	22400	OK
Monitor Dell	IT	2	5900	11800	LOW STOCK
Psací stůl	Nábytek	5	4800	24000	OK
Tiskárna Canon	Elektronika	1	4200	4200	LOW STOCK
Sluchátka Sony	Elektronika	9	2100	18900	OK
Webkamera Logitech	IT	4	1600	6400	LOW STOCK

📁 Lookup tabulka dodavatelů
Kategorie	Dodavatel
IT	TechData
Nábytek	OfficePro
Elektronika	ElectroWorld

📊 Zadání

Byla vytvořena jednoduchá skladová evidence produktů.

Pro každý produkt bylo potřeba:

spočítat hodnotu skladu,
určit stav zásob,
dohledat dodavatele podle kategorie,
filtrovat rizikové produkty.

🧮 Použité vzorce

1️⃣ Výpočet hodnoty skladu
Vzorec
=[@Ks]*[@Cena]
Výsledek
Produkt	Hodnota skladu
Notebook HP	222000
Myš Logitech	1350
Monitor Dell	11800

2️⃣ Status skladu
Vzorec
=KDYŽ([@Ks]<5;"LOW STOCK";"OK")
Logika
Ks	Výsledek
< 5	LOW STOCK
≥ 5	OK
Výsledek
Produkt	Ks	Status
Myš Logitech	3	LOW STOCK
Monitor Dell	2	LOW STOCK
Tiskárna Canon	1	LOW STOCK

3️⃣ Dohledání dodavatele pomocí XLOOKUP()
Vzorec
=XLOOKUP([@Kategorie];Tabulka2[Kategorie];Tabulka2[Dodavatel];"neznámý";0)
Výsledek
Kategorie	Dodavatel
IT	TechData
Nábytek	OfficePro
Elektronika	ElectroWorld

4️⃣ Filtrování rizikových produktů
Použité filtry
pouze produkty se statusem LOW STOCK
filtrování podle kategorií
filtrování podle nízkého počtu kusů
Výsledek
Produkt	Kategorie	Ks	Status
Myš Logitech	IT	3	LOW STOCK
Monitor Dell	IT	2	LOW STOCK
Tiskárna Canon	Elektronika	1	LOW STOCK
Webkamera Logitech	IT	4	LOW STOCK

🔄 Procvičené workflow
Kaskádové filtrování

Příklad:

Status = LOW STOCK
→ Kategorie = IT
Výsledek
Produkt	Kategorie	Ks
Myš Logitech	IT	3
Monitor Dell	IT	2
Webkamera Logitech	IT	4

🧠 Co jsem se naučil
rozdíl mezi SVYHLEDAT() a XLOOKUP()
proč je XLOOKUP() flexibilnější
používání structured references v tabulkách
propojení více tabulek pomocí lookup funkcí
filtrování dat podle business podmínek
práci s moderním Excel workflow
základní inventory management logiku

🛠 Použité funkce a nástroje
XLOOKUP()
KDYŽ()
Excel Tables (Ctrl + T)
Filtry
Structured References

🔗 SQL mindset
Lookup logika
SELECT p.produkt,
       p.kategorie,
       d.dodavatel
FROM produkty p
LEFT JOIN dodavatele d
ON p.kategorie = d.kategorie;
Filtrování LOW STOCK
SELECT *
FROM produkty
WHERE ks < 5;

🚀 Výsledek

Tato case study simulovala základní skladový reporting a ukázala:

lookup → výpočet → business pravidla → filtrování → insight

Projekt připomíná reálné workflow:

inventory managementu
procurement reportingu
controllingu
business analytiky
Power BI dashboardingu
