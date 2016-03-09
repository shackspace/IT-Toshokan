# Sebastian Raschka - Python Machine Learning

In den ersten beiden Kapiteln wird ein Schnelldurchlauf durch maschinelles Lernen gemacht.
Mit einigem an Mathe. Wenn man es schonmal gehört hat, dann fast zu ausführlich.

Kapitel 3 gibt dann einen Überblick über scikit-learn.
Positiv an den beispielen ist, dass die standardprobleme aufgezeigt werden. Z.B. underfitting (high bias) und overfitting (high variance).
Schon in Kapitel 3 werden dann SVM eingeführt und beschrieben, warum sie sinnvoll sind.
Am Ende des Kapitels dann noch andere standardclassifier: decision tree, KNN.

Kapitel 4 erklärt die Vorverarbeitung der Daten und das Unterteilen in Training- und Test-set.
Ausserdem scaling und finden von Features.

In Kapitel 5 wird dann dimension reduction erklärt. Vor allem interessant sind die PrincipalComponentAnalysis- und LinearDiscriminantAnalysis-Beispiele in scikit-learn.
Ausserdem einiges zu komplexeren Kernels.

Kapitel 6 erklärt pipelining, cross-validation, Bewertung der Ergebnisse und Debugging-Strategien.

In Kapitel 7 werden mehrere Modelle kombiniert.

Kapitel 8 wird für ein praktisches Beispiel verwendet. Anhand der sentiment analyse auf IMDB-Daten wird gezeigt, wie man das in Python machen kann.
Richtig viel CL-Statistik-Grundlagen in diesem Kapitel: bag-of-word, tf-idf, tokenizing.
Ausserdem auch online-learning (also nachtrainieren von modellen), weil die daten zu viele sind.

Kapitel 9 zeigt wie eine ML-Anwendung in eine Webseite eingebaut wird. Das verwendete Webframework ist Flask mit SQLite und das Beispiel ist relativ simpel gehalten.

In Kapitel 10 wird regressionsanalyse erklärt. Spannend ist hier, wie die bewertung von Features erklärt wird.

Kapitel 11 erklärt Clustering von ungelabelten Daten. Mit K-Means. Später aber auch kompexere Lösungen um bessere Cluster zu finden und diesen auch hierarchie zu geben.

In Kapitel 12 werden Neuronalen Netzen am Beispiel von Bilderkennung ausgeführt. Das Kapitel ist zwar oberflächliche aber ziemlich gute Einführung in neuronale Netze.
Das Problem ist Bilder von Zahlen unterscheiden. Ein absoluter Klassiker und damit auch vergleichbar mit anderen Beispielen in Octave oder anderen Python-Tutorials.

Kapitel 13 löst dann neuronale Netze mit Theano. Theano ist eine alternative zu TensorFlow.
