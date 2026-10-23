# 6. Bounds και χάρτης

## Τι θα μάθεις

Θα χρησιμοποιήσεις bounds και plot για αριθμητικό και οπτικό έλεγχο.

```python
print("Bounds:", parks.total_bounds)
parks.plot(figsize=(7, 6), color="forestgreen", edgecolor="black")
```

Τα bounds δείχνουν το συνολικό χωρικό περίβλημα. Ο χάρτης βοηθά να εντοπίσουμε geometry που βρίσκεται πολύ μακριά από τα υπόλοιπα features.

## Σύγκριση layers

```python
water = gpd.read_file(gpkg_path, layer="water_points")
ax = parks.plot(figsize=(7, 6), color="green")
water.plot(ax=ax, color="blue")
```

## Επόμενο βήμα

Θα φιλτράρουμε attributes χωρίς να χάσουμε τη geometry.
