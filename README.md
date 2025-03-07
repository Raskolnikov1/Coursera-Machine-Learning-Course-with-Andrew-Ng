# Coursera-Machine-Learning-Course-with-Andrew-Ng


Introductory Machine Learning Course from Stanford  - My first MOOC started 6 years ago. Now completed after all this time... One more victory.....

Goes over the basic Machine Learning Techniques that are common in the field and applied them to a wide variety of different Cases.

### Note of thanks: 

Of course, Professor Ng deserves thanks for making this course and sharing his knowledge with all of his students world wide. Thank you. 

I would like to thank the mentor Tom Mosher for his very helpful tutorials which have been of great assistance in finishing these project assignments. I will be placing pictures of his helpful hints in the future, I hope. 

## Supervised Learning Methods 

### Week 2: Linear Regression 

Purpose: Learn about a Machine Learning Technique that will draw a trendline that can relate a set of features to an output. 
### Explanation
In the course, Linear Regression was one of the first techniques introduced in the course.

The technique attempts to recreate a function through iteration that can match the response variable that is continuous. 

If we had a dataset on housing prices for example, one would find that the price of the house varies depending on certain key factors. Some of these factors are things like square footage, number of bathrooms, number of bedrooms, Number of floors etc. 

| Size    | Number of bedrooms      | Number of floors| Price($1000)   
| ------------- | ------------- | --------    | ---------
| 2104      | 1    | 45   | 460
| 1416         | 2   | 40   | 232

Source: Machine Learning on Coursera - Video: Multiple Features from Week 2 

The question was then put forth. 

Is it possible to create a relationship between these stated "features" i.e. Size, num of bedrooms etc and the price?

It is indeed possible and that was the focus of the project. The way this is done is by forging a polynomial equation that can generate the price response. This polynomial equation is referred to in the series as a hypothesis. 

$$h_{0} = \theta_{0} + \theta_{1}*x_{1} + \theta_{2}*x_{2} + \theta_{3}*x_{3} +\theta_{n}*x_{n}$$

This hypothesis attempts to accurately predict the response variable given a feature space.

### Cost function for Linear Regression 

How do we know if the hypothesis is getting closer to the correct response values according to the dataset. Well in this case its just determinng the Sum of the square or errors. It penalizes very heavily results that are far away from the true value. 

$J = {1}{2*m} * \Sigma((h_{\theta}*X - y)^2)$

With poor theta parameters one would get a very bad fit of data as shown below. Graph was made by Professor Ng. 

