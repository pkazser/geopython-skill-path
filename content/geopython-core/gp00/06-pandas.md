# 6. Εισαγωγή στο pandas

## Πρακτική άσκηση στο Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/starter/gp00_06_pandas_starter.ipynb)

## Τι θα μάθεις

- `DataFrame`,
- `head()`, `tail()`,
- `shape`, `columns`, `dtypes`,
- επιλογή στηλών,
- νέες στήλες,
- filtering,
- missing values,
- `read_csv()` και `to_csv()`.

## Δημιουργία DataFrame

```python
import pandas as pd

data = {
    "city": ["Serres", "Drama", "Kavala"],
    "population": [60000, 45000, 70000]
}

df = pd.DataFrame(data)
df
```

## Βασικός έλεγχος

```python
df.head()
df.shape
df.columns
df.dtypes
```

> 💡 **GeoTip**
>
> Αν έχεις δουλέψει με attribute table στο QGIS, έχεις ήδη τη βασική νοητική εικόνα ενός DataFrame.

## Νέα στήλη

```python
df["country"] = "Greece"
```

Υπολογισμός σε ολόκληρη στήλη:

```python
df["area_ha"] = df["area_m2"] / 10000
```

## Filtering

```python
df[df["population"] > 50000]
```

Πολλαπλές συνθήκες:

```python
df[
    df["active"] &
    (df["elevation"] > 100)
]
```

## Missing values

```python
df.isna().sum()
```

## CSV

```python
df = pd.read_csv("cities.csv")
```

και:

```python
df.to_csv("output.csv", index=False)
```

## DataFrame δεν σημαίνει GeoDataFrame

Αν υπάρχουν longitude/latitude δεν σημαίνει ότι υπάρχει geometry ή CRS.

## Mini Challenge

Δημιούργησε DataFrame 5 σημείων και κράτησε μόνο active σημεία με elevation > 100.

## Επόμενο βήμα

**GeoPandas**

## Ενδεικτική λύση

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/solution/gp00_06_pandas_solution.ipynb)
