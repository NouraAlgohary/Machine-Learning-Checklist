# Machine Learning Project Checklist
A successful well-organized Machine Learning Project shall start with a thoughtful planning. This is the checklist provided by Geron Aurelien on Hands-on machine learning book.

![2022-09-05 (3)](https://user-images.githubusercontent.com/103903785/188495451-d9e32e2f-2260-4e0c-8c8c-373d04435755.png)

## 1. Look at the big Picture
- [ ] **Frame The Problem<br/>**
  - What exactly is the objective? <br/>
  - What the current solution looks like?<br/>
  - Is it (supervised, unsuoervised, or Reinforcement Learning)/ (A classification taska regression task, or something else) / (batch learning or online learning)?<br/>
- [ ] **Select A Performance Measure**<br/>
  - Root Mean Square Error(RMSE), Mean Absolute Error(MAE)...etc<br/>
- [ ] **Check The Assumptions**<br/>
  - List the assumptions <br/>
  - Verify the assumptions

## **2. Get the Data**
- [ ] **Create the Workspace**<br/>
- [Install Pyhton](https://www.python.org/) <br/>
- Create a workspace directory for your ML code datasets using terminal
```
   $ export ML_PATH="$HOME/ml" # You can change the path if you prefer
   $ mkdir -p $ML_PATH 
```
- Install needed modules: Jupytar, NumPy, pandas, Matplotlib, and Scikit-Learn

- [ ] **Download the Data/ Collect the Data**<br/>
  - Determine how much data you need<br/>
  - Find a data source
  - Get your credentials and access authorizations<br/>
  - Get the data
  - Familiarize yourself with the data schema<br/>
- [ ] **Take a Quick Look at the Data Structure**<br/>
  - How many instances do you have?<br/>
  - Data Types<br/>
  - Plot a histogram for each numerical attribute<br/>
  - For categorical attributes, find out what categories exist and how many districts belong to each category<br/>
  
- [ ] **Create a Test Set**<br/>
  - Avoid data snooping bias
  > When you estimate the generalization error using the test
  set, your estimate will be too optimistic, and you will launch a system that will not
  perform as well as expected
  - Pick some instances randomely, 20% of the dataset or less if the data set is huge, and set them aside

## **3. Discover and Visualize the Data to Gain Insights**<br/>
  _**Discover your data(training data) more deeply**_ <br/>
  _**Sample an exploration set if your training set is very large**_<br/>
  _**Make a copy not to harm your training set**_<br/>
- [ ] **Visualizing Geographical Data**<br/>
  - A good idea is to create a scatter plot of all districts to visualize the data<br/>
- [ ] **Looking for Correlations**<br/>
  - Discover correlations between attributes
- [ ] **Experimenting with Attribute Combinations**<br/>
  - Try out various attribute combinations<br/>
  - Iteratively, you can get a reasonable good prototype<br/>
  - Once, you get a prototype up and running, youc can analyze its output to gain more insights and come back to this step<br/>
  - The point is to start off on the right foot and gain insights
  
## **4. Prepare the Data for Machine Learning Algorithms**
  _**First, Revert to a clean training set (by copying)**_ <br/>
  _**Separate the predictors and the labels**_
- [ ] **Data Cleaning**<br/>
  - Fix missing features
    - Get rid of the corresponding districts<br/>
    - Get rid of the whole attribute<br/>
    - Set the values to some value (zero, the mean, the median, etc.)
- [ ] **Handling Text and Categorical Attributes**<br/>
  - Select an encoder, etc.
- [ ] **Custom Transformers**<br/>
  - Create your own transformers for tasks such as cleanup operations or combining specific attributes
- [ ] **Feature Scaling**<br/>
  - One of the important transformations
  - Get all the attributes to have the same scale
  - Common ways: min-max scaling and standradization

Note: _Scaling the target values is not required_
- [ ] **Transformation Pipelines**<br/>
  - Scikit-Learn provides the "Pipeline" class to help with sequences of transformations

Note: _You should write functions for this purpose, not manually:_
  1. _The ability to reproduce these transformations on any dataset easily_<br/>
  2. _Gradually, a library of transformation functions is prepared that can be reused on any project_<br/>
  3. _Using these functions in your life system to transform the new data before feeding it to the algorithm_<br/>
  4. _Easily try various transformations and find out which combination of transformations works best_
  

## **5. Select and Train a Model**
  _Now, you are ready to select and train a ML model_
  _Remember using the sampled training set if the data is huge_
- [ ] **Training and Evaluating on the Training Set**<br/>
- [ ] **Better Evaluation Using Cross Validation**<br/>
### Shortlist Promising Models
1. Train many quick-and-dirty models from different categories (e.g., linear, naive
Bayes, SVM, Random Forest, neural net, etc.) using standard parameters
2. Measure and compare their performance
    - For each model, use N-fold cross-validation and compute the mean and stan‐
dard deviation of the performance measure on the N folds
3. Analyze the most significant variables for each algorithm.
4. Analyze the types of errors the models make
    - What data would a human have used to avoid these errors?
5. Perform a quick round of feature selection and engineering
6. Perform one or two more quick iterations of the five previous steps
7. Shortlist the top three to five most promising models, preferring models that
make different types of errors

## **6. Fine-Tune Your Model**
_**Some ways to fine-tune a model**_
- [ ] **Grid Search**<br/>
  - Fine for exploring relatively few combinations
- [ ] **Randomized Search**<br/>
  - Preferable when the search space is large
  - By setting the number of iterations, you have more control over the computing budget you want to allocate to the hyperparameter search
- [ ] **Ensemble Methods**<br/>
  -  Combining the models that perform best. The group(ensemble) will often perform better than the best individual model
- [ ] **Analyze the Best Models and Their Errors**<br/>
  - Try checking the importance scores 
- [ ] **Evaluate Your System on the Test Set**<br/>
  - Get the predictors and the labels from your test set, run your pipeline, and evaluate the final model on the test set.

**Prelaunch Phase: Present your solution (highlighting what you have learned, what worked and what did not, what assumptions were made, and what your system's limitations are), document everything, and create nice presentations with clear visualizations and easy-to-remember statements.**
## **7. Launch, Monitor, and Maintain Your System**
  - Get your solution ready for production
    - Polish the code
    - Write documentation and tests
  - Deploy your model to your production environment 
    - Save the trained Sckikit-Learn model
    - Load the trained model within your production environment
    - Use it to make predictions<br/>
    
![deploy](https://user-images.githubusercontent.com/103903785/188489588-cc7559f6-7bf5-4cac-a0ee-8002281a28e3.jpg)

  - Mentoring the model's live performance
    - One way: human raters to evaluate the live model
    - Another way: If the data keeps evolving
      - Collect fresh data regularly and label it (e.g., using human raters)
      -  Write a script to train the model and fine-tune the hyperparameters automatically. This script could run automatically, for example every day or every week, depending on your needs
      -  Write another script that will evaluate both the new model and the previous model on the updated test set, and deploy the model to production if the performance has not decreased (if it did, make sure you investigate why)
      -  Evaluate the model's input data quality 

  - Male sure you keep backups of every model you create and have thee process and tools in place to roll back to a previous model quickly

## **Try It Out!**
