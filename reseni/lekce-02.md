## Vysvědčení ◇◇◇◇◆

Vytvoř slovník, který reprezentuje vysvědčení.  
Klíč slovníku bude název předmětu a hodnota známka z daného předmětu.  
Pro zjednodušení vlož do slovníku pouze tři předměty (například český jazyk, matematiku a dějepis).  
Vypiš obsah slovníku pomocí funkce `print()`.

<details>
<summary><b>Řešení</b></summary>


```python
vysvedceni = {
    'matematika': 1,
    'cestina'   : 3,
    'dejepis'   : 2,
}
```

</details>

## Detektivky ◇◇◇◆◆

Vydavatel detektivek si eviduje prodané kusy u jednotlivých knih.  
V následujícím slovníku najdeš tři knihy a u každé z nich je počet prodaných kusů.

```python
prodano = {
    'Zkus mě chytit'     : 4165,
    'Vrah zavolá v deset': 5681,
    'Zločinný steh'      : 2565,
}
```

- Zkopíruj si slovník do svého programu.
- Přidej do slovníku nově vydanou detektivku `"Noc, která mě zabila"`, která zatím nebyla uvedena na trh, je tedy
  prodáno
  `0` kusů.
- U knihy `"Vrah zavolá v deset"` zvyš počet prodaných kusů o `100`.

<details>
<summary><b>Řešení</b></summary>


```python
prodano['Noc, která mě zabila'] = 0

prodano['Vrah zavolá v deset'] += 100
```

</details>

## Tombola ◇◇◆◆◆

V následujícím slovníku jsou uložena čísla lístků tomboly a příslušné výhry.

```python
tombola = {
    7 : 'Láhev kvalitního vína Château Headache',
    15: 'Pytel brambor z místního družstva',
    23: 'Čokoládový dort',
    47: 'Kniha o historii města',
    55: 'Šiška salámu',
    67: 'Vyhlídkový let balónem',
    79: 'Moderní televizor',
    91: 'Roční předplatné městského zpravodaje',
    93: 'Společenská hra Sázky a dostihy',
}
```

- Napiš program, který se nejprve zeptá uživatele na číslo jeho lístku. Vstup uživatele si převeď na `int`!
- Zkontroluj, zda je číslo lístku ve slovníku. Pokud ne, vypiš text `"Bohužel nevyhráváš nic."` Pokud číslo ve slovníku
  je, vypiš uživateli, co vyhrál.
- Odeber výhru pro daný lístek ze slovníku, abychom tam evidovali pouze nevydané ceny.

<details>
<summary><b>Řešení</b></summary>


```python
cislo_uzivatele = int(input('Zadej sve cislo listku: '))

if cislo_uzivatele in tombola:
    vyhra = tombola[cislo_uzivatele]
else:
    vyhra = 'Bohužel nevyhráváš nic.'

# NOTE: mnohem lepsi reseni
# vyhra = tombola.get(cislo_uzivatele, 'Bohužel nevyhráváš nic.')

print(f'Vyhrál jsi: {vyhra}')

tombola.pop(cislo_uzivatele)
```

</details>

## Paranoidní večírek ◇◆◆◆◆

Pořadatel našeho večírku se stává stále více paranoidním a nyní rozhodl, že každý z hostů bude mít speciální heslo,
které je platné jen pro něj. Seznam hostů a jejich hesel je níže.  
Napiš program, který nejprve zkontroluje, zda je host na seznamu, a pokud tam je,zeptá se ho na heslo a zkontroluje jeho
správnost.  
Hostu na seznamu, který zadá správné heslo, vypíše program text: `"Smíš vstoupit."`

<details>
<summary><b>Řešení</b></summary>


```python
hesla = {
    'Jiří'   : 'tajne-heslo',
    'Natálie': 'jeste-tajnejsi-heslo',
    'Klára'  : 'nejtajnejsi-heslo',
}

jmeno_hosta = input('Zadej jmeno: ')
vstup = 'Nesmíš projít.'

if jmeno_hosta in hesla:
    heslo = input('Zadej heslo: ')
    if heslo == hesla[jmeno_hosta]:
        vstup = 'Smíš vstoupit.'

print(vstup)
```

</details>

## Vysvědčení 2 ◇◇◇◆◆

Uvažujme vysvědčení, které máme zapsané jako slovník.

```python
vysvedceni = {
    "Český jazyk"     : 1,
    "Anglický jazyk"  : 1,
    "Matematika"      : 1,
    "Přírodopis"      : 2,
    "Dějepis"         : 1,
    "Fyzika"          : 2,
    "Hudební výchova" : 4,
    "Výtvarná výchova": 2,
    "Tělesná výchova" : 3,
    "Chemie"          : 4,
}
```

- Napiš program, který spočte průměrnou známku ze všech předmětů.
- Uprav program, aby vypsal všechny předměty, ve kterých získal student známku 1.

<details>
<summary><b>Řešení</b></summary>


```python
prumerna_znamka = sum(vysvedceni.values()) / len(vysvedceni)
print(f'Průměrná známka je: {prumerna_znamka}')

print('Předměty s jedničkou:')
for predmet, znamka in vysvedceni.items():
    if znamka == 1:
        print('\t' + predmet)
```

</details>

## Čtenářský deník ◇◇◇◆◆

Gustav je vášnivým čtenářem detektivek z našeho nakladatelství a navíc si zapisuje knihy, které přečetl.  
Níže ve slovníku vidíme, jaké informace si eviduje - název knihy, počet stran a hodnocení od 0 do 10.

```python
knihy = [
    {'nazev': 'Vražda s příliš mnoha notami', 'pocet_stran': 450, 'hodnoceni': 5},
    {'nazev': 'Vražda podle knihy', 'pocet_stran': 524, 'hodnoceni': 9},
    {'nazev': 'Past', 'pocet_stran': 390, 'hodnoceni': 4},
    {'nazev': 'Popel popelu', 'pocet_stran': 411, 'hodnoceni': 10},
    {'nazev': 'Noc, která mě zabila', 'pocet_stran': 159, 'hodnoceni': 7},
    {'nazev': 'Vražda, kouř a stíny', 'pocet_stran': 258, 'hodnoceni': 6},
    {'nazev': 'Zločinný steh', 'pocet_stran': 542, 'hodnoceni': 8},
    {'nazev': 'Zkus mě chytit', 'pocet_stran': 247, 'hodnoceni': 7},
    {'nazev': 'Vrah zavolá v deset', 'pocet_stran': 396, 'hodnoceni': 6},
]
```

- Napiš program, který spočte celkový počet stran, které Gustav přečetl.
- Připiš do programu výpočet počtu knih, kterým dal Gustav hodnocení alespoň 8.

<details>
<summary><b>Řešení</b></summary>


```python
pocet_stran = 0
for kniha in knihy:
    pocet_stran += kniha['pocet_stran']

# NOTE: nebo lépe
# pocet_stran = sum(kniha['pocet_stran'] for kniha in knihy)

print(f'Přečetl {pocet_stran} stran.')

pocet_nad_osm = 0
for kniha in knihy:
    if kniha['hodnoceni'] >= 8:
        pocet_nad_osm += 1
print(f'Počet knih s hodnocením >= 8: {pocet_nad_osm}')
```

</details>
