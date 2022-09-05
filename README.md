# Machine Learning Project Checklist
A successful well-organized Machine Learning Project shall start with a thoughtful planning. This is the checklist provided by Geron Aurelien on Hands-on machine learning book.

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
## must be continued ^^^^^

- [ ] **Download the Data/ Collect the Data**<br/>
  - Determine how much data you need
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
  - Discover your data(training data) more deeply <br/>
  - Sample an exploration set if your training set is very large<br/>
  - Make a copy not to harm your training set<br/>
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
  - First, Revert to a clean training set (by copying)<br/>
  - Separate the predictors and the labels
- [ ] **Data Cleaning**<br/>
  - Fix missing features
    - Get rid of the corresponding districts<br/>
    - Get rid of the whole attribute<br/>
    - Set the values to some value (zero, the mean, the median, etc.)<br/>
- [ ] **Handling Text and Categorical Attributes**<br/>
  - Select an encoder
- [ ] **Custom Transformers**<br/>
  - ^^^^^^^^^^^
- [ ] **Feature Scaling**<br/>
- [ ] **Transformation Pipelines**<br/>

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
- [ ] **Grid Search**<br/>
- [ ] **Randomized Search**<br/>
- [ ] **Ensemble Methods**<br/>
- [ ] **Analyze the Best Models and Their Errors**<br/>
- [ ] **Evaluate Your System on the Test Set**<br/>

## **7. Launch, Monitor, and Maintain Your System**
## **8. Try It Out**
