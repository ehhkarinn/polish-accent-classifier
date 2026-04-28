# polish-accent-classifier

Accent classifier for fake Polish-accented English
# Overview

This project investigates the phonetic gap between **authentic Polish-accented English** and its **cinematic imitation** in Hollywood films. Using a sociophonetic framework alongside a **feedforward neural network (FFNN)**, it compares phonetic features present in real Polish-accented English with those performed by actors portraying Polish characters.
The core finding: actors do not reproduce Polish-accented English accurately. Instead, they produce a **generic Slavic-sounding accent** — confirmed both through phonetic analysis and FFNN misclassification patterns.

---

# Research Questions

1. Which phonetic features characterise authentic Polish-accented English, and which do actors actually use?
2. Can a machine learning model distinguish real from imitated Polish-accented English, and with what confidence?

---
# Key Results

**18 film samples across 6 productions were classified by the FFNN:**

| Predicted Label | Count |
|---|---|
| Polish | 10 |
| Ukrainian | 7 |
| British | 1 |

**Notable findings:**

- **Meryl Streep** (*Sophie's Choice*) received the lowest Polish confidence score (0.37) and was also classified as British (0.88) and Ukrainian (0.69) across samples — the least phonetically accurate performance in the dataset
- **The Immigrant** showed the most consistent Polish classifications (0.55, 0.98, 0.62)
- The high rate of **Ukrainian misclassifications** across films is the central finding: it suggests actors rely on generic Slavic cues rather than Polish-specific phonology

---

## Full Classification Table

| Film | Sample | Predicted | Confidence |
|---|---|---|---|
| Defiance | defiance_01 | Polish | 0.83 |
| Defiance | defiance_02 | Ukrainian | 1.00 |
| Defiance | defiance_03 | Ukrainian | 0.99 |
| Sophie's Choice | sophies_choice_01 | Polish | 0.37 |
| Sophie's Choice | sophies_choice_02 | Ukrainian | 0.69 |
| Sophie's Choice | sophies_choice_03 | British | 0.88 |
| The Zookeeper's Wife | zoo_01 | Polish | 0.98 |
| The Zookeeper's Wife | zoo_02 | Ukrainian | 0.94 |
| The Zookeeper's Wife | zoo_03 | Polish | 0.80 |
| The Immigrant | immigrant_01 | Polish | 0.55 |
| The Immigrant | immigrant_02 | Polish | 0.98 |
| The Immigrant | immigrant_03 | Polish | 0.62 |
| The Way Back | way_01 | Ukrainian | 0.60 |
| The Way Back | way_02 | Polish | 0.78 |
| The Way Back | way_03 | Ukrainian | 1.00 |
| Courageous Heart | heart_01 | Polish | 0.86 |
| Courageous Heart | heart_02 | Ukrainian | 0.67 |
| Courageous Heart | heart_03 | Ukrainian | 0.87 |

---

## Phonetic Analysis Summary

Authentic Polish-accented English is characterised by:
- Word-final obstruent devoicing (e.g. /d/ → [t])
- Substitution of interdental fricatives /θ, ð/ with dental stops /t, d/
- Trill /r/ in place of the English approximant
- Reduced vowel reduction
- Difficulty distinguishing /iː/ and /ɪ/
- Irregular word stress placement

Actor performances were **inconsistent across all features**. The trill /r/ was the most frequently reproduced feature — likely because it functions as a cultural shorthand for 'foreignness'. Features requiring finer phonological knowledge (vowel quality, stress patterns, final devoicing rules) were largely absent or misapplied.

---

## Pipeline

```
Film audio extraction
        ↓
MFCC feature extraction
        ↓
FFNN training on reference accent recordings
(Polish, Ukrainian, British categories)
        ↓
Classification of 18 film samples
        ↓
Phonetic analysis via spectrographic comparison
```

---

## Tools & Technologies

- Python
- Mel-frequency cepstral coefficients (MFCCs)
- Feedforward Neural Network (FFNN)
- Spectrographic analysis
- Google Colab

---

## Films Analysed

- *Sophie's Choice* (1982)
- *Defiance* (2008)
- *The Immigrant* (2013)
- *The Zookeeper's Wife* (2017)
- *The Way Back* (2010)
- *Courageous Heart* (2012)

---
