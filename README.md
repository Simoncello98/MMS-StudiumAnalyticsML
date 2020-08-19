# StudiumAnalytics - ML LinearRegression
Progetto MMS
* Simone Scionti
* Anno accademico 2019/2020

## Descrizione
Progetto per Metodi Matematici e statistici per via del quale è stata sviluppata la componente di machine learning che fa uso della regressione lineare per il progetto StudiumAnalytics. 

## Parti del progetto riguardanti Metodi Matematici e Statistici

* La classe MLPipeline, delegata alla gestione del machine learning e quindi della stima dei dati grazie alla regressione lineare è presente nel file al path:
**MMS-StudiumAnalyticsML/StudiumAnalytics-stable//spark/apps/studium-analytics-streaming-1.0.0/src/main/java/studium/analytics/streaming/ML/MLPipeline.java**

* I programmi che si occupano di creare i dati di training, scritti in c++, si trovano al path:
**MMS-StudiumAnalyticsML/TrainingDataCreators/**


* I file csv di training costruiti dai programmi sopracitati si trovano al path:
**MMS-StudiumAnalyticsML/StudiumAnalytics-stable//spark/MLTrainingData/**


# Guida all'uso dell'intero progetto

- Scaricare o clonare l'intera repository
- Scaricare la cartella drive al seguente link: https://drive.google.com/drive/folders/1uO-NDu6Uzg5gUuxnkWKL6ZIBZzgG3lxV?usp=sharing
  - Una volta scaricata la cartella
  - Spostare i file "elasticsearchBK.tar" e "kibanaBK.tar" nella cartella StudiumAnalytics-stable al seguente path:"StudiumAnalytics-stable/bin/"
  - Spostare il file "kafka_2.12-2.3.1.tgz" nella cartella StudiumAnalytics-stable al seguente path:"StudiumAnalytics-stable/kafka/setup/"
  - Spostare i file "spark-3.0.0-preview2-bin-hadoop2.7.tgzr" nella cartella StudiumAnalytics-stable al seguente path:"StudiumAnalytics-stable/spark/setup/"
  - Spostare i file "studium-analytics-streaming-1.0.0-jar-with-dependencies.jar" nella cartella StudiumAnalytics-stable al seguente path:"StudiumAnalytics-stable/spark/apps/studium-analytics-streaming-1.0.0/target/"
- Aprire la cartella "StudiumAnalytics-stable/bin" e lanciare i seguenti comandi in terminali differenti
  - ./dotnet-start.sh
  - ./kafkaStartZk.sh
  - ./kafkaStartServer.sh
  - ./CreateAllTopics.sh
  - ./elasticSearch.sh che una volta runnato dovrà essere stoppato con "ctr-c" nello stesso terminale eseguire ./kibana.sh, anche esso dovrà essere stoppato una volta runnato, infine eseguire il seguente comando ./restoreVolumes.sh che permette di ripristinare i volumi di elasticsearch e kibana contenenti dati e dashboard
  - ./elasticSearch.sh
  - ./kibana.sh
  - ./sparkSubmitApps.sh
  
  ### N.B. non ci sarà alcun flusso di dati in ingresso poiché la versione dell'app Studium in cui sono integrate le chiamate al servizio API non è stata rilasciata.
  
  
