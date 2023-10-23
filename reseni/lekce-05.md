## Seznamy čísel ◇◇◇◇◆

Mějme zadaný následující seznam

```python
cisla = [1.12, 4.51, 2.64, 13.1, 0.1]
```

Vytvořte seznam, který obsahuje

- každé z čísel ze seznamu cisla vynásobené dvěma,
- každé z čísel ze seznamu cisla s opačným znaménkem,
- každé z čísel ze seznamu cisla umocněné na druhou,
- každé z čísel ze seznamu cisla jako řetězec.

<details>
<summary><b>Řešení</b></summary>


```python
krat_dva = [n * 2 for n in cisla]
minus = [-n for n in cisla]
na_druhou = [n ** 2 for n in cisla]
jako_str = [str(n) for n in cisla]
```

</details>

## Seznamy řetězců ◇◇◇◆◆

Mějme zadaný následující seznam

```python
jmena = ['Roman', 'Jan', 'Miroslav', 'Petr', 'Gabriel']
```

Vytvořte seznam, který obsahuje

- počty písmen ve všech jménech,
- všechna jména napsaná velkými písmeny,
- všechna jména plus písmeno 'a' na konci (stanou se z nich tedy ženská jména),
- všechna jména převedená na malá písmena s koncovkou '@email.cz'.

<details>
<summary><b>Řešení</b></summary>


```python
pocty = [len(jmeno) for jmeno in jmena]
velkymi = [jmeno.upper() for jmeno in jmena]
s_ackem = [jmeno + 'a' for jmeno in jmena]
emaily = [f'{jmeno.lower()}@email.cz' for jmeno in jmena]
```

</details>

## Seznam teplot ◇◇◆◆◆

Mějme zadaný následující seznam naměřených teplot. Seznam obsahuje teploty naměřené pro každý den v týdnu ve čtyřech
časech - ráno, v poledne, večer a v noci.

```python
teploty = [
    [2.1, 5.2, 6.1, -0.1],
    [2.2, 4.8, 5.6, -1.0],
    [3.3, 6.5, 5.9, 1.2],
    [2.9, 5.6, 6.0, 0.0],
    [2.0, 4.6, 5.5, -1.2],
    [1.0, 3.2, 2.1, -2.0],
    [0.4, 2.7, 1.3, -2.8]
]
```

- Vytvořte seznam průměrných teplot pro každý den.
- Vytvořte seznam ranních teplot.
- Vytvořte seznam nočních teplot.
- Vytvořte seznam dvouprvkových seznamů obsahujících pouze polední a noční teplotu.

<details>
<summary><b>Řešení</b></summary>


```python
import statistics

prumery = [statistics.mean(den) for den in teploty]
ranni = [den[0] for den in teploty]
nocni = [den[-1] for den in teploty]
poledne_a_noc = [[den[1], den[-1]] for den in teploty]
```

</details>

## Čtení kódu ◇◇◇◆◆

V této úloze jde o pochopení kódu.  
Nemá tak dané řešení.

## Ověřování věku ◇◇◇◇◆

Následující seznam obsahuje věky uživatelů naší malé sociální sítě.

```python
veky = [35, 12, 44, 11, 18, 21, 28, 18]
```

- Vytvořte pomocí chroustání seznamů seznam celých čísel, které udávají, kolik jednotlivým uživatelům zbývá do 18ti let.
  Záporná čísla budou znamenat, že uživatel už věk překročil.
- Vytvořte pomocí chroustání seznamů seznam pravdivostních hodnot, které udávají, který uživatel je starší 18ti let.
- Vytvořte pomocí chroustání seznamů seznam pravdivostních hodnot, které udávají, který uživatel má přesně 18 let.

<details>
<summary><b>Řešení</b></summary>


```python
zbyva_do_18 = [18 - vek for vek in veky]
starsi_18 = [vek > 18 for vek in veky]
stary_presne_18 = [vek == 18 for vek in veky]
```

</details>

## Promítání ◇◇◇◆◆

V letním kině Šmajchl mají program na každý den uložený jako dva seznamy. První seznam obsahuje názvy filmů a druhý
jejich délky v minutách, např. takto:

