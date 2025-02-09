Questo progetto di data intelligence sul calcio analizza i calci d'angolo della Serie A 2021-2022 per valutare e analizzare un modello di expected assist (xA). L'obiettivo è comprendere quali situazioni da calcio d'angolo portano maggiori benefici offensivi.

**Titolo del Progetto:** Analisi degli Expected Assist da Calci d'Angolo nella Serie A 2021-2022

**Descrizione:**
Questo progetto utilizza dati di eventi posizionali per sviluppare un modello di regressione logistica semplificato per stimare gli expected assist (xA) derivanti da calci d'angolo. L'analisi è focalizzata sulla stagione 2021-2022 della Serie A. Il modello mira a individuare le situazioni di calcio d'angolo che offrono il maggiore vantaggio offensivo.

**Dataset Utilizzati:**
*   **Dati posizionali da calcio d'angolo SICS:** Il dataset principale contiene dati posizionali relativi ai calci d'angolo della Serie A 2021-2022.
*   **Database piede preferito:** Contiene informazioni sul piede preferito dei giocatori, utili per la classificazione dei cross.
*   **Dataset ID giocatori:** Contiene gli ID dei giocatori, usato per il merge dei dataset.

**Struttura del Progetto:**
Il progetto è diviso in diverse fasi principali:

1.  **Preparazione dei Dati:**
    *   Importazione e pulizia dei dati da diverse fonti.
    *   Creazione di un dataset unificato tramite merge dei dataset.
    *   Selezione degli eventi di interesse, ovvero i calci d'angolo.
2.  **Classificazione dei Calci d'Angolo:**
    *   I calci d'angolo sono classificati in quattro gruppi (A, B, C, D) in base alla posizione del calcio d'angolo (destra o sinistra) e al piede preferito del calciatore che effettua il cross.
    *   Gruppo A: angolo destro, piede destro (cross con effetto a uscire)
    *  Gruppo B: angolo sinistro, piede sinistro (cross con effetto a uscire)
    *  Gruppo C: angolo destro, piede sinistro (cross con effetto a rientrare)
    *  Gruppo D: angolo sinistro, piede destro (cross con effetto a rientrare)
3.  **Implementazione del Modello:**
    *   Sviluppo di un modello di regressione logistica per stimare gli expected assist.
    *   Il modello è di tipo shot-centric, ovvero l'assist è legato alla ricezione del passaggio da parte del tiratore.
    *   Le variabili predittive utilizzate nel modello sono la distanza e l'angolo rispetto alla porta.
4.  **Analisi dei Dati:**
    *   Valutazione del modello tramite ROC AUC score.
    *   Analisi della correlazione tra expected assist e assist effettivi.
    *   Confronto dei risultati tra i diversi gruppi di calci d'angolo.
    *   Analisi della precisione probabilistica del modello.
    *   Analisi del conversion rate in funzione della distanza e dell'angolo di tiro.

**Librerie Python Utilizzate:**
*   **pandas:** Per la manipolazione e l'analisi dei dati.
*   **numpy:** Per operazioni matematiche.
*   **seaborn:** Per la visualizzazione dei dati.
*   **matplotlib.pyplot:** Per la creazione di grafici.
*   **scipy:** Per funzioni statistiche e di interpolazione.
*  **sklearn.linear_model:** Per l'implementazione del modello di regressione logistica.
*   **sklearn.metrics:** Per la valutazione del modello.
*   **mplsoccer:** Per la visualizzazione di campi da calcio e heatmap.
*   **highlight_text:** Per evidenziare testo in grafici.

**Risultati Chiave:**
*   I calci d'angolo con cross ad effetto a rientrare (Gruppi C e D) generano un beneficio offensivo maggiore in termini di assist rispetto a quelli con cross ad effetto a uscire (Gruppi A e B).
*   Il modello, nonostante alcune limitazioni, è in grado di descrivere gli expected assist in modo sommario.
*   I valori di ROC AUC mostrano che il modello è abbastanza affidabile.
*   Il modello ha una buona precisione probabilistica.
*   Esiste una correlazione lineare tra i valori del modello di expected assist e gli assist effettivi.
*  Il modello può essere migliorato allenandolo su un set di dati più ampio e considerando altri parametri di dipendenza.

**Miglioramenti Futuri:**
*   Aumentare la base di dati con stagioni precedenti e/o altri campionati.
*   Considerare ulteriori parametri come la posizione dei giocatori della squadra in campo.
*  Analizzare la posizione dei giocatori della squadra avversaria.

**Note Importanti:**
*   I dati posizionali sono stati normalizzati.
*   Il modello di expected assist è considerato simile a quello di expected goal.
*  È stata fatta l'ipotesi che tutti i passaggi presi in considerazione derivano da calcio d'angolo.
