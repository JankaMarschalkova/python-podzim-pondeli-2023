# Tahák pro lekci Základní dotazy

## Import pandas
```
import pandas
```

## Přidání indexů
```
df.set_index("column_name")     # přeměna existujícího sloupce na index
df.reset_index()                # změna zpět na automatický číslený index
df.index                        # kontrola
```

## Počítání nad Series
```
new_series = df["column_name"]  # vytvoření série ze sloupce
new_series.sum()                # .mean, .min, .max, .median
new_series.describe()           # informace o hodnotách v sloupcí
```

## Podmínky
```
filtered_df = df[df["column_name"] < value] # operátory ==, < , >
filtered_df = df[df["column_name"].isin(["value_1", "value_2"])]

# Řetězení více podmínek (and = &, or = |)
filtered_df = df[(df["column_name") > value) & (df["other_column_name"] == value)]

```