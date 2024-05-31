# Marketing_Projekt_Sentiment
**This is the repository for storing the code used for our sentiment analysis and visualisations**

## Vorgehen:

**Unser Datensatz**  
Unser Datensatz (hier zu finden: [Kaggle Dataset](https://www.kaggle.com/datasets/datasnaek/youtube?select=USvideos.csv)) besteht aus rund 1,4 Millionen YouTube-Kommentaren inklusive der Metadaten (Kategorie, Channel). Der Datensatz besteht aus den US-Kommentaren und den GB-Kommentaren. Es gibt 30 unterschiedliche Kategorien, in denen die Videos eingeteilt sind. Die Kommentare stammen von +3000 unterschiedlichen Videos und rund 1700 Kanälen.

**Datensichtung**  
Wir haben uns den Datensatz heruntergeladen und zuerst die Daten gesichtet. Die Erkenntnisse sind in der Präsentation von Folie 4 bis 7 zu finden und hier:  
[Link zum Dataexplorationcode]

**Hypothesenbildung**  
Anhand des Datensatzes haben wir uns Hypothesen überlegt, die wir im späteren Verlauf überprüfen.  
Siehe Präsentation für die Hypothesen.

**Datenvorbereitung**  
Als nächsten Schritt haben wir die Kommentare vorbereitet, um die Sentiment-Analyse durchzuführen. Beispielsweise wurden Emojis entfernt.  
Der Code für diesen Schritt ist hier auffindbar:  
[Link zum Code]

**Sentiment-Analyse**  
Nun folgt die eigentliche Sentiment-Analyse. Wir haben uns für die Bibliothek NLTK entschieden. Als Ergebnis der Sentiment-Analyse erhält jeder Kommentar einen Wert zwischen -1 und 1. Je größer der Wert, desto positiver ist das Sentiment. 

**Beispiele:**
- **Positiv:** "BEST. YOUTUBE. CHANNEL. EVER!!!" hat einen Sentimentwert von 0.9383 erhalten.
- **Neutral:** "Your voice sounds like Bob from Bob's Burgers" hat einen Sentimentwert von 0.00 erhalten.
- **Negativ:** "F*ck you ...." hat einen Sentimentwert von -0.8118 erhalten.

**Hypothesenüberprüfung**  
Nachdem wir für jeden Kommentar den Sentimentwert erhalten haben, haben wir unsere Hypothesen anhand der Werte überprüft und ggf. bestätigt oder abgelehnt.  
Siehe Präsentation für die Ergebnisse.

## Was ist eine Sentiment-Analyse?

**Definition**  
Eine Sentimentanalyse ist eine Analyse von Wörtern, Texten (bei uns Kommentaren), um die Stimmung zu ermitteln. Dafür gibt es verschiedene Techniken und Verfahren. Ziel ist, die Stimmung herauszufinden, ohne selbst die Kommentare zu lesen.

## Wie funktioniert die Sentiment-Analyse?

**Textverarbeitung**  
Bei einer Sentiment-Analyse ist der erste Schritt die Textverarbeitung. Wir benutzen das Natural Language Toolkit (NLTK). Die Funktion `SentimentIntensityAnalyzer` ist ein Teilmodul von NLTK und nutzt den VADER Algorithmus.

**VADER Algorithmus**  
Der VADER Algorithmus steht für Valence Aware Dictionary and Sentiment Reasoner. Das Modul ist darauf spezialisiert, die Stimmung von Texten zu analysieren, besonders in sozialen Medien. VADER verwendet ein vordefiniertes Lexikon von Wörtern, die mit Sentiment-Werten versehen wurden. Diese Werte wurden auf Basis von menschlicher Bewertung entwickelt. Jedes Wort im Lexikon hat einen Wert, der seine Sentiment-Polarität und Stärke darstellt.

**Regelbasierte Anpassung**  
VADER verwendet eine Reihe von Regeln, um die Kontextinformationen zu berücksichtigen. Beispiele:
- **Verstärkung:** Wörter wie "sehr" oder "extrem" verstärken die Sentimentwerte der nachfolgenden Wörter.
- **Negation:** Wörter wie "nicht" oder "kein" können die Sentiment-Polarität eines Satzes umkehren.
- **Intensitätssteigerung:** Großbuchstaben und Satzzeichen (bspw. Ausrufezeichen) können die Intensität von Sentiment verstärken.

**Berechnung des Sentimentwertes**  
Um den Sentimentwert eines Kommentares zu ermitteln:
1. **Wortauswertung:** Jedes Wort im Text wird gegen das Lexikon geprüft, um den Sentiment-Wert zu finden.
2. **Kontextanpassung:** Die Kontextregeln werden angewendet, um die Sentiment-Werte basierend auf dem Kontext anzupassen.
3. **Aggregierung:** Die angepassten Sentiment-Werte werden kombiniert, um eine Gesamtbewertung des Textes zu erstellen.

**Ausgabe der Funktion**  
Die Ausgabe der Funktion sind vier Werte:
- **Negativ (neg)**
- **Neutral (neu)**
- **Positiv (pos)**
- **Compound-Wert:** Ein normalisierter Wert zwischen -1 (sehr negativ) und 1 (extrem positiv).

**Berechnung mit vortrainiertem Modell**  
Der nächste Schritt erfolgt die Sentiment-Berechnung mithilfe des vortrainierten Modells basierend auf Wörtern und Phrasen.

**Code für die Sentiment-Analyse**  
Der Code für die Sentiment-Analyse findet sich unter:  
[Link zum Sentiment-Berechnungscode]
