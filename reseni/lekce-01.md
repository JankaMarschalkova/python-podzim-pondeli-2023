## Součet čísel v seznamu ◇◇◇◇◆

Napiš kód, který zpracuje seznam čísel a vypíše jejich součet (bez použití funkce `sum()`).

<details>
<summary><b>Řešení</b></summary>


```python
soucet = 0

for cislo in [1, 2, 3, 4]:
    soucet += cislo

print(soucet)
```

</details>

## Největší prvek v seznamu ◇◇◇◇◆

Napiš kód, který zpracuje seznam čísel a vypíše největší prvek v tomto seznamu (bez použití funkce `max()`).

<details>
<summary><b>Řešení</b></summary>


```python
nejvetsi = 0

for cislo in [1, 2, 100, 3, 4]:
    if cislo > nejvetsi:
        nejvetsi = cislo

print(nejvetsi)
```

</details>

## Sudá čísla ◇◇◇◆◆

Napiš kód, který zpracuje seznam čísel a vypíše pouze sudá čísla z tohoto seznamu.

<details>
<summary><b>Řešení</b></summary>


```python
for cislo in [1, 2, 100, 3, 4]:
    if cislo % 2 == 0:
        print(cislo)
```

</details>

## Rozdělení čísel ◇◇◇◆◆

Napiš kód, který zpracuje seznam čísel a vytvoří nový seznam se sudými čísly a nový seznam s lichými čísly z původního
seznamu.

<details>
<summary><b>Řešení</b></summary>


```python
sude = []
liche = []

for cislo in [1, 2, 100, 3, 4]:
    if cislo % 2 == 0:
        sude.append(cislo)
    else:
        liche.append(cislo)

print(sude)
print(liche)
```

</details>



## Odstranění duplikátů ◇◇◇◆◆

Napiš kód, který zpracuje seznam a vytvoří nový seznam bez duplikátů. Výsledné pořadí prvků musí být zachováno.

<details>
<summary><b>Řešení</b></summary>


```python
ciste = []

for cislo in [1, 2, 1, 100, 3, 3, 4]:
    if cislo not in ciste:
        ciste.append(cislo)

print(ciste)
```

</details>

## Přijímačky ◇◇◇◆◆

Vrať se k příkladu vysvědčení studenta.

```python
school_report = [
    ['Český jazyk', 1],
    ['Anglický jazyk', 1],
    ['Matematika', 1],
    ['Přírodopis', 2],
    ['Dějepis', 1],
    ['Fyzika', 2],
    ['Hudební výchova', 4],
    ['Výtvarná výchova', 2],
    ['Tělesná výchova', 3],
    ['Chemie', 4],
]
```

Při přihlašování na střední školu mohou být důležitější příklady z některých konkrétních předmětů. Uprav kód z lekce
tak, aby spočítal průměr pouze z jazyků, matematiky a fyziky.

<details>
<summary><b>Řešení</b></summary>


```python

sledovane_predmety = [
    'Český jazyk',
    'Anglický jazyk',
    'Matematika',
    'Fyzika',
]

soucet = 0
for predmet_znamka in school_report:
    # rozdelime si dvojici na dve samostatne promenne pro lepsi praci
    predmet = predmet_znamka[0]
    znamka = predmet_znamka[1]
    if predmet in sledovane_predmety:
        soucet += znamka

print(f'Průměr sledovaných předmětů je: {soucet / len(sledovane_predmety)}')
```

</details>

## Rodná čísla ◇◇◆◆◆

V následujícím seznamu máš seznam rodných čísel pacientů, kteří navštívili v jeden konkrétní den lékařskou ordinaci.

```python
rodna_cisla = [
    '845128/6219',
    '801002/5021',
    '900116/8291',
    '790501/7894',
    '850706/9259',
    '891222/1824',
    '870327/9582',
    '810602/6883',
    '850512/5070',
    '790531/7081'
]
```

- Kolik přišlo mužů a kolik žen?
- Kdy se narodil nejstarší a kdy nejmladší pacient?


