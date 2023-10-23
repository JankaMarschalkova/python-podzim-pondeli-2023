## Závod ◇◇◆◆◆

Pracuj dál se souborem `zavod.json` a zjisti čas závodníka, který získal stříbrnou medaili. Dále projdi data pomocí
cyklu a vytvoř seznam všech závodníků, kteří závod dokončili, tj. jejich oficiální čas není DNF.

Můžeš postupovat následujícím způsobem:

- Vytvoř si prázdný seznam `finishers`, kam budeš vkládat jména závodníků, kteří závod doběhli.
- Pomocí cyklu projdi seznam závodníků. Struktura vyjmuté položky bude obdobná jako struktura dat o vítězi závodu. Do
  cyklu vlož podmínku, která ověří, zda oficiální čas závodníka je odlišná od řetězce DNF.
- Dovnitř podmínky vlož kód, který vloží jméno závodníka do seznamu `finishers`.
- Na konec programu (mimo cyklus) vlož příkaz na vypsání obsahu seznamu `finishers`.

<details>
<summary><b>Řešení</b></summary>


```python
import json

with open('zavod.json', encoding='utf-8') as file:
    runners = json.load(file)

finishers = []

for runner in runners:
    if runner['casy']['oficialni'] != 'DNF':
        finishers.append(runner['jmeno'])

print(finishers)
```

</details>

## Transformace dat ◇◆◆◆◆

Stáhněte si soubor `words.txt` a zpracujte z něj výstupní soubor ve formátu JSON obsahující slovník. Klíče budou písmena
a hodnoty seznamy slov, které začínají písmenem v klíči. Pokud na nějaké písmeno žádná slova nezačínají, tak ve výstupu
toto písmeno nebude. Seřaďte tyto seznamy podle abecedy. Zajistěte, aby i klíče ve výstupním JSON souboru byly seřazeny
a data byla odsazena čtyřmi mezerami pro lepší čitelnost člověkem.

Vzorový výstup: output.json.

<details>
<summary><b>Řešení</b></summary>


```python
import json

words = {}

with open('words.txt', encoding='utf-8') as file:
    for word in file:
        first_letter = word[0]
        if first_letter not in words:
            words[first_letter] = [word]
        words[first_letter].append(word)

for value in words.values():
    value.sort()

with open('output.json', 'w', encoding='utf-8') as out:
    json.dump(words, out, sort_keys=True, indent=4, ensure_ascii=False)
```

</details>