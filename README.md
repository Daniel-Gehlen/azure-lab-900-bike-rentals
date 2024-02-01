## **Report: Automated Machine Learning in Azure Machine Learning**

**Introduction:**

Azure Machine Learning (AML) is a powerful platform that streamlines the development, training, and deployment of machine learning models on Microsoft's cloud. In this report, we explore the Automated Machine Learning (AutoML) feature in Azure Machine Learning through a practical use case of predicting bike rental based on historical data.

**Methods:**

1. **Creation of Azure Machine Learning Workspace:**
   - We provisioned a workspace in the Azure Portal to leverage Azure Machine Learning resources.
   - Configured an AutoML job to train a machine learning model.

2. **Model Training:**
   - Used the bike rental dataset.
   - Defined AutoML job settings, including task type, dataset, primary metric, and allowed models.
   - Submitted the job and awaited completion.

3. **Review of the Best Model:**
   - Analyzed AutoML job results, emphasizing the best-trained model.
   - Evaluated metrics such as normalized root mean squared error.

4. **Model Deployment:**
   - Successfully deployed the best model as a web service using Azure Container Instance.
   
**Results:**

- The best model trained was based on the RandomForest and LightGBM algorithms.
- The chosen metric was normalized root mean squared error, with a threshold of 0.085 to terminate the job.
- The model was deployed successfully as a web service, exhibiting notable accuracy in predictions.

**Test Results:**

After testing the deployed service with a provided JSON input:
```
{
  "Inputs": { 
    "data": [
      {
        "day": 1,
        "mnth": 1,   
        "year": 2022,
        "season": 2,
        "holiday": 0,
        "weekday": 1,
        "workingday": 1,
        "weathersit": 2, 
        "temp": 0.3, 
        "atemp": 0.3,
        "hum": 0.3,
        "windspeed": 0.3 
      }
    ]    
  },   
  "GlobalParameters": 1.0
}
```
**The returned result was:**
```
{
  "Results": [
    361.95238671338427
  ]
}
```
This numerical value represents the model's prediction for the number of bike rentals based on the provided input features. Specifically, the model predicts approximately 362 bike rentals for a given day, considering the specified meteorological and temporal conditions.

In short, the number is the model's prediction answer to the specific use case question, which in this case is: "How many bike rentals are expected based on the given weather and weather conditions?"

**Conclusion:**

Azure Machine Learning, especially the Automated Machine Learning feature, significantly simplifies the process of developing and deploying machine learning models. By allowing the automatic exploration of various algorithms and hyperparameters, AutoML accelerates the development of high-quality models, even for users without deep expertise in machine learning.

The specific use case of predicting bike rental numbers demonstrates how this automated approach can be effective in handling complex datasets, providing accurate results.

**Additional Use Case: Sales Prediction in an E-commerce Setting**

*Results of the Additional Use Case:*

- The trained model demonstrated high accuracy in predicting daily sales.
- Deployment of the model as a web service facilitated seamless integration with existing systems.
- The AutoML approach proved efficient even in complex sales forecasting scenarios.

**In Summary:**

Automated Machine Learning in Azure Machine Learning offers an effective approach for rapid development and deployment of machine learning models. Its ability to handle a variety of tasks and datasets makes it a valuable tool for professionals and organizations looking to harness the benefits of machine learning in the cloud.
