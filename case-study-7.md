📊 Case Study 07 — Dynamic KPI Reporting & Lookup Dashboard
🎯 Cíl projektu

Cílem této mini case study bylo procvičit:

Excel Tables (Ctrl + T)
structured references
INDEX() + POZVYHLEDAT()
IFS() a business logiku
SUBTOTAL()
AGGREGATE()
SOUČIN.SKALÁRNÍ()
dynamické oblasti pomocí POSUN()
parametrické výpočty
mini dashboard workflow

📁 Dataset
ID	Produkt	Kategorie	Region	Tržba	Náklady
101	Notebook	Elektronika	Praha	85000	62000
102	Monitor	Elektronika	Brno	42000	31000
103	Myš	Příslušenství	Ostrava	12000	5000
104	Klávesnice	Příslušenství	Praha	18000	9000
105	Tiskárna	Kancelář	Brno	35000	28000
106	Router	Síť	Ostrava	26000	15000
107	SSD Disk	Komponenty	Praha	47000	32000
108	Webkamera	Příslušenství	Brno	16000	7000

✅ 1️⃣ Výpočet marže

Vzorec:

=([@Tržba]-[@Náklady])/[@Tržba]

Výsledek:

výpočet procentuální marže
použití structured references
automatické rozkopírování v Excel Table

✅ 2️⃣ Business status pomocí IFS()

Business pravidla:

TOP → marže > 30 % A tržba > 40000
RIZIKOVÝ → marže < 20 %
jinak STANDARD

Vzorec:

=IFS(A([@Marže]>0,3;[@Tržba]>40000);"TOP";[@Marže]<0,2;"RIZIKOVÝ";PRAVDA;"STANDARD")

Výsledek:

Produkt	Status
SSD Disk	TOP
ostatní	STANDARD

✅ 3️⃣ Dynamický produktový lookup

Vybraný produkt:

Notebook

Použité funkce:

INDEX()
POZVYHLEDAT()

Příklad:

=INDEX(Tabulka1[Region];POZVYHLEDAT($K$2;Tabulka1[Produkt];0))

Dashboard automaticky vrací:

kategorii
region
tržbu
náklady
marži
status

podle zvoleného produktu.

✅ 4️⃣ Viditelné tržby pomocí SUBTOTAL()

Vzorec:

=SUBTOTAL(109;Tabulka1[Tržba])

Význam:

9 = SUMA
109 = ignoruje skryté řádky

Použití:

filtrování reportů
dashboard KPI
interaktivní reporting

✅ 5️⃣ Počet TOP produktů pomocí SOUČIN.SKALÁRNÍ()

Vzorec:

=SOUČIN.SKALÁRNÍ((Tabulka1[Status]="TOP")*1)

Význam:

převod PRAVDA/NEPRAVDA → 1/0
počítání podle podmínky bez pomocného sloupce

Výsledek:

1

✅ 6️⃣ Průměr marže pomocí AGGREGATE()

Vzorec:

=AGGREGATE(1;7;Tabulka1[Marže])

Význam:

1 = PRŮMĚR
7 = ignorovat skryté řádky a chyby

Použití:

robustní reporting
práce s filtrovanými daty
KPI monitoring

✅ 7️⃣ Dynamický součet posledních X položek

Parametr:

Počet posledních položek = 3

Vzorec:

=SUMA(POSUN(Tabulka1[[#Záhlaví];[Tržba]];POČET2(Tabulka1[Tržba])-K18+1;0;K18;1))

Výsledek:

89000

Význam:

dynamická oblast
parametrické výpočty
práce s POSUN()
automatické rozšíření při přidání dat

🧠 Co jsem se naučil
INDEX() + POZVYHLEDAT() je flexibilnější než SVYHLEDAT()
structured references zlepšují čitelnost vzorců
SUBTOTAL() reaguje na filtry
AGGREGATE() umí ignorovat chyby i skryté řádky
SOUČIN.SKALÁRNÍ() zvládne logické výpočty bez pomocných sloupců
POSUN() umožňuje vytvářet dynamické oblasti
Excel může fungovat jako jednoduchý analytický dashboard

🛠 Použité nástroje
Excel Tables (Ctrl + T)
Structured References
INDEX()
POZVYHLEDAT()
IFS()
A()
SUBTOTAL()
AGGREGATE()
SOUČIN.SKALÁRNÍ()
POSUN()
POČET2()

🔗 BI mindset

Tato case study simuluje jednoduchý analytický dashboard.

Podobný princip se používá v:

sales reportingu
KPI monitoringu
controllingu
Power BI dashboardech
business reportingu
interaktivních filtrech

🚀 Výsledek

Pomocí pokročilých funkcí Excelu jsem vytvořil:

dynamický lookup dashboard
business logiku produktů
KPI reporting
filtrovatelné agregace
parametrické výpočty
dynamickou práci s daty

a procvičil si workflow podobné reálné práci junior data analytika.
