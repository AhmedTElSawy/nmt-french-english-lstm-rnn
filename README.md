# French-to-English Neural Machine Translation (NMT)

A Sequence-to-Sequence (Seq2Seq) model using an Encoder-Decoder RNN architecture with LSTM layers to translate French sentences into English.

## Overview
- **Dataset**: ManyThings.org French-English dataset (processed 15,000 pairs).
- **Model**: Encoder-Decoder architecture using Keras 3.
  - **Encoder**: Embedding layer (256 units) followed by an LSTM layer (256 units).
  - **Decoder**: RepeatVector and a second LSTM layer (256 units) followed by a TimeDistributed Dense layer with Softmax activation.
- **Preprocessing**: 
  - Unicode normalization and punctuation removal.
  - Post-padding sequences to maximum sentence length (French: 11, English: 5).
  - One-hot encoding for the target output vocabulary.
- **Training**: Optimized with Adam and Categorical Cross-Entropy loss over 30 epochs.
- **Results**: 
  - **Training BLEU-4**: ~0.79
  - **Testing BLEU-4**: ~0.31

## How to Run
1. Clone the repo: `git clone https://github.com/AhmedTElSawy/nmt-french-english-lstm-rnn.git`
2. Install dependencies: `pip install -r requirements.txt`
3. Open and run the notebook: `jupyter notebook rnn-lstm-translator.ipynb`

## Dependencies
- TensorFlow/Keras
- NumPy
- NLTK (for BLEU evaluation)
- Pickle
- Unicodedata