```python
nazvy = [
    'Někdo to rád horké, extended edition',
    'Adéla ještě nevečeřela',
    'Kulový blesk'
]
delky = [136, 105, 82]
```

Použijte chroustání seznamů a vyrobte seznam trvání, který bude obsahovat délky filmů nikoliv jako čísla v minutách, ale
jako řetězce v hodinách a v minutách. Výsledek tedy bude vypadat takto

```python
trvani = ['2:16', '1:45', '1:22']
```

<details>
<summary><b>Řešení</b></summary>


```python
trvani = [f'{d // 60}:{d % 60}' for d in delky]
```

</details>

## Počty obyvatel ◇◇◇◆◆

Mějme počty obyvatel v jednotlivých krajích ČR podle následující tabulky.

| Kraj                 | Počet obyvatel |
|----------------------|----------------|
| Hlavní město Praha   | 1 280 508      |
| Jihočeský kraj       | 638 782        |
| Jihomoravský kraj    | 1 178 812      |
| Karlovarský kraj     | 296 749        |
| Kraj Vysočina        | 508 952        |
| Královéhradecký kraj | 550 804        |
| Liberecký kraj       | 440 636        |
| Moravskoslezský kraj | 1 209 879      |
| Olomoucký kraj       | 633 925        |
| Pardubický kraj      | 517 087        |
| Plzeňský kraj        | 578 629        |
| Středočeský kraj     | 1 338 982      |
| Ústecký kraj         | 821 377        |
| Zlínský kraj         | 583 698        |

Tuto tabulku máme reprezentovanou jako seznam:

```python
kraje = [
    ['Hlavní město Praha', '1 280 508'],
    ['Jihočeský kraj', '638 782'],
    ['Jihomoravský kraj', '1 178 812'],
    ['Karlovarský kraj', '296 749'],
    ['Kraj Vysočina', '508 952'],
    ['Královéhradecký kraj', '550 804'],
    ['Liberecký kraj', '440 636'],
    ['Moravskoslezský kraj', '1 209 879'],
    ['Olomoucký kraj', '633 925'],
    ['Pardubický kraj', '517 087'],
    ['Plzeňský kraj', '578 629'],
    ['Středočeský kraj', '1 338 982'],
    ['Ústecký kraj', '821 377'],
    ['Zlínský kraj', '583 698']
]
```

- Vytvořte seznam, který obsahuje pouze názvy všech krajů, tedy první sloupeček této tabulky.
- Vytvořte seznam, který obsahuje počty obyvatel jako čísla. Pro zbavení se mezer v číslech se vám jistě bude hodit
  metoda řetězců jménem replace().
- Do vhodně pojmenované proměnné uložte seznam, který reprezentuje výše uvedenou tabulku jako dva seznamy: seznam jmen a
  seznam počtů obyvatel jako čísla.

<details>
<summary><b>Řešení</b></summary>


```python
nazvy = [kraj[0] for kraj in kraje]
obyvatele = [int(kraj[-1].replace(' ', '')) for kraj in kraje]

jmena_a_pocty = [
  [kraj[0] for kraj in kraje],
  [int(kraj[-1].replace(' ', '')) for kraj in kraje],
]
```

</details>

## Volby ◇◇◆◆◆

Máme pět kandidátů na post prezidenta ČR. Následující tabulka obsahuje hlasy, které jednotliví kandidáti získali v prvním kole prezidentských voleb.

| Kraj                 | Igor Rezek | Augustýn Doležal | Vladan Bednář | Ondřej Brotz | Radim Kašpar |
|----------------------|------------|------------------|---------------|--------------|--------------|
| Hlavní město Praha   | 78774      | 43179            | 225111        | 144799       | 242854       |
| Jihočeský kraj       | 91062      | 22451            | 17475         | 53391        | 46450        |
| Jihomoravský kraj    | 179186     | 216499           | 4493          | 156305       | 61222        |
| Karlovarský kraj     | 9619       | 53476            | 926           | 64737        | 34566        |
| Kraj Vysočina        | 66904      | 85730            | 27271         | 12964        | 38041        |
| Královéhradecký kraj | 118755     | 1929             | 30426         | 25178        | 31952        |
| Liberecký kraj       | 64467      | 40993            | 81181         | 39392        | 4335         |
| Moravskoslezský kraj | 11221      | 97970            | 26179         | 98539        | 112578       |
| Olomoucký kraj       | 171064     | 7638             | 8752          | 96666        | 39738        |
| Pardubický kraj      | 74235      | 101680           | 18920         | 45904        | 1922         |
| Plzeňský kraj        | 39309      | 1505             | 10531         | 30458        | 40228        |
| Středočeský kraj     | 131584     | 1812             | 241122        | 22267        | 99326        |
| Ústecký kraj         | 194133     | 39985            | 200997        | 28229        | 20780        |
| Zlínský kraj         | 66188      | 51607            | 15977         | 177272       | 17664        |

