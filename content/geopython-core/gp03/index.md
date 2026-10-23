# GP03 — CSV to GIS Dataset

## Τι θα κάνουμε

Θα μετατρέψουμε έναν απλό πίνακα CSV σε πραγματικό GIS dataset με geometry, CRS και ασφαλές export.

**CSV → DataFrame → GeoDataFrame → QA → GeoJSON / GeoPackage**

## Μαθησιακοί στόχοι

- να καταλαβαίνεις το schema ενός CSV,
- να ξεχωρίζεις πεδία περιγραφής από πεδία συντεταγμένων,
- να δημιουργείς `GeoDataFrame` από `longitude` και `latitude`,
- να ορίζεις και να ελέγχεις CRS,
- να κάνεις export σε GeoJSON και GeoPackage,
- να ξαναδιαβάζεις το αποτέλεσμα και να το επαληθεύεις.

## Άνοιξε τα notebooks στο Google Colab

### Πρακτική άσκηση στο Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/starter/gp03_csv_to_gis_dataset_starter.ipynb)

### Ενδεικτική λύση

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/solution/gp03_csv_to_gis_dataset_solution.ipynb)

## Το dataset

Το `data/gp03/city_assets.csv` περιέχει σημεία αστικού εξοπλισμού στις Σέρρες. Το CSV δεν περιέχει geometry· θα τη δημιουργήσουμε εμείς.
