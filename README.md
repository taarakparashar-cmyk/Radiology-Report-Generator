Radiology Report Generator

This project uses a frontal chest X-ray to draft the Findings and Impression sections of a radiology report. The experiments compare how well models classify a study as normal or abnormal and how well generated reports capture findings in the reference text.

Dataset and notebook

Download and extract Chest X-rays (Indiana University) on Kaggle.

Keep the image folders alongside indiana_reports.csv and indiana_projections.csv. The projections table links each image filename and view to a study, and the reports table supplies its reference text.

Open the project notebook in Jupyter or VS Code, configure the dataset location, and run the cells in order.

After preprocessing, 3,580 studies had a frontal image and a usable report. The study-level split used 2,506 for training, 537 for validation and 537 for testing.

Experiments and results

Task

Model

Held-out result

Normal or abnormal classification

Five-block CNN

73.6% accuracy, compared with 63.1% for the majority-class baseline

Report generation

DenseNet121 encoder with an LSTM decoder

Best word overlap among the neural generators, with BLEU-4 of 0.104

Report generation

Transformer decoder using image features and nine predicted findings

Best finding-label agreement among the neural generators, with macro F1 of 0.450

The Transformer generated abnormal-sounding text for only 66 of 339 abnormal test studies. That limitation matters when interpreting its output. The project is a research demonstration.
