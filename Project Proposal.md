1\. Title  
Guest Insights: Customer Feedback Sentiment Analyzer for a Restaurant

2\. Name  
Xu Zhang (xz766)

3\. Description  
Guest Insights is an web application that ingests customer feedback in CSV format and automatically classifies each review as Positive / Neutral / Negative using a custom sentiment model built from scratch. 

Users will first upload a CSV with columns: date (MM-DD-YYYY), rating (1–5), and text. Then the AI model will label each review and return the results. The Dashboard then summarizes what matters: (a) overall sentiment distribution with week-over-week change, (b) a trend line of sentiment over time, and (c) Top Mentions, a ranked list of \~10 keyphrases mined from the currently filtered reviews. Top Mentions includes a polarity toggle—Positive, Negative, or Both—so users can quickly see what guests praise versus what they complain about.

These reviews will be put in a Review Explorer table providing the detailed view behind the charts, with columns: Date, Rating, Text (truncated), and Label. There will be a filter for the table which filters by date range, rating, sentiment label, and keyword search, which will reshape both the dashboard and the table. Clicking a keyphrase in Top Mentions jumps to the Review Explorer table to the matching reviews; clicking a table row opens the full text for context.

There will be an Export action that lets users download the labeled reviews as CSV for later purposes. The result is a focused, production-style tool that turns raw feedback into clear, actionable insight for restaurant operations.

4\. General Approach  
Build the model:

* Gather labeled restaurant reviews.  
* Train a small neural-network sentiment classifier.

App architecture:

* web UI (upload, dashboard, table) \+ backend API with a local database.

Data flow

* Upload CSV → run the model to predict and assign labels → store results on the table.

Insights

* Compute overall sentiment and a time trend.  
* Extract Top Mentions with a Positive / Negative toggle.

Drill-down

* Provide basic filters (date range, rating, sentiment, keyword) and a table of reviews.  
* Export the current filtered view to CSV.

5\. Coherent Plan  
Evaluation of the Model: Run the model on the test set of data and report macro-F1 and confusion matrix. Macro-F1 needs to be greater than or equal to 0.75.  
Evaluation of Top Mentions quality: Randomly sample some reviews and manually gather \~10 keyphrases. Compare these \~10 phrases to Top Mentions.

6\. Timeline  
Week 1 — Plan & data

* Gather a small set of reviews.  
* Set up the codebase and a simple app skeleton.

Week 2 — Build model

* Build a small sentiment model.  
* Get a first set of results.

Week 3 — Improve the model

* Tweak the model until the results are stable.  
* Save the final model version to use in the app.

Week 4 — Back end

* Add routes to upload a CSV, run the model to assign labels, and store results.

Week 5 — Front end basics

* Build the Upload page, Dashboard summary, and the Review table.

Week 6 — Insights & drill-down

* Add Top Mentions (Positive / Negative / Both), filters, and CSV export.

Week 7 — Evaluate & fix

* Report macro-F1 and a confusion matrix on the test set.  
* Do a quick manual check of predictions and fix obvious issues.

Week 8 — Polish & deliver

* Clean up the UI, prepare the demo, and finish the write-up.

