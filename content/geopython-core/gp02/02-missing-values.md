# 2. Missing values

## Τι θα μάθεις

Θα εντοπίσεις κενές τιμές και θα αποφασίσεις αν μια εγγραφή μπορεί να παραμείνει στο dataset.

```python
import pandas as pd

df = pd.read_csv("data/gp02/observations_dirty.csv")
df.isna().sum()
```

## Δεν είναι όλα τα κενά ίδια

Μια κενή περιγραφή μπορεί να συμπληρωθεί ή να παραμείνει κενή. Μια κενή latitude όμως εμποδίζει τη δημιουργία σημείου.

```python
df[df["latitude"].isna()]
```

Για το workflow μας θα κρατήσουμε μόνο γραμμές με απαραίτητο `observation_id`, `longitude` και `latitude`.

```python
clean = df.dropna(subset=["observation_id", "longitude", "latitude"]).copy()
```

## GeoTip

Πριν και μετά το `dropna()` μέτρησε τις γραμμές. Έτσι γνωρίζεις πόσα features αποκλείστηκαν.

## Επόμενο βήμα

Θα ελέγξουμε τους τύπους των στηλών.
