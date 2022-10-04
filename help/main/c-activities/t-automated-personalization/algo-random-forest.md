---
keywords: random forest;decision tree;ap;Automated Personalization
description: Learn how Adobe [!DNL Target] uses the Random Forest algorithm in both Automated Personalization (AP) and Auto-Target activities.
title: How Does [!DNL Target] Use the Random Forest Algorithm?
feature: Automated Personalization
exl-id: 07a89525-4071-4434-ac96-c59a4f4422ad
---
# ![PREMIUM](/help/main/assets/premium.png) Random Forest algorithm

Target's main personalization algorithm used in both Automated Personalization and Auto-Target is Random Forest. Ensemble methods like Random Forest use multiple learning algorithms to obtain better predictive performance than could be obtained from any of the constituent learning algorithms. The Random Forest algorithm in Automated Personalization is a classification or regression method that operates by constructing a multitude of decision trees when it is being trained.

 When you think of statistics, a single regression model used to predict an outcome might come to mind. The latest data science research suggests that "ensemble methods," where multiple models are created from the same data set and then intelligently combined, produce better results than would predicting based on a single model alone.

The Random Forest algorithm is the key underlying personalization algorithm used in Automated Personalization and Auto-Target activities. Random Forest combines hundreds of decisions trees together in order to arrive at a better prediction than a single tree could make by itself.

## What is a decision tree? {#section_7F5865D8064447F4856FED426243FDAC}

The goal of a decision tree is to break down all available visit data a system can learn from and then group that data, where visits within each group are as similar as possible to each other with regard to the goal metric. Across groups, however, the visits are as different as possible, with respect to the goal metric (e.g. conversion rate). The decision tree looks at the different variables it has in the training set to determine how to split the data in a MECE (Mutually-Exclusive-Collectively-Exhaustive) way into these groups (or "leaves") to maximize this goal.

In a simple example, let's assume we only have two input variables:

* Gender (with two potential values, Male or Female) 
* Zip Code (with five potential values in our small data set: 11111, 22222, 33333, 44444, or 55555)

If our goal metric is conversion, then the tree would first determine which of our two variables explains the largest amount of variation in the visit data's conversion rate.

Let's say zip code is most predictive. This variable would then form the first "branch" of the tree. The decision tree would then determine how to split the visit data, such as the conversion rate of the records within each split was as similar as possible, and the conversion rate between the splits was as different as possible. In our example, we'll assume 11111, 22222, 33333 are one split and 44444 and 55555 are a second split.

This action would result in the first layer of our decision tree:

![decsion_tree_1 image](assets/decsion_tree_1.png)

The decision tree would ask the question, "What is the most predictive variable?" In our example, we only have two variables, so the answer here is clearly gender. The tree now will look to complete a similar exercise to split the data *within each branch*. First, let's consider the 11111, 22222, and 33333 branch. In these zip codes, if there is a difference in conversion between men and women, then there would be two leaves (men and women), and this branch would be complete. In the other branch, 44444 and 55555, let's assume there is no statistical difference between how women and men convert. In this case, the first branch becomes the final split.

Our example would result in the below tree:

![decsion_tree_2 image](assets/decsion_tree_2.png)

## How are decision trees used by Random Forest? {#section_536C105EF9F540C096D60450CAC6F627}

Decision trees can be a powerful statistical tool. However, they have some disadvantages. Most critically, they can "over-fit" the data so that an individual tree poorly predicts future data that wasn't used to build the initial tree. This challenge is known as the [bias-variance tradeoff](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff) in statistical learning. Random forests help overcome this overfitting challenge. At the highest level, a random forest is a collection of decision trees that are built slightly differently on the same data set that "vote" together to yield a better model than an individual tree. The trees are built by randomly selecting a sub-set of visits records with replacement (known as bagging), as well as randomly selecting a sub-set of the attributes, so that the forest consists of slightly different decision trees. This method introduces small variations into the trees that are created in the Random Forest. Adding in this controlled amount of variance helps improve the predictive accuracy of the algorithm.  

## How do Target's personalization algorithms use Random Forest? {#section_32FB53CAD8DF40FB9C0F1217FBDBB691}

**How Models are Built**

The following diagram summarizes how models are built for Auto-Target or Automated Personalization activities:

![random_forest_flow image](assets/random_forest_flow.png)

1. Target collects data on visitors while randomly serving experiences / offers 
1. After Target hits a critical mass of data, it performs feature engineering 
1. Target builds Random Forest models for each experience / offer 
1. Target checks if the model meets a threshold quality score 
1. Target pushes the model to production to personalize future traffic

Target uses data it collects automatically, as well as custom data provided by you, to build its personalization algorithms. These models predict the best experience or offer to show to visitors. Generally, one model is built per experience (if an Auto-Target activity) or per offer (if an Automated Personalization activity). Target then chooses to display the experience or offer that yields the highest predicted success metric (e.g. conversion rate). These models must be trained on randomly served visits before they can be used for prediction. As a result, when an activity first starts, even those visitors who are in the personalized group are randomly shown different experiences or offers until the personalization algorithms are ready.

Each model must be validated to ensure it is good at predicting the behavior of visitors before it is used in your activity. Models are validated based on their AUC (area under the curve). Because of the need for validation, the exact time when a model will start serving personalized experiences is dependent on the details of the data. In practice, and for traffic planning purposes, it usually takes more than the minimum number of conversions before each model is valid.

When a model becomes valid for an experience or offer, the clock icon to the left of experience/offer name changes to a green checkbox. When there are valid models for at least two experiences/offers, some visits start to become personalized.

**Feature Transformation **

Before the data goes through the personalization algorithm, it undergoes a feature transformation, which can be thought of as prepping the data collected in the training records for use by the personalization models.

The feature transformations depend on the type of attribute. Mainly, there are two types of attributes (or "features" as they are sometimes described by data scientists):

* **Categorical:** Categorical features cannot be counted but can be sorted into different groups. They could be features like country, gender, or zip code. 
* **Numeric:** Numeric features can be measured or counted, such as age, income, and so on.

For categorical features, a set of all possible features is maintained and the likelihood transformation is used to reduce the data size. For numeric features, re-scaling ensures that the features are comparable across the board.

**Balancing learning vs. personalizing with the Multi-Armed Bandit**

After Target has personalization models built to personalize your traffic, there is a clear tradeoff you face for future visitors to your activity: should you personalize all the traffic based on the current model or should you continue to learn from new visitors by randomly serving them random offers? You want to make sure the personalization algorithm is always learning about new trends in your visitors, while personalizing most of the traffic.

The multi-arm bandit is how Target helps you meet this goal. The multi-arm bandit ensures the model is always "spending" a small fraction traffic to continue to learn throughout the life of the activity learning and to prevent over-exploitation of previously learned trends.

In the data-science world, the multi-armed bandit (MAB) problem is a classic example of the exploration vs. exploitation dilemma in which a collection of one-armed bandits, each with unknown reward probability, is given. The key idea is to develop a strategy, which results in the arm with the highest success probability to be played so the total reward obtained is maximized. Multi-armed bandit is used in the system when for online scoring after the online models are built. This helps with online learning during exploration. The current multi-armed algorithm is epsilon (ε) greedy algorithm. In this algorithm, with probability 1- ε, the best arm is chosen. And, with probability ε, any other arm is randomly chosen.
