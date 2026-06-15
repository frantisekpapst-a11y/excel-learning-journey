# 📦 Case Study 04 – E-commerce Performance Analytics

## 🎯 Cíl projektu

Cílem této mini case study bylo procvičit pokročilé použití funkce `SOUČIN.SKALÁRNÍ()` při analýze objednávek v e-commerce datasetu.

Procvičeno:

- `SOUČIN.SKALÁRNÍ()`
- podmíněné počítání
- podmíněné sčítání
- logika `AND`
- logika `OR`
- práce s `TRUE/FALSE`
- převod logických hodnot na `1/0`
- structured references v Excel tabulkách
- business KPI výpočty bez pomocných sloupců

---

# 📊 Dataset

| Objednávka | Kanál | Kategorie | Tržba | Marže % | Vráceno | Priorita |
|---|---|---|---:|---:|---:|---:|
| 1001 | Ads | Notebook | 45000 | 0,18 | 0 | 1 |
| 1002 | Organic | Mobil | 18000 | 0,25 | 0 | 1 |
| 1003 | Ads | Notebook | 52000 | 0,12 | 1 | 0 |
| 1004 | Referral | TV | 27000 | 0,31 | 0 | 1 |
| 1005 | Organic | Notebook | 61000 | 0,22 | 0 | 1 |
| 1006 | Ads | Mobil | 15000 | 0,15 | 1 | 0 |
| 1007 | Referral | Notebook | 33000 | 0,27 | 0 | 1 |
| 1008 | Organic | TV | 29000 | 0,19 | 0 | 1 |

---

# 🧠 Business zadání

Analyzovat objednávky e-shopu a spočítat základní KPI pomocí funkce `SOUČIN.SKALÁRNÍ()` místo klasických funkcí jako `SUMIF()`, `SUMIFS()` nebo `COUNTIFS()`.

---

# ✅ Úkol 1 – Počet objednávek s marží nad 20 %

## Zadání

Spočítat počet objednávek, kde:

```text
Marže % > 20 %
Vzorec
=SOUČIN.SKALÁRNÍ((Tabulka2[Marže %]>0,2)*1)
Výsledek
4
Interpretace

Čtyři objednávky mají marži vyšší než 20 %.

✅ Úkol 2 – Celková tržba za kategorii Notebook
Zadání

Spočítat celkové tržby, kde:

Kategorie = Notebook
Vzorec
=SOUČIN.SKALÁRNÍ((Tabulka2[Kategorie]="Notebook")*(Tabulka2[Tržba]))
Výsledek
191000
Interpretace

Celkové tržby za kategorii Notebook jsou 191 000 Kč.

✅ Úkol 3 – Tržby z kanálu Organic s prioritou 1
Zadání

Spočítat tržby, kde:

Kanál = Organic
AND
Priorita = 1
Vzorec
=SOUČIN.SKALÁRNÍ((Tabulka2[Kanál]="Organic")*(Tabulka2[Priorita]=1)*(Tabulka2[Tržba]))
Výsledek
108000
Interpretace

Tržby z prioritních objednávek z kanálu Organic jsou 108 000 Kč.

✅ Úkol 4 – Tržby za Notebook nebo TV
Zadání

Spočítat tržby, kde:

Kategorie = Notebook
OR
Kategorie = TV

Každý řádek se má započítat pouze jednou.

Vzorec
=SOUČIN.SKALÁRNÍ(((Tabulka2[Kategorie]="Notebook")+(Tabulka2[Kategorie]="TV")>0)*Tabulka2[Tržba])
Výsledek
247000
Interpretace

Celkové tržby za kategorie Notebook a TV jsou 247 000 Kč.

✅ Úkol 5 – Výkonnostní tržby z Ads nebo Organic
Zadání

Spočítat tržby, kde:

(Kanál = Ads OR Kanál = Organic)
AND
Marže % > 20 %
AND
Vráceno = 0
Vzorec
=SOUČIN.SKALÁRNÍ((((Tabulka2[Kanál]="Ads")+(Tabulka2[Kanál]="Organic"))>0)*(Tabulka2[Marže %]>0,2)*(Tabulka2[Vráceno]=0)*(Tabulka2[Tržba]))
Výsledek
79000
Interpretace

Výkonnostní tržby z kanálů Ads nebo Organic, s marží nad 20 % a bez vrácení, jsou 79 000 Kč.

Do výsledku vstoupily objednávky:

Objednávka	Kanál	Tržba	Marže %	Vráceno
1002	Organic	18000	0,25	0
1005	Organic	61000	0,22	0
🧠 Klíčová logika
AND logika

Používá se násobení:

(podmínka1)*(podmínka2)

Význam:

musí platit všechny podmínky současně
OR logika

Používá se sčítání a porovnání >0:

((podmínka1)+(podmínka2)>0)

Význam:

stačí, aby platila alespoň jedna podmínka
Proč >0

Bez >0 by se řádek, který splní více OR podmínek, mohl započítat vícekrát.

Porovnání:

>0

převede výsledek na čistý filtr:

PRAVDA / NEPRAVDA

tedy:

1 / 0
🧩 Debugging pomocí F9

Při kontrole složitých vzorců lze označit část vzorce a stisknout:

F9

Excel zobrazí mezivýsledek jako pole, například:

{PRAVDA;PRAVDA;PRAVDA;NEPRAVDA;PRAVDA;PRAVDA;NEPRAVDA;PRAVDA}

Důležité:

Po kontrole stisknout ESC, ne Enter.

Jinak Excel vloží mezivýsledek napevno do vzorce.

🔗 SQL mindset

Tento výpočet:

=SOUČIN.SKALÁRNÍ((((Tabulka2[Kanál]="Ads")+(Tabulka2[Kanál]="Organic"))>0)*(Tabulka2[Marže %]>0,2)*(Tabulka2[Vráceno]=0)*(Tabulka2[Tržba]))

odpovídá logice:

SELECT
  SUM(trzba)
FROM orders
WHERE kanal IN ('Ads', 'Organic')
  AND marze > 0.2
  AND vraceno = 0;
📌 Shrnutí

V této case study jsem si procvičil použití funkce SOUČIN.SKALÁRNÍ() jako flexibilní alternativy k běžným agregačním funkcím.

Hlavní přínos:

filtr → logika → agregace → KPI

Tento způsob práce je blízký logice SQL, Power BI i datové analýze v Pythonu.