Pokud nevíš, jak funguje rodné číslo, vysvětlení je níže:  
Rodné číslo je identifikační číslo, které slouží k jednoznačné identifikaci osoby. V České republice se rodné číslo
skládá z 10 číslic a jednoho lomítka, které ho rozděluje na části.
- Prvních 6 číslic udává datum narození v pořadí rok (2 číslice), měsíc (2 číslice) a den (2 číslice). Například pro
narození 2. února 1990 by prvních 6 číslic mělo být 900202. Zbytek rodného čísla (tj. část za lomítkem) slouží k
identifikaci konkrétní osoby.
- Ženy mají k číslu měsíce přičteno 50, např. 845128/6219 je číslo patřící ženě.*

<details>
<summary><b>Řešení</b></summary>


```python
pocet_muzu = 0
datumy_jako_cislo = []

for rodne_cislo in rodna_cisla:
    ciselne_datum = int(rodne_cislo[:6])
    if int(rodne_cislo[2]) >= 5:  # zena
        ciselne_datum -= 5_000
    else:
        pocet_muzu += 1
    datumy_jako_cislo.append(ciselne_datum)

print(f'přišlo {pocet_muzu} mužů a {len(rodna_cisla) - pocet_muzu} žen')

print(f'nejmladsi se narodil {max(datumy_jako_cislo)}')
print(f'nejstarší se narodil {min(datumy_jako_cislo)}')
```


</details>

## Průměrné teploty ◇◇◇◆◆

Následující tabulka obsahuje průměrné roční teploty v České republice za roky 2001 až 2010 (zdroj: Český
hydrometeorologický ústav).

| rok  | teplota °C  |
|------|:-----------:|
| 2001 |     7.8     |
| 2002 |     8.7     |
| 2003 |     8.2     |
| 2004 |     7.8     |
| 2005 |     7.7     |
| 2006 |     8.2     |
| 2007 |     9.1     |
| 2008 |     8.9     |
| 2009 |     8.4     |
| 2010 |     7.2     |

Vytvořte reprezentaci této tabulky pomocí seznamu seznamů. Zde existují dvě možnosti.  
Nejprve vytvořte seznam, který obsahuje řádky tabulky jako dvouprvkové seznamy a uložte jej do proměnné `radky`.  
Poté vytvořte seznam, který obsahuje sloupce tabulky, tedy dva seznamy po deseti prvcích. Uložte jej do
proměnné `sloupce`.

Pro obě tyto reprezentace vyřešte následující úkoly

- Získejte teplotu na třetím řádku tabulky.
- Získejte rok na pátém řádku tabulky.
- Získejte poslední řádek tabulky jako seznam.
- Vytvořte tabulku bez prvních dvou řádků.
- Vytvořte tabulku pouze z prvních dvou řádků.
- Vytvořte tabulku obsahující jen řádky 5, 6, 7, 8 (myšleno při "lidském" číslování, tj. od 1).
- Použitím proměnné `sloupce` vypište seznam teplot seřazený vzestupně podle velikosti. Šlo by to i pomocí
  proměnné `radky`, ale to ještě neumíme.

<details>
<summary><b>Řešení</b></summary>


```python
radky = [
    [2001, 7.8],
    [2002, 8.7],
    [2003, 8.2],
    [2004, 7.8],
    [2005, 7.7],
    [2006, 8.2],
    [2007, 9.1],
    [2008, 8.9],
    [2009, 8.4],
    [2010, 7.2],
]

# Získejte teplotu na třetím řádku tabulky.
radky[2][1]

# Získejte rok na pátém řádku tabulky.
radky[4][0]

# Získejte poslední řádek tabulky jako seznam.
radky[-1]

# Vytvořte tabulku bez prvních dvou řádků.
radky[2:]

# Vytvořte tabulku pouze z prvních dvou řádků.
radky[:2]

# Vytvořte tabulku obsahující jen řádky 5, 6, 7, 8 (myšleno při "lidském" číslování, tj. od 1).
radky[4:8]

sloupce = [
    [2001, 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010],
    [7.8, 8.7, 8.2, 7.8, 7.7, 8.2, 9.1, 8.9, 8.4, 7.2],
]

# Použitím proměnné sloupce vypište seznam teplot seřazený vzestupně podle velikosti.
print(sorted(sloupce[1]))
```

</details>

## Známky z písemek ◇◇◆◆◆

