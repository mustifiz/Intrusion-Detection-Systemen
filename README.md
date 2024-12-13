# NSL-KDD Datensatzanalyse

Dieses Projekt befasst sich mit der Analyse des **NSL-KDD-Datensatzes**, einem bekannten Datensatz im Bereich **Netzwerksicherheit** und **Cybersicherheit**. Der NSL-KDD-Datensatz behebt die Einschränkungen des ursprünglichen KDD'99-Datensatzes und bietet eine verbesserte Datenqualität für die Forschung zur Erkennung von Netzwerkangriffen.

## Über den Datensatz

Der NSL-KDD-Datensatz wurde entwickelt, um maschinelle Lernalgorithmen zur Erkennung von Netzwerkangriffen zu evaluieren. Er enthält markierte Datensätze des Netzwerkverkehrs, die entweder als normal oder als Angriffstyp kategorisiert sind. Der Datensatz ist in Trainings- und Testdatensätze unterteilt und umfasst die folgenden Komponenten:

- **KDDTrain+.ARFF**: Vollständiger Trainingsdatensatz mit binären Labels (ARFF-Format).
- **KDDTrain+.TXT**: Vollständiger Trainingsdatensatz mit Angriffstyp-Labels und Schwierigkeitsgrad (CSV-Format).
- **KDDTrain+_20Percent.ARFF**: Ein 20%-Teil des KDDTrain+.ARFF-Datensatzes.
- **KDDTrain+_20Percent.TXT**: Ein 20%-Teil des KDDTrain+.TXT-Datensatzes.
- **KDDTest+.ARFF**: Vollständiger Testdatensatz mit binären Labels (ARFF-Format).
- **KDDTest+.TXT**: Vollständiger Testdatensatz mit Angriffstyp-Labels und Schwierigkeitsgrad (CSV-Format).
- **KDDTest-21.ARFF**: Ein Teil des Testdatensatzes, der Datensätze mit dem maximalen Schwierigkeitsgrad ausschließt.
- **KDDTest-21.TXT**: Dasselbe wie oben im CSV-Format.

### Verbesserungen gegenüber dem KDD'99-Datensatz

1. **Reduzierte Redundanz**: Entfernt doppelte Datensätze im Trainingsdatensatz, um eine Verzerrung der Klassifikatoren zu vermeiden.
2. **Ausgewogene Schwierigkeitsgrade**: Gewährleistet eine größere Bandbreite von Klassifikationsraten bei maschinellen Lerntechniken.
3. **Keine doppelten Testdatensätze**: Verhindert Overfitting bei häufig auftretenden Datensätzen.
4. **Angemessene Datensatzgröße**: Ermöglicht vollständige Experimente, ohne dass eine zufällige Stichprobe erforderlich ist.

## Projektziele

Die Hauptziele dieses Projekts sind:

1. **Datenexploration**: Analyse der Struktur und Eigenschaften des NSL-KDD-Datensatzes.
2. **Feature Engineering**: Verarbeitung und Normalisierung der Merkmale für maschinelles Lernen.
3. **Modellentwicklung**: Training von Modellen, um Netzwerkverkehr als normal oder als Angriffstyp zu klassifizieren.
4. **Evaluierung**: Bewertung der Modelle anhand standardisierter Metriken wie Genauigkeit, Präzision, Recall und F1-Score.

## Ergebnisse

### Modellspezifikationen
- **Logistische Regression**
- **XGBoost-Klassifikator** mit optimierten Hyperparametern:
  - `colsample_bytree=0.5`, `learning_rate=0.1`, `max_depth=6`, `n_estimators=128`, `subsample=0.8`

#### Feature Engineering
- Auswahl der 15 wichtigsten Merkmale (z. B. `duration`, `protocol_type`, `flag`).
- Normalisierung mit `StandardScaler`.

### Leistungsmetriken
- **Genauigkeit (Accuracy)**: Bewertet die Gesamtleistung des Modells.
- **Präzision (Precision)**: Misst den Anteil der korrekten positiven Vorhersagen.
- **Recall (Empfindlichkeit)**: Bewertet, wie viele tatsächliche positive Fälle korrekt erkannt wurden.
- **F1-Score**: Harmonisches Mittel von Präzision und Recall.
- **AUC (Area Under Curve)**: Fläche unter der ROC-Kurve.

### Ergebnisse des XGBoost-Modells
- **F1-Score**: Basierend auf der Modellbewertung berechnet.
- **Recall**: Während der Tests hervorgehoben.
- **AUC**: Über die ROC-Kurve überprüft.

Die detaillierten Evaluierungsergebnisse und Visualisierungen sind im Verzeichnis `results` verfügbar.

## Beiträge

Beiträge sind willkommen! Forken Sie dieses Repository und senden Sie Pull-Requests.

## Lizenz

Dieses Projekt steht unter der MIT-Lizenz. Siehe die Datei [LICENSE](LICENSE) für Details.
