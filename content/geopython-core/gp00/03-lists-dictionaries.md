# 3. Λίστες και λεξικά

## Πρακτική άσκηση στο Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/starter/gp00_03_lists_dictionaries_starter.ipynb)

## Τι θα μάθεις

- λίστες,
- indexes,
- `append()`, `remove()`, `len()`,
- dictionaries,
- list of dictionaries,
- μετάβαση προς DataFrame.

## Λίστα

```python
cities = ["Serres", "Drama", "Kavala"]
print(cities)
```

Η αρίθμηση ξεκινά από `0`:

```python
print(cities[0])
```

## Προσθήκη

```python
cities.append("Thessaloniki")
```

## Αριθμητικές λίστες

```python
elevations = [82.4, 95.1, 105.3, 74.8]

print(min(elevations))
print(max(elevations))
print(sum(elevations) / len(elevations))
```

## Dictionary

```python
point = {
    "name": "Station A",
    "longitude": 23.55,
    "latitude": 41.09,
    "elevation": 125.4
}
```

Πρόσβαση:

```python
print(point["name"])
print(point["elevation"])
```

> 💡 **GeoTip**
>
> Ένα dictionary μοιάζει με μία εγγραφή attribute table.

## List of dictionaries

```python
points = [
    {"name": "P1", "longitude": 23.55, "latitude": 41.09},
    {"name": "P2", "longitude": 23.56, "latitude": 41.10},
    {"name": "P3", "longitude": 23.57, "latitude": 41.08}
]
```

## Από list of dictionaries σε pandas

```python
import pandas as pd
df = pd.DataFrame(points)
df
```

## Mini άσκηση

Δημιούργησε τρία σημεία με `id`, `name`, `x`, `y`, `elevation` και εμφάνισε:
- το δεύτερο σημείο,
- το elevation του τρίτου,
- πόσα σημεία υπάρχουν.

## Επόμενο βήμα

**Συνθήκες και επαναλήψεις**

## Ενδεικτική λύση

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/solution/gp00_03_lists_dictionaries_solution.ipynb)
