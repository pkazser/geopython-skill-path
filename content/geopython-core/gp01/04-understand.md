# 4. Understand — Κατανόηση του dataset

## Τι θα μάθεις

Οι στήλες δεν είναι απλώς ονόματα. Πρέπει να γνωρίζουμε τι σημαίνει κάθε τιμή και σε ποιες μονάδες μετριέται.

| Στήλη | Σημασία |
|---|---|
| `name` | όνομα σημείου |
| `category` | τύπος παρατήρησης |
| `longitude` | γεωγραφικό μήκος |
| `latitude` | γεωγραφικό πλάτος |
| `elevation_m` | υψόμετρο σε μέτρα |
| `status` | αποτέλεσμα ελέγχου |

Τα `longitude` και `latitude` είναι συντεταγμένες σε μοίρες. Δεν είναι μέτρα.

## Από DataFrame σε GeoDataFrame

```python
import geopandas as gpd
from shapely.geometry import Point

geometry = [Point(xy) for xy in zip(points["longitude"], points["latitude"])]
gdf = gpd.GeoDataFrame(points, geometry=geometry, crs="EPSG:4326")
print(gdf.crs)
print(gdf.geometry.geom_type.unique())
```

Τώρα ο πίνακας έχει στήλη `geometry` και CRS.

## GeoTip

Η σειρά των συντεταγμένων είναι `Point(longitude, latitude)`, δηλαδή `Point(X, Y)`. Δεν αντιστρέφουμε τις δύο τιμές.

## Επόμενο βήμα

Τώρα που γνωρίζουμε τις στήλες και έχουμε γεωμετρία, μπορούμε να επιλέξουμε εγγραφές.
