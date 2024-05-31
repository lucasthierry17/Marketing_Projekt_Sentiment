# Marketing_Projekt_Sentiment
This is the repository for storing the code used for our sentiment analysis and visualisations

Vorgehen: 
Unser Datensatz (hier zu finden: https://www.kaggle.com/datasets/datasnaek/youtube?select=USvideos.csv) besteht aus rund 1,4 Millionen YouTube-Kommentaren inklusive der Metadaten (Kategorie, Channel). 
Der Datensatz besteht aus den US-Kommentaren und den GB-Kommentaren.
Es gibt 30 unterschiedliche Kategorien, in denen die Videos eingeteilt sind. Die Kommentare stammen von +3000 unterschiedlichen Videos und rund 1700 Kanälen. 

Wir haben uns den Datensatz heruntergeladen und zuerst die Daten gesichtet. Die Erkenntnisse sind in der Präsentation von Folie 4 bis 7 zu finden und hier: 
LinkzumDataexplorationcode

Anhand des Datensatzes haben wir uns Hypothesen überlegt, die wir im späteren Verlauf überprüfen. 
Siehe Präsentation für die Hypothesen.

Als nächsten Schritt haben wir die Kommentare vorbereitet, um die Sentiment-Analyse durchzuführen. Beispielsweise wurden Emojis entfernt. 
Der Code für diesen Schritt ist hier auffindbar: 

Nun folgt die eigentliche Sentiment-Analyse. Wir haben uns für die Bibliothek NLTK entschieden. 
Als Ergebnis der Sentiment-Analyse erhält jeder Kommentar einen Wert zwischen -1 und 1. Je größer der Wert desto positiver ist das Sentiment. 
Beispiele: 
- "BEST. YOUTUBE. CHANNEL. EVER!!!" hat einen Sentimentwert von 0.9383 erhalten (sehr positiv)
- "Your voice sounds like Bob from Bob's Burgers hat einen Sentimentwert von 0.00 erhalten (neutral)
- "F*ck you ...." hat einen Sentimentwert von -0.8118 erhalten (sehr negativ)

Nachdem wir für jeden Kommentar den Sentimenetwert erhalten haben, haben wir unsere Hypothesen anhand der Werte überprüft und ggf. bestätigt oder abgelehnt. 
Siehe Präsentation für die Ergebnisse. 

Was ist eine Sentiment-Analyse ?
Eine Sentimentanalyse ist eine Analyse von Wörtern, Texten (bei uns Kommentaren) um die Stimmung zu ermitteln.
Dafür gibt es verschiedene Techniken und Verfahren. Ziel ist, die Stimmung herauszufinden, ohne selbst die Kommentare zu lesen. 

Wie funktioniert die Sentiment-Analyse?
Bei einer Sentiment-Analyse ist der erste Schritt die Textverarbeitung. 
Als nächsten erfolgt die Sentiment Berechnung mithilfe des vortrainierten Modells basierend auf Wörtern und Phrasen. 

Der Code für die Sentiment-Analyse findet sich unter: 
