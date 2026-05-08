# Data Poisoning & Model Inversion:

## How it's noticed:

+ Sudden Model Degradation: An unexplained, sharp drop in predictive accuracy, particularly on specific edge cases or sub-datasets.
+ Trigger-Based Misclassification (Backdoors): The model functions correctly normally but fails spectacularly when presented with a specific "trigger" (e.g., a specific sticker on a stop sign causing an autonomous vehicle to misclassify it).
+ Anomalies in Training Data: Auditing reveals unexpected outliers, high concentrations of mislabeled data, or data that does not match the statistical distribution of legitimate data.
+ Drift Detection: Monitoring tools identify that model predictions are shifting, indicating that the underlying model parameters have been altered.
+ High-Volume Erroneous Outputs: A sudden spike in incorrect, inconsistent, or biased outputs.
+ Unusual Query Patterns: A high volume of requests from a single source, often featuring subtle variations in the input (probing), designed to map the model's decision boundaries.
+ High-Confidence Verbatim Responses: The model outputs highly specific, sensitive information (e.g., private user data, confidential documents) verbatim rather than general, synthesized responses.
+ Specific API Anomalies: Monitoring reveals requests that explicitly ask for examples, verbatim text, or templates, often attempting to extract memorized data.
+ High-Volume "Membership Inference" Probes: Queries designed to see if the model knows a specific data point, which is a common precursor to inverting the model to recover that data.
+ Unusual Output Lengths: Responses that are exceptionally long or oddly formatted, which can indicate the model is being forced to dump trained data, often returning over 1,000 tokens when normal usage returns a small paragraph.

## Mitigation Process:

+ Isolate and Remove Affected Data: Identify and quarantine the tainted data subset. Use data provenance records to trace the origins, transformations, and access logs to determine when the poisoned data was introduced.
+ Rollback and Retrain: Revert to a previous, uncompromised version of the model and retrain it using only verified, clean datasets. Avoid resuming training from a checkpoint that might already contain the poisoning effects.
+ Rollback and Retrain: Revert to a previous, uncompromised version of the model and retrain it using only verified, clean datasets. Avoid resuming training from a checkpoint that might already contain the poisoning effects.
+ Rollback and Retrain: Revert to a previous, uncompromised version of the model and retrain it using only verified, clean datasets. Avoid resuming training from a checkpoint that might already contain the poisoning effects.
+ Update Security Policies: Tighten access controls on training pipelines and data repositories to prevent future unauthorized modifications.
+ Limit Output Information: Reduce the precision of the confidence scores or probabilities returned by the model, or remove them entirely, as these are often used by attackers to infer private data.
+ Apply Differential Privacy: Integrate differential privacy techniques during training to add noise to the model's learning process, ensuring that the influence of any single training point is limited.
+ Regularization Techniques: Apply techniques like Dropout or weight decay to prevent the model from overfitting and memorizing specific, sensitive inputs.
+ Monitor Query Patterns: Actively monitor for unusual API usage patterns, such as an high volume of high-confidence, similar queries from a single user
+ Introduce Defensive Poisoning: Novel research suggests that deliberately introducing specific noise to the output can confuse the inversion model without hurting the original model’s utility.
+ Pause Production: Temporarily disable the exposed API or RAG (Retrieval-Augmented Generation) corpora to prevent further data exposure while the investigation is ongoing.
+ Audit Data Sources: Vette the trust level of data sources to ensure that future data ingestion is not compromised.
