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

## Γιατί είναι χρήσιμο

Μια γραμμή χωρίς latitude δεν μπορεί να γίνει Point. Αν τη διατηρήσουμε, μπορεί αργότερα να δημιουργηθεί κενή geometry ή να αποτύχει το export. Αντίθετα, μια κενή περιγραφική στήλη μπορεί να είναι αποδεκτή, ανάλογα με το ερώτημα.

## Τι πρέπει να παρατηρήσεις

```python
print("Πριν:", len(df))
clean = df.dropna(subset=["observation_id", "longitude", "latitude"]).copy()
print("Μετά:", len(clean))
```

Το `subset` είναι σημαντικό: δεν πετάμε όλες τις γραμμές που έχουν οποιοδήποτε κενό. Αποκλείουμε μόνο όσες λείπουν από τα πεδία που είναι απαραίτητα για το συγκεκριμένο workflow.

## Πρόσεξε

Το `fillna(0)` δεν είναι γενική λύση. Μηδενική latitude ή longitude είναι πραγματική γεωγραφική θέση, όχι ουδέτερη τιμή.

## QA checkpoint

```python
assert clean["longitude"].notna().all()
assert clean["latitude"].notna().all()
```

Πόσες γραμμές αφαιρέθηκαν και γιατί; Κράτησε την απάντηση πριν περάσεις στο επόμενο lesson.
