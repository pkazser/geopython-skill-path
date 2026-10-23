# 1. Από CSV σε GIS dataset

## Τι θα μάθεις

Το CSV είναι πίνακας τιμών. Για να γίνει GIS dataset χρειάζεται geometry και CRS.

```python
import pandas as pd

df = pd.read_csv("data/gp03/city_assets.csv")
print(df.columns)
print(df.dtypes)
```

Τα `asset_id`, `asset_type` και `condition` είναι περιγραφικά πεδία. Τα `longitude` και `latitude` είναι οι είσοδοι για τη geometry.

## Η νοητική μετατροπή

```text
γραμμή CSV
    ↓
attribute row + Point geometry + CRS
    ↓
GIS feature
```

## Checkpoint

Πριν συνεχίσεις, βρες ποια στήλη είναι μοναδικό ID και ποια πεδία θα χρησιμοποιήσεις για X και Y.
