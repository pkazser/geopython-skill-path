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

## Γιατί είναι χρήσιμο

Τα bounds είναι γρήγορος αριθμητικός έλεγχος χωρικής έκτασης. Ο χάρτης δείχνει αν τα layers ευθυγραμμίζονται και αν υπάρχει προφανές outlier.

## Τι πρέπει να παρατηρήσεις

Τα πάρκα και τα water points πρέπει να εμφανίζονται στην ίδια περιοχή. Αν τα σημεία είναι πολύ μακριά από τα polygons, έλεγξε CRS, σειρά longitude/latitude και το layer που διάβασες.

## QA checkpoint

```python
assert parks.total_bounds.shape == (4,)
assert water.total_bounds.shape == (4,)
assert parks.crs == water.crs
```

Ο οπτικός έλεγχος δεν αντικαθιστά τα assertions, αλλά συχνά αποκαλύπτει λάθη που δεν φαίνονται από τις στήλες.
