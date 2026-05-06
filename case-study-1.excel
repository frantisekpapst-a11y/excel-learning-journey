🧠 Case Study 01 – Sales Bonus Logic
Excel • Logické operátory • KDYŽ() • AND / OR / XOR mindset
🎯 Zadání

Firma chce automaticky vyhodnocovat bonus obchodníků.

Bonus získá obchodník pokud:

splní obě podmínky:
tržby ≥ 120 000 Kč
marže ≥ 25 %

NEBO

získá alespoň 5 nových klientů.

📊 Dataset
Obchodník	Tržby	Marže	Noví klienti	Bonus
Novák	150000	0,28	3	?
Dvořák	90000	0,22	7	?
Svoboda	130000	0,20	2	?
Černý	125000	0,30	6	?
Procházka	80000	0,18	1	?

✅ Řešení – logický AND + OR
Vzorec
=KDYŽ(((B2>=120000)*(C2>=0,25))+(D2>=5)>0;"BONUS";"NO BONUS")

🔍 Vysvětlení logiky
Část 1 – AND
(B2>=120000)*(C2>=0,25)

Obě podmínky musí být pravda.

Excel převádí:

PRAVDA = 1
NEPRAVDA = 0

Proto:

1 * 1 = 1

ale:

1 * 0 = 0
Část 2 – OR
+(D2>=5)>0

Stačí:

splnit sales + marži
NEBO
mít ≥ 5 klientů

Používáme:

>0

protože:

1 = jedna podmínka splněna
2 = obě podmínky splněny
📊 Výsledky
Obchodník	Bonus
Novák	BONUS
Dvořák	BONUS
Svoboda	NO BONUS
Černý	BONUS
Procházka	NO BONUS
