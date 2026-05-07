📊 Case Study 05 — Access Control & Business Rules in Excel
🎯 Cíl projektu

Cílem této mini case study bylo procvičit:

logické funkce A()
logické funkce NEBO()
funkci KDYŽ()
business pravidla
převod logických výsledků na text
práci se structured references
modelování rozhodovací logiky v Excelu

📁 Použitý dataset

Tabulka obsahovala informace o účastnících firemní akce.

Jméno	Typ	Kredit	VIP	Zaplaceno
Jan	zaměstnanec	500	0	0
Petra	externista	0	1	0
Lukáš	návštěvník	0	0	300
Eva	návštěvník	0	0	100

✅ Business pravidla

Účastník získá přístup pokud:

má VIP status,
nebo má dostupný kredit,
nebo provedl platbu.

V této case study nebyly definovány přesné limity pro kredit ani platbu, proto byla použita vlastní business interpretace:

jakákoliv hodnota > 0 znamená splnění podmínky

🧮 Použité vzorce
Logické vyhodnocení přístupu
=NEBO([@VIP]=1;[@Kredit]>0;[@Zaplaceno]>0)

Výsledek:

PRAVDA
NEPRAVDA
Textový výstup pomocí KDYŽ()
=KDYŽ(NEBO([@VIP]=1;[@Kredit]>0;[@Zaplaceno]>0);"ano";"ne")
Alternativní přísnější business pravidlo

Možné rozšíření:

=KDYŽ(NEBO([@VIP]=1;[@Kredit]>=300;[@Zaplaceno]>=300);"ano";"ne")

Tato varianta vyžaduje minimální kredit nebo platbu ve výši 300.

📊 Výsledky analýzy
Jméno	Přístup
Jan	ano
Petra	ano
Lukáš	ano
Eva	ano

🧠 Co jsem se naučil
rozdíl mezi logikou AND / OR
kdy použít A()
kdy použít NEBO()
jak vytvářet business pravidla v Excelu
jak převádět logické výsledky na textový výstup
jak používat structured references
že analytik často musí definovat vlastní interpretaci pravidel
🛠 Použité funkce a nástroje
KDYŽ()
NEBO()
A()
logické operátory
Excel Tables
structured references

🚀 Výsledek

Tato case study simulovala jednoduchý systém rozhodování o přístupu na akci pomocí business pravidel.

Projekt ukázal, jak lze pomocí logických funkcí modelovat reálné rozhodovací procesy podobně jako v SQL nebo Pythonu a jak důležitá je správná interpretace business podmínek při práci s daty.
