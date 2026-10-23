# 4. Συνθήκες και επαναλήψεις

## Πρακτική άσκηση στο Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/starter/gp00_04_if_for_starter.ipynb)

## Τι θα μάθεις

- `if`, `elif`, `else`,
- συγκρίσεις,
- `and`, `or`,
- `for`,
- συνδυασμό `for` + `if`,
- βασική λογική filtering.

## `if`

```python
elevation = 125

if elevation > 100:
    print("Το σημείο βρίσκεται πάνω από 100 m")
```

## `if / else`

```python
elevation = 80

if elevation > 100:
    print("Υψηλό σημείο")
else:
    print("Χαμηλότερο σημείο")
```

## `elif`

```python
elevation = 350

if elevation < 100:
    print("Low")
elif elevation < 500:
    print("Medium")
else:
    print("High")
```

## `for`

```python
cities = ["Serres", "Drama", "Kavala"]

for city in cities:
    print(city)
```

## `for` + `if`

```python
elevations = [82.4, 95.1, 105.3, 174.8]

for elevation in elevations:
    if elevation > 100:
        print(elevation)
```

## Φιλτραρισμένη λίστα

```python
distances = [120, 350, 620, 180, 900]
nearby = []

for distance in distances:
    if distance <= 500:
        nearby.append(distance)

print(nearby)
```

## Πολλαπλές συνθήκες

```python
for poi in pois:
    if poi["category"] == "school" and poi["distance_m"] <= 500:
        print(poi["name"])
```

## Mini Challenge

Κράτησε μόνο ενεργά σημεία με elevation > 100.

## Επόμενο βήμα

**Συναρτήσεις και βιβλιοθήκες**

## Ενδεικτική λύση

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/solution/gp00_04_if_for_solution.ipynb)
