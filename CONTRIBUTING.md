# Contributing to Phishing Detector

## Setup

```bash
git clone https://github.com/builtbysardor/phishing-detector.git
cd phishing-detector
pip install -r requirements.txt

# Train the model
python ml/train_model.py

# Start API
uvicorn backend.main:app --reload
# → http://localhost:8000
```

## Adding Training Data

Edit `ml/generate_data.py` to add more phishing/legitimate email samples.
Re-run training after changes: `python ml/train_model.py`

## Model Architecture

- **Vectorizer**: TF-IDF on combined subject + body + sender features
- **Classifier**: Multinomial Naive Bayes
- **Threshold**: 0.7 confidence for phishing classification
