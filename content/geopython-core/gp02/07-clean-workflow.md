# 7. Καθαρισμός με GeoPandas

## Τι θα μάθεις

Θα οργανώσεις τον καθαρισμό σε διαδοχικά, επαναλήψιμα βήματα.

```python
df = pd.read_csv("data/gp02/observations_dirty.csv")
for column in ["longitude", "latitude", "elevation_m"]:
    df[column] = pd.to_numeric(df[column], errors="coerce")

clean = df.dropna(subset=["observation_id", "longitude", "latitude"]).copy()
clean = clean.drop_duplicates("observation_id")
clean = clean[
    clean["longitude"].between(-180, 180) &
    clean["latitude"].between(-90, 90)
].copy()
```

Στη συνέχεια δημιουργούμε το `GeoDataFrame`, ορίζουμε CRS και κρατάμε μόνο τις στήλες που χρειαζόμαστε.

Η σειρά είναι σημαντική: πρώτα καθαρίζουμε τις τιμές, μετά δημιουργούμε geometry.

## Checkpoint

Κατέγραψε πόσες γραμμές είχες αρχικά και πόσες έμειναν μετά από κάθε κανόνα.

## Γιατί είναι χρήσιμο

Η διαδοχική ροή κάνει τον καθαρισμό επαναλήψιμο. Αν αύριο λάβεις νέο CSV, μπορείς να εκτελέσεις τους ίδιους κανόνες και να συγκρίνεις τα counts.

## Before / after QA

```python
print("Before:", len(df))
print("After:", len(gdf))
print("CRS:", gdf.crs)
print("Types:", gdf.geometry.geom_type.value_counts().to_dict())
print("Bounds:", gdf.total_bounds)
```

Το ζητούμενο δεν είναι να κρατήσεις όσο το δυνατόν περισσότερες γραμμές. Είναι να ξέρεις ποιες αφαιρέθηκαν και γιατί.

## Πρόσεξε

Μην τροποποιείς το αρχικό `df` χωρίς αντίγραφο. Το `clean = ... .copy()` κρατά χωριστό το αποτέλεσμα και επιτρέπει σύγκριση με την πηγή.

## Επόμενο βήμα

Στο επόμενο lesson θα μετατρέψουμε τους ελέγχους σε σαφή QA checklist.
