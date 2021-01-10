![Diagram](diagram.png)
This repo contains a Jupyter notebook illustrating how to use the:
* BigQuery DataQnA API
* Translate API
* StT API

**Workflow:**
1. Get a Spanish command from the local microphone
2. Transcribe the audio file using Google Cloud StT APIs
3. Translate the transcript text to English
4. Use BQ DataQnA to run the command against the database - it will autogen SQL

**Additional information:**

* [Ask questions to BigQuery and get instant answers through Data QnA](https://cloud.google.com/blog/products/data-analytics/introducing-data-qna)
* [Trying out Data QnA on BigQuery and Google Sheets](https://medium.com/daas-labs/trying-out-data-qna-on-bigquery-and-google-sheets-e47939fddf25)
* [Pushing the Last Frontier of Data Analysis Democratization With BigQuery Data QnA](https://medium.com/swlh/pushing-the-last-frontier-of-data-analysis-democratization-with-bigquery-data-qna-e6bc9d4ca58b)
* [Data QnA Python library](https://pypi.org/project/google-cloud-data-qna/)
