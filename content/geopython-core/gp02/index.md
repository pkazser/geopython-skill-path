# GP02 — Clean Geospatial Data

## Τι θα κάνουμε

Στο GP01 έμαθες να ακολουθείς ένα GeoPython workflow. Τώρα θα μάθεις να αντιμετωπίζεις τα προβλήματα που συναντάμε πριν εμπιστευτούμε ένα dataset.

Θα δουλέψουμε με ένα μικρό CSV που περιέχει κενές τιμές, διπλότυπα, λάθος τύπους και προβληματικές συντεταγμένες.

**Κατανοώ → Εντοπίζω → Διορθώνω → Επαληθεύω → Εξάγω**

## Μαθησιακοί στόχοι

- να εντοπίζεις missing values και διπλότυπα,
- να ελέγχεις και να διορθώνεις τύπους δεδομένων,
- να αναγνωρίζεις μη έγκυρες συντεταγμένες,
- να ελέγχεις κενές και invalid γεωμετρίες,
- να κρατάς τεκμηριωμένα μόνο τις διορθώσεις που χρειάζονται,
- να εκτελείς επαναλήψιμα GeoPython QA checks.

## Άνοιξε τα notebooks στο Google Colab

### Πρακτική άσκηση στο Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/starter/gp02_clean_geospatial_data_starter.ipynb)

### Ενδεικτική λύση

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pkazser/geopython-skill-path/blob/main/notebooks/solution/gp02_clean_geospatial_data_solution.ipynb)

## Το dataset

Το `data/gp02/observations_dirty.csv` είναι σκόπιμα ατελές. Δεν διορθώνουμε σιωπηλά τα πάντα: πρώτα μετράμε το πρόβλημα, μετά επιλέγουμε κανόνα και στο τέλος ελέγχουμε το αποτέλεσμα.
