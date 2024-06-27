# Marketing_Projekt_Sentiment
**This is the repository for storing the code used for our sentiment analysis and visualisations as well as to describe our goals and methods**

## Vorgehen:

**Unsere Ziele**

Unsere Hypothesen anhand der Daten belegen / widerlegen können. Außerdem möchten wir Erkenntnisse aus dem Datensatz schließen und möglicherweise Zusammenhänge erkennen.
Des Weiteren ist es wichtig, die Daten einzuordnen. Wie relevant sind die Daten? Was sind mögliche Schwächen des Datensatzes? Wie könnte man die Relevanz erhöhen?

**Unser Datensatz**  
Unser Datensatz (hier zu finden: [Kaggle Dataset](https://www.kaggle.com/datasets/datasnaek/youtube?select=USvideos.csv)) besteht aus rund 1,4 Millionen YouTube-Kommentaren inklusive der Metadaten (Kategorie, Channel). Der Datensatz besteht aus den US-Kommentaren und den GB-Kommentaren. Es gibt 30 unterschiedliche Kategorien, in denen die Videos eingeteilt sind. Die Kommentare stammen von +3000 unterschiedlichen Videos und rund 1700 Kanälen.

**Datensichtung**  
Wir haben uns den Datensatz heruntergeladen und zuerst die Daten gesichtet. Die Erkenntnisse sind in der Präsentation von Folie 4 bis 7 zu finden und hier:  
https://github.com/lucasthierry17/Marketing_Projekt_Sentiment/blob/main/data_exploration.ipynb

**Hypothesenbildung**  
Anhand des Datensatzes haben wir uns Hypothesen überlegt, die wir im späteren Verlauf überprüfen.  
Siehe Präsentation für die Hypothesen.

**Datenvorbereitung**  
Als nächsten Schritt haben wir die Kommentare vorbereitet, um die Sentiment-Analyse durchzuführen. Beispielsweise wurden Emojis entfernt.  
Der Code für diesen Schritt ist hier auffindbar:  
https://github.com/lucasthierry17/Marketing_Projekt_Sentiment/blob/main/data_exploration.ipynb

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
- **Intensitätssteigerung:** Großbuchstaben und Satzzeichen (bspw. Ausrufezeichen) können die Intensität vom Sentiment verstärken.

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
Im nächsten Schritt erfolgt die Sentiment-Berechnung mithilfe des vortrainierten Modells basierend auf Wörtern und Phrasen.

**Code für die Sentiment-Analyse**  
Der Code für die Sentiment-Analyse befindet sich unter:  
(https://github.com/lucasthierry17/Marketing_Projekt_Sentiment/blob/main/sentiment_analysis_youtube_comments.ipynb)

**Alternativen zum VADER Algorithmus**
Es gibt verschiedene Algorithmen und Ansätze, um einen Sentiment-Wert aus den Kommentaren zu berechnen. 

Eine Alternative zum VADER-Modell ist TextBlob, eine einfache Python-Bibliothek, die Sentimentanalyse durch Verarbeitung von Textdaten ermöglicht. 
Sie verwendet einen wörterbuchbasierten Ansatz, um den Text zu analysieren. 

Eine weitere Alternative ist BERT (Bidirectional Encoder Representations from Transformers), ein fortschrittliches NLP-Modell, das Kontextinformationen
in beide Richtungen berücksichtigt, um präzisere Sentimentanalysen zu ermöglichen.

## Was haben wir gelernt?
Aufgrund der Größe und Komplextität des Datensatzes mussten wir die Daten sorgfältig vorbereiten und bereinigen. Außerdem sind die Daten von der Quelle aufgeteilt in 
verschiedene Datensätze, dadurch mussten wir uns unseren Datensatz erst aus den gegebenen Daten mergen. 
Neben der Datenaufbereitung haben wir auch das Vorgehen und die Funktionsweise einer Sentiment-Analyse gelernt. Wir haben verschiedene Modelle ausprobiert und dabei aufgrund der Datengröße auch auf die Effizienz der Modelle schauen. 
Zuletzt haben wir uns im Umgang mit Git, Github und Python weiter verbessert. Diese Tools haben wir im Zuge unseres Projektes benutzt.

## Welche Risiken / Schwachstellen sehen wir?
Obwohl der Datensatz Kommentare aus vielfältigen Videos und Kategorien enthält, ist er nicht optimal diversifiziert. Das birgt das Risiko, sich anhand des Datensatzes zu 
falschen Schlussfolgerungen leiten zu lassen. 
Eine weitere Schwachstelle ist der Zeitraum der aufgenommenen Daten. Knapp vier Wochen von Kommentaren liegen uns im Datensatz vor. Um die Aussagekraft zu verbessern, könnte man den Zeitraum der Daten ausweiten und ggf. auch weitere Länder mit einbeziehen. 









