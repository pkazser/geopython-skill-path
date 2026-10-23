# 4. Understand — Κατανόηση του dataset

## Τι θα μάθεις

Οι στήλες δεν είναι απλώς ονόματα. Πρέπει να γνωρίζουμε τι σημαίνει κάθε τιμή και σε ποιες μονάδες μετριέται.

## Τι πρόβλημα λύνουμε

Το ίδιο όνομα μπορεί να χρησιμοποιείται διαφορετικά σε διαφορετικά datasets. Πριν δημιουργήσουμε geometry, πρέπει να γνωρίζουμε ότι το `longitude` είναι X, το `latitude` είναι Y και ότι οι τιμές είναι μοίρες WGS84.

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

Το `GeoDataFrame` κρατά τις αρχικές columns και προσθέτει geometry. Το `crs="EPSG:4326"` δηλώνει την ερμηνεία των υπαρχουσών coordinates· δεν μετατρέπει ακόμη τις θέσεις. Η αναμενόμενη geometry type είναι `Point`.

## QA και ερμηνεία

Έλεγξε rows πριν/μετά, μη κενές geometry, τύπους `Point`, bounds και CRS. Αν τα bounds είναι περίπου longitude 23–24 και latitude 41, το dataset βρίσκεται στην αναμενόμενη περιοχή. Αν τα x/y είναι ανάποδα, το GeoDataFrame μπορεί να δημιουργηθεί χωρίς error αλλά ο χάρτης θα το αποκαλύψει.

Τώρα ο πίνακας έχει στήλη `geometry` και CRS.

## GeoTip

Η σειρά των συντεταγμένων είναι `Point(longitude, latitude)`, δηλαδή `Point(X, Y)`. Δεν αντιστρέφουμε τις δύο τιμές.

## Επόμενο βήμα

Τώρα που γνωρίζουμε τις στήλες και έχουμε γεωμετρία, μπορούμε να επιλέξουμε εγγραφές.