Data máme k dispozici v následujícím formátu

```python
hlasy = [
    [78774, 43179, 225111, 144799, 242854],
    [91062, 22451, 17475, 53391, 46450],
    [179186, 216499, 4493, 156305, 61222],
    [9619, 53476, 926, 64737, 34566],
    [66904, 85730, 27271, 12964, 38041],
    [118755, 1929, 30426, 25178, 31952],
    [64467, 40993, 81181, 39392, 4335],
    [11221, 97970, 26179, 98539, 112578],
    [171064, 7638, 8752, 96666, 39738],
    [74235, 101680, 18920, 45904, 1922],
    [39309, 1505, 10531, 30458, 40228],
    [131584, 1812, 241122, 22267, 99326],
    [194133, 39985, 200997, 28229, 20780],
    [66188, 51607, 15977, 177272, 17664]
]
```

Zodpovězte následující otázky:

- Kolik získal každý kandidát hlasů v celé ČR?
- Který kandidát vyhrál první kolo voleb?
- Ve kterých krajích byla nejvyšší a nejnižší volební účast
- Vytvořte tabulku, která ukazuje který kandidát vyhrál v kterém kraji.
- Vytvořte tabulku podobnou té z tohoto cvičení, která místo čísel bude obsahovat jaké procento celkového počtu hlasů získal každý kandidát v daném kraji.

**Nápověda**: postupuje tak, že použijete na každý řádek tabulky zvlášť chroustání seznamů. Tabulku můžete sestavit tak, že tento postup ručně zopakujete 13 krát, jednou pro každý kraj. Pokud toužíte po elegantnějším řešení, vyčkejte na nepovinné úložky.

<details>
<summary><b>Řešení</b></summary>


```python
# soucty hlasu po kandidatech
soucty_hlasu = []
for poradi_kandidata in range(len(hlasy[0])):
    soucet_za_kandidata = 0
    for kraj in hlasy:
        soucet_za_kandidata += kraj[poradi_kandidata]
    soucty_hlasu.append(soucet_za_kandidata)
print(soucty_hlasu)

# ktery vyhral
cislo_viteze = soucty_hlasu.index(min(soucty_hlasu))
print(cislo_viteze)

# nejvyssi a nejnizsi ucast
ucasti = [sum(kraj) for kraj in hlasy]
nejnizsi = ucasti.index(min(ucasti))
nejvyssi = ucasti.index(max(ucasti))
print(f'kraj s nejinzsi ucasti je {nejnizsi}')
print(f'kraj s nejvyssi ucasti je {nejvyssi}')

# procenta celkoveho poctu
procenta = []
for kraj in hlasy:
    soucet = sum(kraj)
    procenta.append(
        [round((kandidat / soucet) * 100, 2) for kandidat in kraj]
    )
print(procenta)
```

</details>

## Elegantní volby ◇◆◆◆◆

Pokud vás trápí, že řešení varianty e) v úloze o volbách není příliš elegantní, zkuste sestavit Python výraz na jeden řádek, 
který celý bod e) vyřeší najednou. Bude potřeba do sebe zanořit dvě chroustání seznamů, jedno přes hodnoty v řádcích a druhé přes jednotlivé kraje.

<details>
<summary><b>Řešení</b></summary>


```python
# procenta celkoveho poctu
procenta = [
    [round((kandidat / sum(kraj)) * 100, 2) for kandidat in kraj]
    for kraj in hlasy
]
print(procenta)
```

</details>