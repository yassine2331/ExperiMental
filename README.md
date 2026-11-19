# ExperiMental

Machine learning and deep learning on mobile and wearable devices (phones and Garmin watches) to predict
**EMA** (Ecological Momentary Assessment) responses, such as mental health indicators, from sensor data.
The models come with **explanations**, mainly counterfactual ones ("what would need to change for the
prediction to be different?").

The workflow is:

1. **Train** models (classical ML and deep learning) to predict the EMA responses.
2. **Run** the models on the devices and measure how well they perform there.
3. **Explain** the predictions with counterfactual explanations.

> Participant data is sensitive and is never committed to this repository.

## Getting started

```bash
python -m venv .venv && source .venv/bin/activate
pip install -e ".[dev]"
```

## Project structure

```
ExperiMental/
├── configs/              # Settings for data, models, experiments and explanations
├── data/                 # Local only, never committed (sensitive)
├── src/emaml/            # Main Python package
│   ├── data/             # Loading phone, watch and EMA data
│   ├── features/         # Turning raw signals into model inputs
│   ├── targets/          # Definitions of what we predict
│   ├── models/           # Classical ML and deep learning models
│   ├── training/         # Training and validation
│   ├── evaluation/       # Metrics and results
│   ├── explain/          # Counterfactual explanations and other explanation methods
│   ├── export/           # Converting models to run on phones and watches
│   └── utils/            # Shared helpers
├── scripts/              # Commands to run each step (preprocess, train, evaluate, explain, export)
├── notebooks/            # Exploration and analysis
├── experiments/          # Results of experiment runs (local only)
├── models/               # Trained and exported models (local only)
├── deploy/               # On-device apps
│   ├── android/          # Android app
│   ├── ios/              # iOS app
│   ├── garmin/           # Garmin watch app
│   └── benchmarks/       # Speed, memory and battery measurements on devices
├── tests/                # Automated tests
└── docs/                 # Documentation
```
