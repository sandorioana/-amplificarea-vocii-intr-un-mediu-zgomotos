
##  Scopul proiectului

Amplificarea vocii într-un mediu zgomotos folosind metode tradiționale (ICA, filtrare Wiener) și rețele neuronale (Autoencoder, LSTM).


 📁 Structura proiectului

- `ProjectPSVsandorIOANA_GATA.ipynb` – codul principal în Google Colab
- `UrbanSound8K.tar.gz`, `test-clean.tar.gz` – seturi de date audio
- Fișiere rezultate: audio separat, grafice, valori SNR

---

## Cum se rulează

1. Deschide `ProjectPSVsandorIOANA_GATA.ipynb` în [Google Colab](https://colab.research.google.com)
2. Încarcă fișierele `.tar.gz` în Google Drive
3. Rulează celulele în ordine:
   - Instalare librării
   - Montare Drive
   - Extracție date
   - Aplicare ICA și Wiener
   - Antrenare rețele neuronale
   - Comparație folosind SNR

---

##  Cerințe

- Python 3.8+
- Biblioteci:
  - `librosa`, `scikit-learn`, `tensorflow`
  - `numpy`, `pandas`, `scipy`, `matplotlib`

---

## Rezultate

- Spectrograme audio procesate
- Fișiere audio redabile
- Metrici obiective: SNR înainte și după procesare

---

##  Extensii posibile

- Separare audio în timp real
- Aplicații pentru asistenți vocali
- Reducerea zgomotului în apeluri sau podcasturi
