# BQ SQL Assistant: Hey BigQuery!
Have you ever thought of being able to interact with a database using voice?

In this demo, we will build a small prototype to launch SQL statements using voice commands.

**Workflow:**
1. Get a command from the local microphone. To make things even more interesting we will be building a multi-language SQL assistant, we will be using Spanish (es-ES) in the demo.
2. Transcribe the audio file using Google Cloud Speech to Tecx APIs
3. Translate the transcript text to English (es-US)
4. Use BigQuery DataQnA to run the command against the database - it will autogen SQL
5.Get the results back on a pandas DataFrame and plot the results using matplotlib

**Prototype architecture:**
![Diagram](diagram.png)

**Setup:**

1.Enable DataQnA for a table of your choice. Refer to BigQuery documentation for enabling DataQnA. At the time of writing this document Data QnA is  in private Alpha. Access is only available to allowlisted users. Apply for access [here](http://g.co/cloud/data-qna)
> **_NOTE:_**  it is a good idea to add field synonyms with the different ways of referencing/naming the field in question
2. Install ffmpeg on your host system. Instructions on [ffmpeg](https://ffmpeg.org/). This is required for audio file manipulation
3. Install the following required python packages: 
```
pip install google-cloud-speech #Google Cloud Speech-to-text API
pip install google-cloud-data-qna #Google Cloud BigQuery DataQnA API
pip install google-cloud-bigquery #Google Cloud BigQuery
pip install google-cloud-translate #Google Cloud Translate API
pip install ipywebrtc #This is required for recording audio from IPython                             
jupyter labextension install jupyter-webrtc #Enable Jupyter notebook widget
```
4. Open and run the notebook, you will need to modify and adapt to your environment the following values:
```
os.environ["GOOGLE_APPLICATION_CREDENTIALS"] = <KEY_FILE>
project = <PROJECT_NAME>
location = <DATASET_LOCATION>
dataset= <DATASET_NAME>
table= <KEY_FILE>
lang_code= <AUDIO_LANGUAGE_CODE>
```
**Additional information:**

* [Ask questions to BigQuery and get instant answers through Data QnA](https://cloud.google.com/blog/products/data-analytics/introducing-data-qna)
* [Trying out Data QnA on BigQuery and Google Sheets](https://medium.com/daas-labs/trying-out-data-qna-on-bigquery-and-google-sheets-e47939fddf25)
* [Pushing the Last Frontier of Data Analysis Democratization With BigQuery Data QnA](https://medium.com/swlh/pushing-the-last-frontier-of-data-analysis-democratization-with-bigquery-data-qna-e6bc9d4ca58b)
* [Data QnA Python library](https://pypi.org/project/google-cloud-data-qna/)
