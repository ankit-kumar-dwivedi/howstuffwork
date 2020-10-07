# Supervised and Unsupervised learning

## Supervised learning

Supervised learning as the name indicates the presence of a supervisor as a teacher. Basically supervised learning is a learning in which we teach or train the machine using data which is well labeled that means some data is already tagged with the correct answer. After that, the machine is provided with a new set of examples(data) so that supervised learning algorithm analyses the training data(set of training examples) and produces a correct outcome from labeled data. 

For instance, suppose you are given a basket filled with different kinds of fruits. Now the first step is to train the machine with all different fruits one by one like this: 
 

 


    If shape of object is rounded and depression at top having color Red then it will be labeled as –Apple. 
    If shape of object is long curving cylinder having color Green-Yellow then it will be labeled as –Banana. 
     

Now suppose after training the data, you have given a new separate fruit say Banana from basket and asked to identify it. 
 

Since the machine has already learned the things from previous data and this time have to use it wisely. It will first classify the fruit with its shape and color and would confirm the fruit name as BANANA and put it in Banana category. Thus the machine learns the things from training data(basket containing fruits) and then apply the knowledge to test data(new fruit). 

Supervised learning classified into two categories of algorithms: 
 

    Classification: A classification problem is when the output variable is a category, such as “Red” or “blue” or “disease” and “no disease”.
    Regression: A regression problem is when the output variable is a real value, such as “dollars” or “weight”.

Supervised learning deals with or learns with “labeled” data.Which implies that some data is already tagged with the correct answer.

Types:-
```
    Regression
    Logistic Regression
    Classification
    Naïve Bayes Classifiers
    Decision Trees
    Support Vector Machine
```

Advantages:-
```
    Supervised learning allows collecting data and produce  data output from the previous experiences.
    Helps to optimize performance criteria with the help of experience.
    Supervised machine learning helps to solve various types of real-world computation problems.
```

Disadvantages:-

```

    Classifying big data can be challenging.
    Training for supervised learning needs a lot of computation time.So,it requires a lot of time.
```


## Unsupervised learning

Unsupervised learning is the training of machine using information that is neither classified nor labeled and allowing the algorithm to act on that information without guidance. Here the task of machine is to group unsorted information according to similarities, patterns and differences without any prior training of data. 

Unlike supervised learning, no teacher is provided that means no training will be given to the machine. Therefore machine is restricted to find the hidden structure in unlabeled data by our-self. 
For instance, suppose it is given an image having both dogs and cats which have not seen ever. 
 

Thus the machine has no idea about the features of dogs and cat so we can’t categorize it in dogs and cats. But it can categorize them according to their similarities, patterns, and differences i.e., we can easily categorize the above picture into two parts. First first may contain all pics having dogs in it and second part may contain all pics having cats in it. Here you didn’t learn anything before, means no training data or examples. 

 It allows the model to work on its own to discover patterns and information that was previously undetected. It mainly deals with unlabelled data.

Unsupervised learning classified into two categories of algorithms: 
 
```

    Clustering: A clustering problem is where you want to discover the inherent groupings in the data, such as grouping customers by purchasing behavior.
    Association: An association rule learning problem is where you want to discover rules that describe large portions of your data, such as people that buy X also tend to buy Y.
```

Types of Unsupervised Learning:-

Clustering
```

    Exclusive (partitioning)
    Agglomerative
    Overlapping
    Probabilistic
```

Clustering Types:-
```

    Hierarchical clustering
    K-means clustering
    K-NN (k nearest neighbors)
    Principal Component Analysis
    Singular Value Decomposition
    Independent Component Analysis
```
