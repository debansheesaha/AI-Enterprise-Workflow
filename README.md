# AI Enterprise Workflow - Capstone Project Submission

My capstone project submission for the IBM AI Enterprise Workflow course on Coursera.

## Usage

Start application.
```bash
python run_app.py
```
Test application.
```bash
python run_tests.py
```
Predict future revenue (default is total revenue for next 30 days; add `country` parameter to get revenue for specific country).
```bash
curl --request POST 'http://127.0.0.1/predict?date=2018-11-20'
```
Build image.
```bash
docker build -t app .
```
Run image.
```bash
docker run \
    -it \
    --rm \
    -p 3000:80 \
    --name app \
    app
```

## Endpoints

- `POST /predict?date={date}&duration={duration}&country={country}`
- `POST /logs?type={type}`

## Marking Criteria

- Are there unit tests for the API?\
Yes, see `tests/app_test.py`.
- Are there unit tests for the model?\
Yes, see `tests/model_test.py`.
- Are there unit tests for the logging?\
Yes, see `tests/log_test.py`.
- Can all of the unit tests be run with a single script and do all of the unit tests pass?\
Yes, run `python run_tests.py`.
- Is there a mechanism to monitor performance?\
Yes, see `src/monitor.py` which contains a function to compute the Wasserstein distance metric.
- Was there an attempt to isolate the read/write unit tests from production models and logs?\
Yes, see `src/log.py`.
- Does the API work as expected? For example, can you get predictions for a specific country as well as for all countries combined?\
Yes, use `curl --request POST 'http://127.0.0.1/predict?date=2018-11-20'` or `curl --request POST 'http://127.0.0.1/predict?date=2018-11-20&country=Australia'`
- Does the data ingestion exists as a function or script to facilitate automation?\
Yes, see `src/ingest.py`.
- Were multiple models compared?\
Yes, an ARIMA and SARIMA model were compared. Model comparisons are in `nb/results.ipynb`.
- Did the EDA investigation use visualizations?\
Yes, see `nb/analysis.ipynb` which includes time-series, seasonal-trend decomposition, auto-correlation and partial auto-correlation plots.
- Is everything containerized within a working Docker image?\
Yes, see `Dockerfile`.
- Did they use a visualization to compare their model to the baseline model?\
Yes, see `nb/results.ipynb` where the ARIMA and SARIMA model results are compared to the actual revenue.

## Certificate
[IBM AI Enterprise Workflow Specialization](https://www.coursera.org/account/accomplishments/specialization/certificate/FEMQA3MYLH4B)

[[1] AI Workflow: Business Priorities and Data Ingestion](https://www.coursera.org/account/accomplishments/certificate/2X2RFPD9DQVU)
[[2] AI Workflow: Data Analysis and Hypothesis Testing](https://www.coursera.org/account/accomplishments/certificate/MLG59HKYWDZU)
[[3] AI Workflow: Feature Engineering and Bias Detection](https://www.coursera.org/account/accomplishments/certificate/TTB9B9CQ4VP8)
[[4] AI Workflow: Machine Learning, Visual Recognition and NLP](https://www.coursera.org/account/accomplishments/certificate/N5XX4T5TQGUM)
[[5] AI Workflow: Enterprise Model Deployment](https://www.coursera.org/account/accomplishments/certificate/3R37ZMTRHAEH)
[[6] AI Workflow: AI in Production](https://www.coursera.org/account/accomplishments/certificate/HPHJ9H2RAW43)

## References
[[1] IBM AI Enterprise Workflow Specialization](https://www.coursera.org/specializations/ibm-ai-workflow)
