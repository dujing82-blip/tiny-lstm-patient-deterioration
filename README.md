# Tiny LSTM Patient Deterioration

A classroom project for learning **why LSTM was invented**.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dujing82-blip/tiny-lstm-patient-deterioration/blob/main/LSTM_Patient_Deterioration.ipynb)

> **Educational demo only.** The dataset is synthetic. This repository is not a clinical model and must not be used for patient care.

## The question

Can a sequence model use 24 hours of vital signs to recognize a deterioration pattern?

```text
24 hours × 3 vital signs
          ↓
   SimpleRNN / LSTM
          ↓
 deterioration / stable
```

The three features are heart rate, respiratory rate, and oxygen saturation (SpO₂).

## Why this example?

Some synthetic deterioration cases contain an important warning pattern early in the 24-hour sequence followed by partial recovery. This creates a simple long-term-memory problem.

Students first train a `SimpleRNN(16)`, then replace it with `LSTM(16)` while keeping the rest of the model nearly identical.

## Dataset

`patient_vital_signs.csv` contains 1,200 synthetic patients, each with 24 hourly observations (28,800 rows total). The data is pre-generated and stored in this repository; the Colab notebook only loads it.

## Learning goals

- Review RNN input shape: `[examples, time steps, features]`
- Understand why patient history is a sequence
- Compare SimpleRNN and LSTM
- Explore long-term dependencies
- Motivate LSTM cell state and gates
- Use built-in Binary Crossentropy for binary classification

## Run

Click **Open in Colab** above and choose **Runtime → Run all**.

## License

MIT.
