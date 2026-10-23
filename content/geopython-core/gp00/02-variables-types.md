# 2. Μεταβλητές και τύποι δεδομένων

## Πρακτική άσκηση στο Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/starter/gp00_02_variables_types_starter.ipynb)

## Τι θα μάθεις

- τι είναι μεταβλητή,
- `str`, `int`, `float`, `bool`,
- `type()`,
- απλούς υπολογισμούς,
- μετατροπές τύπων.

## Μεταβλητές

```python
city = "Serres"
population = 60000
latitude = 41.09
longitude = 23.55
```

> 💡 **GeoTip**
>
> Χρησιμοποίησε ονόματα όπως `latitude`, `longitude`, `crs`, `area_m2`, `distance_m`.

## Βασικοί τύποι

```python
city = "Serres"      # str
population = 60000   # int
latitude = 41.09     # float
active = True        # bool
```

## `type()`

```python
print(type(city))
print(type(population))
print(type(latitude))
```

## Υπολογισμός εμβαδού

```python
width = 100
height = 50
area = width * height
print(area)
```

## Από m² σε ha

```python
area_m2 = 25000
area_ha = area_m2 / 10000
print(area_ha)
```

## Μετατροπή τύπου

```python
population = "60000"
population = int(population)
```

## ⚠️ Αριθμός ως κείμενο

```python
distance = "100"
print(distance + distance)
```

δίνει `100100`.

## Mini άσκηση

Δημιούργησε:
- `name = "Survey Point 01"`
- `x = 445250.50`
- `y = 4548120.75`
- `elevation = 82.4`
- `crs = "EPSG:2100"`
- `active = True`

και πρόσθεσε 1.5 m στο elevation.

## Επόμενο βήμα

**Λίστες και λεξικά**

## Ενδεικτική λύση

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/solution/gp00_02_variables_types_solution.ipynb)
