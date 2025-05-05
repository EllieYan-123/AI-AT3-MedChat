MedChat -- AI-based intelligent medication recommendation and disease diagnosis system

1.	Project background and demand analysis

Patient side: In non-emergency medical scenarios, users lack medical knowledge and are difficult to choose safe and effective drugs based on symptoms, especially in terms of drug contraindicances (such as pregnant women, drug conflicts) and side effects perception.
Medical end: Pharmacists face issues such as high prescription volume, fatigue, and similarity of drug names.

Solution
Develop MedChat -- an intelligent system based on natural language processing (NLP) and machine learning that provides: medicine recommendations based on symptoms or disease keywords entered by users through conversational interaction.
	Recommend effective over-the-counter (OTC) or prescription drugs (subject to physician confirmation) based on drug databases and drug classifications.
	In addition, key information such as prescription drugs, safety during pregnancy and side effects will be marked.

Target Users
Healthcare companies embed it into embedded online platforms.
-- Patient side: Provide daily medication consultation services for ordinary users, reduce medical costs in non-emergency scenarios, and improve health literacy.
-- Enterprise side: reduce pharmacist decision-making time and improve drug safety.



2.	Dataset
Kaggle:
https://www.kaggle.com/datasets/jithinanievarghese/drugs-side-effects-and-medical-condition/data

example code:
1.	Focus on disease prediction
https://www.kaggle.com/code/tin555/cp3403-5634-project-v2024a#Task-3:-Preprocessing

2.	Focus on medicine recommendation
https://www.kaggle.com/code/hyeonseo6101/medicine-recommendation

3.	Applications of MedChat
Two main parts:
1. Symptom resolution module:
Methods: NLP word segmentation + keyword matching or semantic similarity.
Example: The user enters "I have cough + fever" → extract the keywords "cough" and "fever".

2. Drug Recommendation engine: (LAB7-exercise1-code example)
Disease matching: Filter 'drugs' by the medical_condition field based on keywords that extracted from the step 1.
Then the display relative risks and attentions:  side effects, safety during pregnancy, etc.

Example Case:
User input symptoms (e.g., "I recently had a runny nose, cough, fever")
System returns, disease prediction: colds (60% possibility). (Scores can be ranked based on coverage, frequency, etc.)
Considering your medical condition of cold, you might need to take drugs like Paracetamol.
This medicine is over the counter. This might accompany side effects such as (dizziness.......). In addition, this drug should not be used by pregnant women, and during the use of NON-alcohol. So, you should be aware of this when taking it.
![image](https://github.com/user-attachments/assets/3e5b69cc-823f-4da1-81a1-9372f2cf5ebd)