![image](https://user-images.githubusercontent.com/20827630/184058843-31af0f2c-92db-4bef-9458-78f0b8c216cf.png)

Source: Source: Machine Learning Course by Andrew Ng - Week 1 - Cost Function- Intuition || 

The theta parameters are modified so that the distance between the points is minimized. This results in a graph shown below that was made by Professor Ng. 

![Professor Ng's iteration of Linear Regression](https://user-images.githubusercontent.com/20827630/184058679-73a12e71-223c-4727-ba8d-f3bb3881a740.png)

Source: Machine Learning Course by Andrew Ng - Week 1 - Cost Function- Intuition || 

#### Gradient Descent for Linear Regression

In order to fit the hypothesis to the response variable, it is necessary to change the theta parameters. This is done with a technique called gradient descent. It uses the following formula: 

$\theta_{n} = \theta_{n} - \alpha * \Sigma(h_{\theta} * X - y)$

This can be easily extrapolated to as many theta parameters as necessary. What happens is that the theta parameters in the hypothesis function are updated until the function matches the response variable as closely as possible. 

#### Results of Linear Regression project: 

![image](https://user-images.githubusercontent.com/20827630/184282376-a2b10c8f-26d1-41f1-8474-56685901377d.png)



### Week 3: Logistic Regression 

#### Explanation: 

Logistic Regression was the next important technique taught in the course. 

Instead of trying to predict a continuous variable, this technique tries to predict a categorical variable i.e. Cancer or No Cancer, Lend Money vs Don't Lend Money, Happy vs Sad etc. Its either one or the other. 

The professor discussed how a naive attempt to solve the problem was to use linear regression and just limit the bounds of the response variable to between 0 and 1. However, the response is categorical while linear regression will potentially give results that are between 0 and 1. If you are building a cancer classifier, I imagine you don't want to get a response of .5. That is a meaningless result. 

So what function can be used if not the polynomial expression used in Week 2? 

Looks like the function referred to as the sigmoid function will be of use. 

This function is shown below. 

$g(z) = \frac{1}{1+e^{-z}}$

![Logistic Function](https://user-images.githubusercontent.com/20827630/184052065-e4529d1c-794e-426a-9997-6d3926f4caa8.png)

Source: Machine Learning Course By Andrew NG - Week 3 Reading: Hypothesis Section

This function will map any real value number into a response from 0 to 1. Notice that z has a very small range where it gives a non-integer input. This way, it will be able to classify most of the examples into the categorical bins of 0 and 1.

The hypothesis function therefore becomes a probability that an input will result in a categorical variable response. i.e. P(Y = 1) = .70

However, we still need a way of forcing the function to take a stand. We need to enforce a decision boundary. If it is on one side of the boundary, it will go into one bin. If it is on the other side of the boundary, it will go to the other bin. 

The decision boundary for the logistic function was decided to be .5. If the hypothesis is greater than .5, output the categorical value of 1. Else output categorical variable of 0. The input in octave is just the Theta Matrix transpose multiplied by the X matrix. $\Theta * X$. Note that the input does not have to be linear. It can be whatever shape fits the data. 

### Cost Function for Logistic Regression 

So how do we determine if we are accurately predicting the response variables? Well the following cost function is used. 

$J(\Theta) = \frac{1}{m} \Sigma_{i=1}^{m} * Cost(h_{\theta}(x^{(i)}), y^{(i)})$

$Cost(h_{\theta}(x), y) = -log(h_{\theta} * (x))$ if y = 1$

$Cost(h_{\theta}(x), y) = -log(1 - h_{\theta} * (x))$ if y = 0 $

The reason why this Cost function is used is it was just a creative exercise in order to achieve the desired outcome. What function would allow me to penalize incorrect classifications extremely and when the classifications get closer the cost falls extremely low the closer it gets to the correct value. The functions above seem to do the job correctly so these are used. 

Professor Ng elegantly shows the Cost function as a consequence of the hypothesis function for both scenarios. 

![Professor Ng's graphs for logistic Cost function](https://user-images.githubusercontent.com/20827630/184055145-3c3ccf73-702e-4248-af51-e33b6df125de.png)

Source: Machine Learning Course By Andrew NG - Week 3 Reading: Cost Function

So combining both of these functions will allow for computing the appropriate cost for the hypothesis function. 

#### Gradient Descent for Logistic Regression

#### Multiclass Classification 

TBD

#### Results of Logistic Regression Project 

![image](https://user-images.githubusercontent.com/20827630/184286261-b0e991ef-ffab-4fad-8c00-95581b298505.png)



### Week 4: Multi-Class Classification and Neural Networks 

#### Explanation:

This week went over one of the most recent additions to the machine learning engineeers toolkit called a neural network. It is an algorithm inspired by the inner workings of the brain. It is believed that the brain is using something called "The Master Algorithm" which allows different parts of the brain that are responsible for one function i.e. like hearing and training that brain tissue to be used for seeing things. The brain is comprised of a particular type of cell called a neuron. It has dendrite that accept inputs and sends the result through to the axon which is the output. The algorithm shown in this week attempts to recreate this powerful functionality. 

The nerual network is a universal function approximator that can create non linear decision boundaries and is inspired by the way the brain learns. 

Between the input and output, we can have hidden layers that can allow for the matching of more complicated non-linear decision boundaries. 

Here is a simplified version of the progression of the neural network. 

$[x1x2x3] -> [] -> h_{\theta}*x$

The inputs x1x2x3 are like the dendrites in the neurons, the inputs are then processed within other hidden networks of neurons and then output in the hypothesis or the axon of the last neurons. 

So what is in the empty brackets? It is the activation functions that show the intermediate outputs. These are [a1a2a3]. What are these activation units though? 

They are the summations of all the results from the previous neurons which are then fed into a sigmoid function. 

Neural networks can be represented with the following type of diagram. 

![image](https://user-images.githubusercontent.com/20827630/184502416-cc763568-df40-4f82-81ff-9c911e4df213.png)

Source: Machine Learning with Andrew Ng - Week 4 - Neural Networks - Lecture_slides 

In order to perform the prediction phase it is necessary to perform something called a feedForward operation. 

All this operation is doing is multiplying the inputs with the Theta Matrices, activating the results with sigmoid function and adding bias units whenever necessary. 

The resulting hypothesis function will appropriately classify all the examples with appropriate label. 

The equations used in the feedforward operation are shown below for the example network. 

This is shown below and was taken from the course. 

![image](https://user-images.githubusercontent.com/20827630/184272996-f8a6c9b9-48b6-441e-9b2e-b4fc5063191c.png)
 
Source: Machine Learning with Andrew Ng - Week 4 - Neural Networks - Model Representation l

### Cost function for neural networks in classification 

The Cost function used by neural networks for classification is the same as the one used for Logistic Regression. It is shwon below 

$J(\Theta) = \frac{-1}{m} * \Sigma(y^{i} * log(h_{\theta} * X) + (1 - y^{i}) * (1 - log(h_{\theta} * X)))$

This is applied to each of the output nodes to see which class accurately represents the training example in the X matrix. 

### Gradient for neural networks in classification 

The gradient is the derivative of the Cost function with regard to the theta parameters. It is shown below. 

$\frac{d(J_{\Theta})} {d_{\Theta_{j}}} = -\frac{1}{m} * \Sigma(h_{\theta} * X - y) * X$

This will allow you to choose the optimal theta parameters that will minimize the Cost Functions for each class label. 

### Results of Neural Network MultiClassification Project 

![image](https://user-images.githubusercontent.com/20827630/184469799-1eca7fac-b6a7-4e63-a3fc-e0ae305497c7.png)



### Week 5: Neural Network Learning 

#### Explanation: 

The previous week taught me how to perform a classification task with pre-made Theta matrices and then sending the inputs through these theta matrices and activating the layers in order to find the correct labels for each feature. However, what if the matrices are not the ones that give the highest accuracy from the start? 

This requires the use of a technique called backpropagation which allows for the modifying of the theta parameters. 

#### Cost Function for Neural Network Learning: 

$$ \qquad -\frac{1}{m} \sum_{i=1}^m \sum_{k=1}^k [y_{k}^{i} * log(h_{\theta}(x^{i}){k} + (1-y{k}^{i}) * (1 - log(h_{\theta}(x^{i}){k})] + \frac{\lambda}{2*m} \sum_{l=1}^{L-1} \sum_{i=1}^{S_l} \sum_{j=1}^{S_l + 1} (\Theta_{j,i}^{(l)})^2) $$

It looks like the Cost function is adding up all of the examples for all of the labels. 

#### Gradient for Neural Network Learning 

The gradient is calculated differently this time. Instead of using the gradient used in Week 4, it is now going to be done using a tchnique called BackPropagation. 

##### Explanation of BackPropagation: 

Here is a schematic showing a brief view of BackPropagation in action. The diagram was taken from the Machine Learning Course. 

![image](https://user-images.githubusercontent.com/20827630/184551188-022ba661-3344-4a50-ad57-3509ece34c93.png)

Source: Machine Learning with Andrew Ng - Week 5 - Neural Networks Learning - BackPropagation Intuition

Lets say you calculate the activation results for each layer in a neural network. The activation layer for the last layer is the hypothesis you are comparing to the true value y. Determine how close the hypothesis and the true value is by subtracting the results from each other: 

$\delta_{L} = a(L) -  y$

Now it is required to send this difference back through the layers. The equations used for that are 

$\delta(3) = (\Theta^{3})^{T} * \delta^{4} .* g'(z^{3}) $

$\delta(2) = (\Theta^{2})^{T} * \delta^{3} .* g'(z^{2}) $

g' is the sigmoid gradient which is the derivative of the sigmoid function. My guess it will be a horizontal line at the beginning and will be a straight line when it curves up and down. 

It is then possible to add up all of these errors and get the partial derivative. 

$\Delta_{i,j}^{l} = \Delta_{i,j}^{l} + a_{j}^{l} * \delta_{i}^{l+1}$

So I can use this derivative to guide the Theta Matrices in the right direction. 

### Results of Neural Network Learning Project 

![image](https://user-images.githubusercontent.com/20827630/184470456-560fb781-27d8-4d60-88be-59b68139a62f.png)


### Week 6: Regularized Linear Regression for Bias/Variance 

#### Explanation: 

So you have made an algorithm, (in this case a linear regression with a regularization parameter), it now time to optimize the algorithm to see which parameters give the best model. 

What if the model you are making doesn't accurately represent the test data? Well you can try a battery of different modifications that are suggested: 

- Getting more training examples
- Trying a smaller amount of features
- Getting additional features
- Trying polynomial features
- Increasing or decreasing $\lambda$

So when the hypothesis does as well with the prediction as you would like, there is still an issue here. The hypothesis is tested with this data. So if you get perfect predictions, it might mean that the model will only work with that dataset. Its like teaching a student with questions in A hw set and then placing those exact same questions in the final exam. You want to test the model's ability to generalize. 

With this in mind the next phase of testing may begin. This involves creating different datasets for testing. This can be made from the original dataset by performing a 70:30 split. 70% of the data will be used to train the hypothesis and the other 30% is used to evaluate the hypothesis. 

There is a new metric that needs to be considered called the Test Set Error and was summarized by Professor Ng himself. 

![image](https://user-images.githubusercontent.com/20827630/184552158-571517d0-9514-4ded-b5d5-6be1a519df20.png)


Source: Machine Learning with Andrew Ng - Week 6 - Evaluating a Hypothesis


However, there is another set the Cross Validation set that will allow for choosing the appropriate amount of polynomial features. First Theta is chosen by training set, the different polynomial degrees are tested on CV set and the lowest error for that one is used on the test set. We can now determine whether there is High Bias(Underfitting) or High Variance(Overfitting). The different scenarios are shown in a figure from the course. 

![image](https://user-images.githubusercontent.com/20827630/184552869-dec38150-0f98-4a98-af62-ac1c4cde63ea.png)

Source: Machine Learning with Andrew Ng - Week 6 - Diagnosing Bias vs Variance 


So how can the regularization term help with this? Well as you have seen from previous lessons, regularization can destroy the effects of polynomial features. So what $\lambda$ value will get the correct model? Well as the professor said, we can try a whole different array of regularization parameters and see which model is correct. 

Professor Ng summarizes this very well with the following diagram from his course. 

![image](https://user-images.githubusercontent.com/20827630/184553380-5379c104-6aa8-4743-8f02-1358a3b863db.png)

Source: Machine Learning with Andrew Ng - Week 6 - Regularization Bias and Variance 

You can choose the right $\lambda$ and use it to make the best hypothesis. 


This is all the information that will be exercised in the project for this Week. 

#### Results

![image](https://user-images.githubusercontent.com/20827630/184470566-a8f478f1-0ebe-4ec7-888c-6d3ef039afed.png)


### Week 7: Support Vector Machines 

#### Explanation: 

Support Vector Machines are a black-box algorithm that uses an optimization objective that is a little more difficult then the previous weeks. 

The optimization objective is a play on the optimization objective for logistic regression. 

To understand this modified objective, it is required to understand a modified view of the sigmoid function. 

Instead of z in the sigmoid function, replace it with its other representation which is $\Theta^{T}*X$

It is seen that for both cost functions that comprise logistic regression, when y = 1, the cost function gives a proper classification when $\Theta^{T} * X $ is very large. For y = 0, the other cost function shows a proper classification when $\Theta^{T} * X $ is very small. So how can can we use this information? Well, we can simplify the logistic equation into a piecewise function. 

The Cost function for y = 1 can be reduced to a line with a negative slope connected to a line with 0 slope. 

The Cost function for y = 0 can be reduced to a line with a positive slope that extends from a line with 0 slope. 

This is shown in the diagram taken from the course. 

![image](https://user-images.githubusercontent.com/20827630/185022952-5d3a71c9-bfbc-4943-b448-4fc6ca2716f8.png)

Source: Machine Learning with Andrew Ng - Week 7 - Support Vector Machines - Lecture Slides 

So now instead of the logistic Cost function which uses exponentials, we can now use these modified cost functions which don't have exponentials. 

## Cost Function for Support Vector Machines 

$ \Sigma_{i=1}^{m} y^{(i)} * cost_{1}($\Theta^{T}*x^{i}) + (1 - y^{(i)}) * cost_{0}($\Theta^{T}*x^{i}) + \frac{1}{2} *\Sigma_{i=1}^{n} \theta_{j}^{2} $

Now instead of using lambda to control the shape of the function, we are using C to control the slope of the decision boundary which is a straight line. This C parameter can be decreased to make a vertical line or decreased to make a horizontal line. Finding the correct C parameter will allow to correctly separate the different data classes. 

The Extra term at the end is responsible for creating the margins that can make more accurate decision classifiers. 

#### Math for Large Margin Classification 

TBD

#### Kernels 

Okay, so the SVM seems to perform well on data that is linearly separable, that is to say the data points for each class could be separated with a linear decision boundary. What about data that requires a non linear decision boundary? The professor showed an example as so: 

![image](https://user-images.githubusercontent.com/20827630/185027221-ebda4f14-b840-4360-ab46-5dd7355d8cd8.png)

Source: Machine Learning with Andrew Ng - Week 7 - Support Vector Machines

The decision boundary is an oval shape and is comprised of many polynomial features. This is very inconvenient way to represent the boundary. Is there perhaps a more convenient way? 


Time to put that mathematical creativity to good use again. 

This time, it was suggested to use landmarks in order to calculate similarity metrics. The new x values are then compared to these landmarks and this result becomes a feature in the new polynomial which acts as the hypothesis.

So this is interesting, if x is close to any of these landmarks, the result of the hypothesis function will be greater then the threshold value so you would predict 1. If x is significantly far from any of these landmarks, the hypothesis function will not be above the threshold value so it will return 0. 

These landmarks are kind of acting like a Sonar detector. If one of these landmarks detects an X coordinate if its close enough, it will predict as a whole that the response is the classification of 1. If the sonar detectors can't detect the point coordinate, the response is the classification of 0. 

![image](https://user-images.githubusercontent.com/20827630/185538994-00cd1472-dc5f-47b3-8e07-40563b7e6541.png)

Source: Machine Learning with Andrew Ng - Week 7 - Support Vector Machines - Kernels 1 

These landmarks have to come from somewhere though. Where should they be taken from? They are taken from the coordinate pairs (x,y). Similarity functions are computed 
using the x coordinate as the landmark. 


#### Results of Support Vector Machine Project 

![image](https://user-images.githubusercontent.com/20827630/184470808-cf0fb79e-3c8f-44fb-a0f7-3115078c8c02.png)

## Unsupervised Learning Methods 

What is unsupervised learning? It is a way of drawing conclusions without being given a training set to work with. This tends to be useful for grouping things together also known by its alternate name of Clustering. Its useful for distinguishing points from each other and has been used in astronomy, social network analysis, Market Segmentation and Organizing computer clusters. In this section, the K-means clustering algorithm will be analyzed. 

### Week 8: K-means Clustering and PCA

#### Explanation for K-means: 

This unsupervised learning algorithm looks at a dataset and places K number of clusters in the dataset. Assign each data point to its closest cluster and then for each cluster, recompute the new centroid location by averaging all the values assigned to that cluster. This process then repeats until the most optimum cluster placement is achieved. The end result looks something like this. 

![image](https://user-images.githubusercontent.com/20827630/187011219-929d22f8-1107-498b-a6d2-73b32ceac919.png)

Source: Machine Learning with Andrew Ng - Week 8 - Lecture Slides 


#### Cost function for K-means and PCA

The closest cluster to each data point is found through the following minimization objective. 

 min k || $x^{i} - \mu_{k}$||
 
The Cost function is merely choosing the smallest norm (distance) between each datapoint and prospective centroid and it is referred to as the distortion function.

#### Important considerations
Its important for this algorithm that you engage in random initialization of centroids. The number of centroids should be less then the number of examples. Choose some 
training examples to serve as the centroids. Make sure to do these random initializations many times to determing best distortion since local optima is a problem.

In addition, the number of ideal clusters can not only be found using the elbow method as shown below but can be decided upon with domain knowledge i.e. t-shirt sizes. 

![image](https://user-images.githubusercontent.com/20827630/187012932-1b05f74a-ed27-4fcb-b45b-c2b470c3e1aa.png)

Source: Machine Learning with Andrew Ng- Week 8 - KMeans Clustering -  Lecture Slides 

#### Explanation for PCA

PCA stands for Principal Component Analysis. Imagine if you have a dataset comprised of thirty features. There are many different relationships to explore. If you wanted to make the investigation a little easier, you could use what is called a dimensionality reduction technique. If the feature space is two dimensional, you could try and place that data into one dimension for example. 

The way this is done is to draw a line through the dataset in such a way that the sum of squares between the points and that line are minimized. 

![image](https://user-images.githubusercontent.com/20827630/187014470-169e22dd-fd50-4076-a001-413e97d53310.png)

Source: Machine Learning with Andrew Ng - Week 8 - Principal Component Analysis - Lecture Slides 

Of course, this extends to higher dimensions. If you want to reduce a three dimensional dataset to a two dimensional dataset you need to find two lines that the points have the smallest sum of squares distance from. 

#### PCA algorithm 

So in order to perform this dimensionality reduction technique, first you need to perform feature scaling. 

$$ \mu_{j} = \frac{1}{m} * \Sigma(x_{i}) $$

Subtract this mean value from the feature values to get normalized values. 

It is then time to compute the covariance matrix which is a matrix that shows the variance between each pair of datapoints. 

$$\Sigma = \frac{1}{m} * \Sigma(x^{i} * (x^{i})^{T})  $$

From this matrix, it is possible to find eigenvectors of that matrix through singular value decomposition. These are the "components" referenced in Principal component analysis. 

Now you just need to decide how many components you want to keep. These are the k top components. This is the reduced Eigenvector matrix U'. Simply multiply by the x vector to get the compressed representation z. 

One can recover the approximate original representation by multiplying Ureduce with the compressed representation. Note however, that since information was lost to create the compressed representation, one can only require an approximation of the original representation. 

#### Deciding on number of components 

So how are the number of components decided. Well a metric is used to choose the number of components that can preserve a certain level of variance. In this case, it is desired to preserve 99% of the variance. The number of components necessary to do this can be represented with the formula shown in the following slide from the course. 

![image](https://user-images.githubusercontent.com/20827630/187326417-7d01576d-453a-4e31-a02e-fbfa43f16080.png)
Source: Machine Learning with Andrew Ng - Week 8 - PCA - Choosing Particular Number of Components

There is another way to do this though. This involves using the matrix S which is a square matrix that has values on the diagonal. It is possible to choose only a subset of these values on the diagonal and add them up. Then divide the values by total summation of the diagonal to see what the variance is. The number of entries in the numerator correspond to the number of components. 

So the best time to use the PCA alrogithm is when one wants to compress the dataset so it doesn't take as much space, reducing the size of the input feature space and to visualize high dimensional data in an easier way. It is recommended to try to use the original dataset first and if necessary go to PCA. 

#### Results of K-means Clustering and PCA Project 

![image](https://user-images.githubusercontent.com/20827630/184471056-49379698-d58d-4381-933a-d09ddbf96a75.png)

### Week 9: Anamoly Detection and Recommender Systems 

#### Explanation: 

Anomaly detection involves trying to distinguish a bad result from the others. The failure modes though can be numerous. An example used in the machine learning course was the detection of faulty airplane engines. The good examples were clustered around a point but there was one example that was way outside the cluster. This fail could be the result of a bad bolt, bad piston, bad sparkplug etc. 

![image](https://user-images.githubusercontent.com/20827630/188342085-0c5b8065-6fdd-46e4-bbd7-4e639efb56b3.png)
Source: Machine Learning with Andrew Ng - Week 9 - Anomaly Detection 

As a result, it was desired to use an epsilon cutoff. All of the good examples seemed to sit within a certain circular area. The fail example lies outside of that circular area. This was shown in the slide from the course.  

![image](https://user-images.githubusercontent.com/20827630/188342331-3ec7e39f-941e-4f47-9049-5ecff5467fe8.png)
Source: Machine Learning with Andrew Ng - Week 9 - Anomaly Detection 

So how can the fails be distinguished from the passes in this case? Gaussian functions seem like a useful way to do this. 

The differences between an anomaly detection system and a supervised learning system is the training set and the nature of the fails. An anomaly detection system has a small amount of positive examples compared to failed examples. An anomaly detection system has a wide variety of different anomalies that need to be distinguished from good examples. Some examples are 

- Fraud Detection 
- Airplane Manufacturing 
- Monitoring Server Racks 

The supervised learning system has many examples both positive and negative. The supervised learning system has fail examples that don't seem to change all that much so there is no variability in that regard. Some examples of these types of situations are 

- Email Spam Classification 
- Weather Prediction (Sunny, rainy etc)
- Cancer classification

#### Cost function for Anomaly Detection and Recommender Systems. 

A gaussian function shows a distribution of likely values where it peaks in the middle and tapers off at the ends. This is represented by a mean and a standard deviation. 

![image](https://user-images.githubusercontent.com/20827630/193379609-7f9a05d8-b62c-4f31-b8e5-90b1ac7feead.png)
Source: https://intuitivetutorial.com/2021/01/03/gaussian-distribution-explained-visually/ Author: Dr. Sajil C. K.

$\mu = \frac{1}{m} * \Sigma(x_{i})$

$\sigma^{2} = \frac{1}{m} * \Sigma(x_{i} - \mu)^{2}$

So one needs to choose features that can show evidence of anomolous behavior. This is reprsented by $x_{i}$. Then find mean and standard deviation of all the features for the training examples. This is your collection of gaussian distributions. One for each feature of the training examples. Maybe for the car engine example, there will be a feature for engine noise, mechanical vibrations, fuel injection flow rate etc. 

For the new training example, each feature  of that example is compared to the appropriate gaussian distribution. The probabilities calculated for each feature will then be multiplied together for that training example. If the total probability is below the threshold epsilon value then that is an anomolous example. 

#### Making an anomaly detection system 

If one wanted to make an anomaly detection system, take a training set of good engines and use a CV scheme that includes a small set of anomolous examples. Once a model is refined from the CV scheme apply to a test set. 

Fit the model p(x) with the training data and then predict the anomolous example with the cross validation set. The cross validation set can also be used to find the optimal cutoff point $\epsilon$. There are three different evaluation metrics recommended by Professor Ng. 

- True Positive, False Positive, True Negative, False Negative 
- Precision/recall
- F1-score

#### Choosing features for Anomaly detection 

It looks like feature choice should be a set of features whose values can be extremely large or extremely small. The professor chose to use the server monitoring as the example. There are features for memory use, number of disk accesses, CPU Load and network traffic. It is also possible to perform feature engineering with the base features as well if you wish. 

#### Results of Anomaly Detection and Recommender systems 

![image](https://user-images.githubusercontent.com/20827630/184471099-8c76f324-9498-4f65-be91-87334682f227.png)

# End of Projects for Machine Learning Course with Andrew Ng 



