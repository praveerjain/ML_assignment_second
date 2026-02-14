# 🌌 Stellar Classification - Model Comparison

---

## a. Problem Statement
The goal of this project is to classify celestial objects (Galaxy, Star, Quasar) using machine learning models.  We aim to preprocess the dataset, perform feature selection, train multiple classifiers, and evaluate their performance using standard metrics. The comparison helps identify which model performs best for stellar classification tasks.

---

## b. Context of data
In astronomy, stellar classification refers to the categorization of stars according to their spectral properties. Extending beyond stars, the classification of galaxies and quasars based on their spectra forms one of the foundational frameworks of the field. Early efforts to catalogue stars and map their distribution across the sky revealed that they constitute our own galaxy. The recognition of Andromeda as a distinct galaxy marked a turning point, after which increasingly powerful telescopes enabled systematic surveys of countless galaxies. This dataset is designed to classify stars, galaxies, and quasars by analysing their spectral characteristics

---

## b. Dataset Description
The data consists of 100,000 observations of space taken by the SDSS (Sloan Digital Sky Survey). Every observation is described by 17 feature columns and 1 class column which identifies it to be either a star, galaxy or quasar. Below are the parameters which are used of classification of stellar objects:-
1.	alpha = Right Ascension angle (at J2000 epoch)
2.	delta = Declination angle (at J2000 epoch)
3.	u = Ultraviolet filter in the photometric system
4.	g = Green filter in the photometric system
5.	r = Red filter in the photometric system
6.	i = Near Infrared filter in the photometric system
7.	z = Infrared filter in the photometric system
8.	run_ID = Run Number used to identify the specifikc scan
9.	rereun_ID = Rerun Number to specify how the image was processed
10.	cam_col = Camera column to identify the scanline within the run
11.	field_ID = Field number to identify each field
12.	spec_obj_ID = Unique ID used for optical spectroscopic objects (this means that 2 different observations with the same spec_obj_ID must share the output class)
13.	redshift = redshift value based on the increase in wavelength
14.	plate = plate ID, identifies each plate in SDSS
15.	MJD = Modified Julian Date, used to indicate when a given piece of SDSS data was taken
16.	fiber_ID = fiber ID that identifies the fiber that pointed the light at the focal plane in each observation

---

## c. Models Used

### Comparison Table of Evaluation Metrics

| ML Model Name        | Accuracy | AUC   | Precision | Recall | F1   | MCC   |
|----------------------|----------|-------|-----------|--------|------|-------|
| Logistic Regression  | 0.9283   | 0.9776| 0.9293    | 0.9283 |0.9277|0.8719 |
| Decision Tree        | 0.9631   | 0.9672| 0.9630    | 0.9631 |0.9630|0.9345 |
| kNN                  | 0.9269   | 0.9675| 0.9278    | 0.9269 |0.9266|0.8692 |
| Naive Bayes          | 0.7431   | 0.7902| 0.7902    | 0.7432 |0.6905|0.5372 |
| Random Forest (Ens.) | 0.9781   | 0.9952| 0.9780    | 0.9781 |0.9779|0.9611 |
| XGBoost (Ens.)       | 0.9758   | 0.9956| 0.9756    | 0.9758 |0.9756|0.9570 |

---

### Observations on Model Performance

| ML Model Name        | Observation about model performance |
|----------------------|--------------------------------------|
| Logistic Regression  | Performs well on linearly separable data; moderate accuracy and balanced metrics. |
| Decision Tree        | Easy to interpret; prone to overfitting; performance depends on depth and pruning. |
| kNN                  | Sensitive to scaling and choice of k; performs reasonably but it is observed to have higher processing time.|
| Naive Bayes          | It assumes that all the parameters are independent to each other, in reality most of the features are correlated. It produces relatively simple boundaries, which fail to capture complex, non-linear relationships. It is fast but less accurate compared to ensemble methods. |
| Random Forest (Ens.) | Strong performance due to ensemble averaging; robust against overfitting; high accuracy and F1. |
| XGBoost (Ens.)       | Best overall performance; handles complex relationships; high accuracy, precision, and MCC. |

---
