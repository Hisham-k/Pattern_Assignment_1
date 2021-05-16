# Pattern recognition Assignment One

## Made By:

## Abdulrahman Hussam
## Hisham Khalid



# Methods Expilination 

In our solution we implemented 3 functions, batch_algo, online_algo and random generator. We had inspirations from the tutorial code
and then we wrote it our way with some changes.


# 1- Batch_algo

We take x,y as input training data and by default we set the learning rate to 1.

We initialze weights with random values between -1 and 1 and it has the same length as x.

We start weight changes count and epoch count with 0 and then we enter the main loop.

While the norm of the delta is still larger than the error we defind above (Which is a very small number that is close to zero):

    we initialize delta with zeros
    
    We enter a for loop for i in range X.shape[0]
    
        we Multiply weights with X[i] and if Y[i] times the result is < 0, meaning prediction is different than actual output,
    
            We update the delta by subrtacting ( Y[i] * X[i] ) from it 
    
        We get the norm of the delta and then update the weights by subtracting (lr*norm delta) from it
    
        We then check if not all the deltas == zero we update the weight change count
    After the for loop we update the delta and append it in array to be plotted later
    
    We increas the epoch count and then repreat all of this until delta reaches zero


# 2- Online_algo

The online_algo is exactly the same as the batch except we update the weights and delta inside the if condition and not just the delta and we update the weights count also inside the if condition.


# 3- data_generator_algo

    We followed the tutorial initial code and then we used the generated data into our batch and online algorithms.
    
    We calculated the accuray using acuuracy_score by giving it Y_pred and Y_test
    
    We then plotted the line with the data and after that we plotted the delta change.
    
    We drew the line by getting the min value for x1 and max value and drew a line between them.
    
    we calculated x2 from the relation : y=x1w1 + x2w2, and assuming y=0 ( to view on a 2d plane) so >>>>> x2 = x1*w1 /-w2


# Some Comparisons :

## Batch algo vs Online algo for problem one

Batch : Epochs:  966
Weight Changes: 7720
![Delta change of problem 1 for batch_algo](Pictures/1.png) 

Online: Epochs:  110
Weight Changes: 366
![Delta change of problem 1 for online_algo](Pictures/2.png)

## Batch algo vs Online algo for problem four

Batch : Epochs:  9
Weight Changes: 64
![Delta change of problem 4 for batch_algo](Pictures/3.png) 



Online: Epochs:  4
Weight Changes: 9
![Delta change of problem 4 for online_algo](Pictures/4.png)

## Batch algo vs Online algo for data generator

Batch:

Model Accuracy :  100.0 %
Epochs:  6
Weight Changes: 58
![Delta change and model visualization for batch_algo](Pictures/5.png) 
Online:

Model Accuracy :  100.0 %
Epochs:  9
Weight Changes: 18
![Delta change and model visualization for online_algo](Pictures/6.png) 

