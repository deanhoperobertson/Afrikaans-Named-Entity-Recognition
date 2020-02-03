# Afrikaans Named Entity Recognition

This repository explores different techiques used for Named Entity Recognition (NER) on the NCHLT Afrikaans Named Entity Annotated Corpus. The data can be found here: https://repo.sadilar.org/handle/20.500.12185/299 and was curated by the South African Department of Science and Innnovation.

The onyl statistcial models currently built on this data was by Roald Eiselen (Univerity of Potchefstroom). Reults can be found here:https://www.aclweb.org/anthology/L16-1533.pdf attaining an average F1 score of **75.86** with the hightest score achievied of **77**.

## Models
### Feature Engineered
- Conditional Random Fields [w] (F1=**75.19**) 
- Conditional Random Fields [w-1] (F1=**76.19**) 
- Conditional Random Fields [w-2] (F1=**77.64**) 
- Conditional Random Fields [w-3] (F1=**76.83**) 

### Neural Network 
- BiLSTM-CRF (FastText Wiki 300D 99k) (F1=**61.6**)
- BiLSTM-CRF (Casing Features + FastText Wiki 300D 800k) (F1=**??**)

### Results
We managed to attain the same results (if not better) using a Conditional Random Field approach and add more *engineered features* than the orginal paper by Roald Eiselen. 

*Error Analysis*: Afrikaans word embedding used in the BiLSTM-CRF is missing 33%-39% of the words use in the NCHLT Afrikaans NER Corpus. I used the FastText Afrikaans pre-trained word embeddings trained on Wikipedia found at:
https://fasttext.cc/docs/en/pretrained-vectors.html 

