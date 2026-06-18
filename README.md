# Eurovision_2026

# Eurovision Song Contest 2026 Prediction Pipeline

Questo repository ospita un progetto end-to-end di Machine Learning focalizzato sulla **predizione dei risultati dell'Eurovision Song Contest 2026**, limitatamente all'utilizzo di **modelli lineari e probabilistici classici**. 

L'obiettivo scientifico è dimostrare come un fenomeno socio-culturale complesso, fortemente influenzato da geopolitica e fan-engagement, possa essere decomposto e modellato in componenti additive interpretabili senza ricorrere ad architetture black-box non lineari.

---

## 📊 Panoramica del Progetto & Architettura

Il framework integra quattro fonti di dati eterogenee:
1. **Dati Storici ESC (2016–2025):** Risultati ufficiali, voti delle giurie e del televoto.
2. **Audio Features (Spotify API):** Caratteristiche intrinseche dei brani (danceability, energy, acousticness, ecc.).
3. **Voti Bilaterali Storici:** Matrici di preferenza sistematica e storica tra nazioni (alleanze geopolitiche di voto).
4. **Dati Gravitazionali (CEPII):** Distanza geografica, contiguità e confini linguistici/culturali tra i paesi.

L'intero impianto epistemologico si articola su tre Task complementari:

* **Task A — Regressione (`Points_Final`):** Stima del punteggio totale ottenuto in Finale tramite Ordinary Least Squares (**OLS**), **Ridge** e **Lasso** Regression (regolarizzazione L2 ed L1 per la gestione della multicollinearità).
* **Task B — Classificazione Binaria (`Grand_Final_Ind`):** Predizione della qualificazione alla Grand Final contrapponendo approcci discriminativi (**Logistic Regression**) e generativi (**LDA**, **QDA**, **Naive Bayes**).
* **Task C — Classificazione Multi-classe:** Categorizzazione delle nazioni in fasce di piazzamento finali (Top 5, Top 10, Flop, ecc.).

---

## 🛠️ Pipeline Econometrica e di Machine Learning

1. **Feature Engineering & Gravity Models:** Introduzione di *Gravity Features* derivate dai dataset CEPII per pesare l'interazione stocastica del televoto transfrontaliero in base alla prossimità geografica e socio-linguistica.
2. **Standardizzazione:** Trattamento delle feature continue per garantire l'equità delle penalizzazioni nei modelli regolarizzati.
3. **Validazione Temporale Rigorosa:** Suddivisione dei dati rispettando la sequenzialità temporale degli eventi (evitando il *data leakage* trans-temporale tipico delle K-Fold cross-validation standard su serie storiche).

---

## 📈 Risultati Principali e Conclusioni

* **Convergenza dei Confini di Separazione:** La forte coerenza e stabilità tra Logistic Regression e Linear Discriminant Analysis (LDA) nel Task B evidenzia la linearità intrinseca del confine di separazione fra nazioni qualificate ed eliminate.
* **Potere del Fan-Engagement:** L'introduzione del segnale di engagement pre-evento si è rivelata la feature a più alto peso specifico, agendo da fortissimo regolarizzatore naturale del rumore stocastico del contest.
* **Interpretabilità vs Complessità:** Il progetto valida l'efficacia dei modelli lineari come solidi strumenti di analisi quantitativa anche in domini ad altissima volatilità socio-culturale, producendo stime predittive coerenti e diagnosticamente leggibili.

---

## 🚀 Come Eseguire il Progetto

### Requisiti
Assicurati di avere installato Python (>= 3.10) e le librerie elencate in `requirements.txt` (scikit-learn, pandas, numpy, matplotlib, seaborn).

```bash
# Clona il repository
git clone [https://github.com/TUO-USERNAME/eurovision-2026-prediction.git](https://github.com/TUO-USERNAME/eurovision-2026-prediction.git)

# Entra nella cartella
cd eurovision-2026-prediction

# Esegui il Notebook Jupyter
jupyter notebook Eurovision_2026_Final_perdavvero.ipynb
