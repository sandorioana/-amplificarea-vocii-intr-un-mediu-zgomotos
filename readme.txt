
Proiect:Amplificarea vocii într-un mediu zgomotos

Scopul proiectului:
Implementarea unei aplicații complete pentru reducerea zgomotului din semnale vocale folosind atât metode clasice (Wiener, ICA), cât și metode moderne bazate pe rețele neuronale (CNN+LSTM), cu evaluare pe fișiere vocale reale și compararea performanței la diferite niveluri de zgomot (SNR 5dB și 10dB).

Structura proiectului:
├── README.txt
├── main.py (script principal)
├── model/
│   └── model_denoising_final.h5 (model antrenat)
├── utils/
│   ├── filtering.py (aplicarea filtrării Wiener și ICA)
│   └── apply_methods.py (compară metodele)
├── results/
│   ├── waveform_comparison.png
│   ├── spectrogram_comparison.png
│   └── training_metrics.png
├── data/
│   ├── clean_voice.wav
│   ├── noisy_voice.wav
│   └── ad_hoc_sample.wav
└── notebooks/
    └── analysis.ipynb (analiză și vizualizări)

 Resurse necesare pentru instalare:
Python 3.8+
Biblioteci Python (se instalează automat în Colab):
librosa -procesare audio
tensorflow  -rețele neuronale
scikit-learn
scipy - preprocesare și metrici
matplotlib
pandas
numpy


Fișiere necesare:
ProjectPSVsandorIOANA_GATA.ipynb— notebook-ul cu tot codul
"C:\Users\sando\Desktop\psvproiectfinal\ProjectPSVsandorIOANA_GATA.ipynb"
UrbanSound8K.tar.gz — arhivă cu  zgomote
test-clean.tar.gz — arhivă cu înregistrări de voce (LibriSpeech)


Metode implementate:
1. Filtrare Wiener– eliminare adaptivă a zgomotului
2. ICA – extragerea sursei vocale dintr-un amestec
3. CNN + LSTM – model hibrid antrenat pe segmente de voce zgomotoasă
   - Encoder: 2 straturi Conv1D + MaxPooling
   - Bottleneck: Dense(256) + Dropout
   - Clasificator: Dense(10, softmax)
   - Decoder: Dense → Reshape → LSTM → Conv1D + UpSampling
4. Comparare denoising la 5dB vs 10dB
5. Aplicare metode  pe fișier ad-hoc – semnal extern procesat complet

Evaluare performanță:
- SNR inițial vs. SNR după denoising
- Acuratețe clasificare energie vocală
- Metrici: MAE, MSE, RMSE

Rezultat: Modelul CNN+LSTM a obținut o acuratețe de până la 98%, depășind metodele clasice la calitatea semnalului.
          Modelul a fost testat și pe fișiere vocale externe. Fișierul `ad_hoc_sample.wav` din folderul `/data` demonstrează aplicabilitatea reală.


Cum rulezi proiectul:
1. Instalează dependințele:
   `pip install -r requirements.txt`
2. Rulează scriptul principal:
   `python main.py`

Etape de lucru/*Instrucțiuni de rulare:
Deschide Google Colab
Încarcă notebook-ul  ProjectPSVsandorIOANA_GATA.ipynb
Încărcarea și preprocesarea fișierelor audio din două seturi de date: UrbanSound8K și LibriSpeech;
Rulează celulele din notebook în ordine:
3. Rulează celulele în ordine:
   - Instalarea automată a bibliotecilor
   - Montarea Google Drive
   - Dezarhivarea seturilor de date
   - Procesarea audio și antrenarea rețelei
   - Vizualizarea și ascultarea rezultatelor
Se vizualizarea spectrogramele și se afișeaza rezultatele sub formă grafică;
Redarea fișierelor audio înainte și după procesare pentru evaluare auditivă.



 