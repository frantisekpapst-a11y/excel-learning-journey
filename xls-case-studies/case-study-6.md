# 📊 Case Study 06 — Conditional Formatting for KPI Monitoring

## 🎯 Cíl projektu

Cílem této mini case study bylo procvičit:

- základní podmíněné formátování
- vlastní pravidla pomocí vzorců
- zvýraznění celých řádků
- logiku `A()` a `NEBO()`
- práci s KPI alerty
- vizuální reporting v Excelu

---

# 📁 Dataset

| Produkt | Kategorie | Tržba | Marže | Reklamace |
|---|---|---:|---:|---:|
| Notebook | IT | 45000 | 0,18 | 1 |
| Myš | IT | 1200 | 0,35 | 0 |
| TV | Elektro | 18000 | 0,22 | 3 |
| Lednice | Elektro | 25000 | 0,15 | 6 |
| Tablet | IT | 9000 | 0,12 | 2 |
| Mobil | Elektro | 32000 | 0,28 | 1 |

---

# ✅ Business pravidla

## 1️⃣ High Revenue

Zvýraznit tržby vyšší než 20 000.

```excel
=$C2>20000

Výsledek:

Produkt	Tržba
Notebook	45000
Lednice	25000
Mobil	32000
2️⃣ Low Margin

Zvýraznit marže nižší než 20 %.

=$D2<0,2

Výsledek:

Produkt	Marže
Notebook	0,18
Lednice	0,15
Tablet	0,12
3️⃣ Rizikový produkt

Zvýraznit celý řádek, pokud:

Marže < 20 %
A ZÁROVEŇ
Reklamace > 3

Vzorec:

=A($D2<0,2;$E2>3)

Výsledek:

Produkt	Marže	Reklamace
Lednice	0,15	6
4️⃣ Prioritní produkt

Zvýraznit celý řádek, pokud:

Kategorie = IT
NEBO
Tržba > 30000

Vzorec:

=NEBO($B2="IT";$C2>30000)

Výsledek:

Produkt	Kategorie	Tržba
Notebook	IT	45000
Myš	IT	1200
Tablet	IT	9000
Mobil	Elektro	32000
🧠 Co jsem se naučil
podmíněné formátování nemění hodnoty, pouze vzhled
oblast „Platí pro“ určuje, co se bude formátovat
vzorec určuje, podle čeho se rozhoduje
pro zvýraznění celého řádku je nutné označit celý rozsah tabulky
znak $ zamyká sloupec, ale řádek se může posouvat
A() znamená, že musí platit všechny podmínky
NEBO() znamená, že stačí splnit alespoň jednu podmínku
🛠 Použité nástroje
Podmíněné formátování
Nové pravidlo
Vlastní vzorec
Správce pravidel
A()
NEBO()
Excel Tables
🔗 BI mindset

Tato case study ukazuje, jak lze v Excelu vytvořit jednoduchý vizuální alert systém.

Podobný princip se používá v:

dashboardech
KPI reportech
Power BI
risk monitoringu
sales reportingu
🚀 Výsledek

Pomocí podmíněného formátování jsem vytvořil jednoduchý KPI monitoring, který automaticky zvýrazňuje důležité hodnoty a rizikové produkty bez ručního formátování.
