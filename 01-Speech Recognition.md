# Speech Recognition

## Overview

- speech --speech recognition--> text
  - input: speech 
    - a sequence of vector (T, D)
      - T: length
      - D: feature dimension
  - output: text
    - a sequence of token (N, V)
      - N: length
      - V: vocabulary size
  - usually, T >> N

---

- Token
  - phoneme: smallest unit of sound
    - need lexicon 
  - grapheme: smallest unit of writing
    - en: 26 letters + {_}(space) + {punctuation marks}
    - zh: 4000+ characters 
  - word: usually V>100K
  - morpheme: smallest unit of meaning
    - grapheme < **morpheme** < word
    - en: {un, happy, ness} {un, break, able}
    - linguistic or statistic
  - bytes: Language independent
    - byte pair encoding (BPE)

```mermaid
pie title Token
  "phoneme" : 32
  "grapheme" : 41
  "word" : 10
  "morpheme" : 17
```

---

- Acoustic Feature

```mermaid
graph LR
  A[waveform] --DFT--> B[spectrogram]
  B --filter bank--> C[filter bank output]
  C --log DCT--> D[MFCC]
```

![acous](images/acoustic_feature.png)

```mermaid
pie title Acoustic Feature
  "filter bank output" : 75
  "MFCC" : 18
  "spectrogram" : 2
  "waveform" : 4
  "others" : 1
```

---

- data
  - timit 4hr
  - wsj 80hr
  - switchboard 300hr
  - librispeech 960hr
  - fisher 2000hr
- views
  - seq2seq
  - HMM
- models
  - LAS
  - CTC
  - RNN-T
  - Nerual Transducer
  - MoChA