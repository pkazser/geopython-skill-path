# 3. Συντεταγμένες και geometry

## Τι θα μάθεις

Θα μετατρέψεις τα δύο πεδία συντεταγμένων σε Points.

```python
import geopandas as gpd

gdf = gpd.GeoDataFrame(
    df,
    geometry=gpd.points_from_xy(df["longitude"], df["latitude"]),
    crs="EPSG:4326"
)
```

Η σειρά είναι πάντα `longitude` ως X και `latitude` ως Y.

## Πρώτος έλεγχος

```python
print(gdf.geometry.head())
print(gdf.geometry.geom_type.value_counts())
```

## Συνηθισμένο λάθος

Η αντίστροφη σειρά μπορεί να δημιουργήσει σημεία σε λάθος περιοχή χωρίς να εμφανιστεί error. Ο οπτικός έλεγχος είναι απαραίτητος.

## Γιατί είναι χρήσιμο

Τα X/Y είναι ο πυρήνας της μετατροπής. Αν αντιστρέψεις longitude και latitude, μπορεί να πάρεις τεχνικά valid Points αλλά σε λάθος θέση.

## Πρακτική εκτέλεση

```python
print(gdf[["asset_id", "longitude", "latitude", "geometry"]].head())
print(gdf.total_bounds)
```

Για το dataset των Σερρών περιμένουμε bounds κοντά στα `23.55–23.60` longitude και `41.08–41.12` latitude. Τα bounds δεν αποδεικνύουν τα πάντα, αλλά αποκαλύπτουν προφανείς αναστροφές ή outliers.

## Checkpoint

Ποια τιμή περνά ως X στο `points_from_xy()` και ποια ως Y; Απάντησε πριν συνεχίσεις.