Máme data o písemce, která obsahovala 4 otázky. Za každou otázku mohl student (studentka) získat max. 10 bodů.  
Výsledky studentů jsou v následující tabulce.

| Student | Otázka 1 | Otázka 2 | Otázka 3 | Otázka 4 |
|---------|----------|----------|----------|----------|
| A       | 9        | 7        | 8        | 5        |
| B       | 5        | 3        | 6        | 6        |
| C       | 8        | 4        | 9        | 7        |
| D       | 8        | 5        | 4        | 8        |
| E       | 10       | 6        | 10       | 7        |

Ulož si známky studentů do dvourozměrného seznamu.

Spočítej známku jednotlivých studentů. Známku urči podle celkového počtu bodů ze všech příkladů. Bodovací tabulku najdeš
níže.

| Body        | Známka |
|-------------|-------:|
| 36 a více   |      1 |
| 32 a více   |      2 |
| 26 a více   |      3 |
| 20 a více   |      4 |
| méně než 20 |      5 |

Vypočítej průměrné body z jednotlivých otázek. Ze které otázky dostali studenti v průměru nejvíce bodů? A ze které
naopak nejméně?

<details>
<summary><b>Řešení</b></summary>


```python
tabulka_bodu = [
    ['A', 9, 7, 8, 5],
    ['B', 5, 3, 6, 6],
    ['C', 8, 4, 9, 7],
    ['D', 8, 5, 4, 8],
    ['E', 10, 6, 10, 7],
]

body_celkem = []
for student_znamky in tabulka_bodu:
    # rozdlel na studenta a body
    student = student_znamky[0]
    body = student_znamky[1:]

    celkem_bodu = sum(body)

    # urci znamku
    if celkem_bodu < 20:
        znamka = 5
    elif celkem_bodu <= 26:
        znamka = 4
    elif celkem_bodu <= 32:
        znamka = 3
    elif celkem_bodu <= 36:
        znamka = 2
    else:
        znamka = 1

    # vypis
    print(f'student {student} dostal {znamka}')

# Vypočítej průměrné body z jednotlivých otázek.
# Ze které otázky dostali studenti v průměru nejvíce bodů? A ze které naopak nejméně?

# přepíšeme si tabulku
tabulka_po_sloupcich = [
    ['A', 'B', 'C', 'D', 'E'],
    [9, 5, 8, 8, 10],
    [7, 3, 4, 5, 6],
    [8, 6, 9, 4, 10],
    [5, 6, 7, 8, 7],
]

import statistics

prumery = []
for radek in tabulka_po_sloupcich[1:]:
    prumery.append(statistics.mean(radek))

print(prumery)

# z výsledného seznamu je možné vyčíst jednotlivé průměry
```

</details>

## Zasedačka ◇◇◆◆◆

Níže máš seznam akcí, které se konaly v zasedačce jedné firmy.

```python
akce = [
    "školení - řízení firemních vozidel",
    "jazykový kurz - angličtina",
    "pohovor - Jan Dvořák",
    "pohovor - Antonín Sova",
    "jazykový kurz - němčina",
    "pohovor - Iveta Hájková",
    "pohovor - Ivan Brož",
    "pohovor - Katarína Martináková",
    "setkání se zákazníkem - Metrostav",
    "jazykový kurz - angličtina",
    "školení - vykazování práce",
    "pohovor - Klaudie Moudrusová",
]
```

Napiš program, který zjistí následující:

- Kolik se uskutečnilo pohovorů?
- V jakých jazycích se mohou zaměstnanci firmy vzdělávat?

Při řešení můžeš využít operátor `in` a slicing, případně metodu `split()`

<details>
<summary><b>Řešení</b></summary>


```python
dostupne_jazyky = []
pocet_pohovoru = 0

for radek_text in akce:

    # rozdelim a ulozim do dvou promennych
    radek = radek_text.split(' - ')
    typ = radek[0]
    data = radek[1]

    if typ == 'jazykový kurz':
        # musime zkontrolovat, jestli uz v seznamu nemame
        if data not in dostupne_jazyky:
            dostupne_jazyky.append(data)

    if typ == 'pohovor':
        pocet_pohovoru += 1

print(f'dostupne jazyky jsou {dostupne_jazyky}')
print(f'bylo {pocet_pohovoru} pohovoru')
```

</details>
