# 8. Λάθη, debugging και βοήθεια από ΤΝ

## Πρακτική άσκηση στο Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/starter/gp00_08_errors_ai_help_starter.ipynb)

## Τι θα μάθεις

- βασικά errors,
- debugging,
- QA,
- υπεύθυνη χρήση ΤΝ.

## Τα errors είναι φυσιολογικά

Σημαντικό δεν είναι να μην κάνεις ποτέ λάθος, αλλά να μπορείς να εντοπίζεις και να διορθώνεις προβλήματα.

## Συνηθισμένα errors

### SyntaxError

```python
if elevation > 100
    print(elevation)
```

### NameError

```python
city = "Serres"
print(City)
```

### TypeError

```python
distance = "100"
result = distance + 50
```

### KeyError

```python
point = {"name": "P1", "elevation": 82}
print(point["height"])
```

### IndexError

```python
cities = ["Serres", "Drama", "Kavala"]
print(cities[3])
```

## Debugging

```text
1. Διαβάζω το error
2. Βρίσκω τη γραμμή
3. Ελέγχω μεταβλητές και τύπους
4. Δοκιμάζω μικρότερο παράδειγμα
5. Διορθώνω
6. Εκτελώ ξανά
7. Ελέγχω το αποτέλεσμα
```

## Ο κώδικας μπορεί να τρέχει και να είναι λάθος

```python
Point(latitude, longitude)
```

μπορεί να εκτελεστεί αλλά να αντιστρέφει X/Y.

## GeoPython QA

```python
print("Rows:", len(gdf))
print("CRS:", gdf.crs)
print(gdf.geometry.geom_type.value_counts())
print(gdf.total_bounds)
```

## ΤΝ ως βοηθός

Δεν κάνουμε:

```text
Copy → Paste → Run → Τέλος
```

Αλλά:

```text
Ρωτάω → Κατανοώ → Εκτελώ → Ελέγχω → Διορθώνω
```

## Mini Challenge

Διόρθωσε:
- αντιστροφή longitude/latitude,
- `GDF` αντί `gdf`.

## Επόμενο βήμα

**Mini Challenge**

## Ενδεικτική λύση

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/solution/gp00_08_errors_ai_help_solution.ipynb)
