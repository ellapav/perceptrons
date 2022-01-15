The two perceptrons in this Repository illustrate the Perceptron Learning Model. 

In perceptron1.ipynb we consider the following training data with two categories (labels):

C1(1) : (0,1.5)^T , (1,1)^T , (2,2)^T , (2,0)^T

C2(−1) : (0, 0)^T , (1, 0)^T , (0, 1)^T

That is, there are seven data points, each data point has two features and a corresponding label.
(# data = m = 7, # features = n = 2)

In perceptron2.ipynb we consider the data of people applying for credit cards, and a banker has determined if they should be in category:

Approved (1)

Denied (-1)

Each data point has 16 associated features (found in credit_data.csv) and a corresponding label (found in credit_label.csv).
(# data = m = 653, # features = n = 16)



The goal in both programs is to determine the best hyperplane that separates the two data sets. 



In both cases the hyperplane is given by w^T x = 0, where w is the weight vector and x = [1, x_1,...,x_n]^T where n is the number of features of a data point.
We use the Perceptron Learning Algorithm to start with an initial guess and update it to the optimal solution. The main two functions which perform the Perceptron Learning Algorithm are defined:


w_fit2a(w_old , data , label, gamma, EPOCH) # best for visualizing the evolution of the line

	w_old = 1 x 3 initial-guess weight vector.
	
	data = k x 3 matrix. Column 1 contains 1's, Columns 2 and 3 contain the data
	
	label = k x 1 column. 1 for Class 1, -1 for Class 2.
	
	gamma = learning rate (0<gamma<1)
	
	EPOCH = maximum # of cycles through the data points
	
returns a graph of the data points, the iterations of the 3 x 1 weight vectors, and the corresponding hyperplanes plotted. It also tells how many EPOCH's it took to achieve separation (if possible before the pre-set EPOCH value).
(Note this function only works for data with 2 features.)


w_fit3(w_old , data , label, gamma, EPOCH) # best for getting the weight vector quickly. 

	w_old = 1 x (n+1) initial-guess weight vector.
	
	data = k x (n+1) matrix. Column 1 contains 1's, Columns 2 through n+1 contain the data
	
	label = k x 1 column. 1 for Class 1, -1 for Class 2.
	
	gamma = learning rate (0<gamma<1)
	
	EPOCH = maximum # of cycles through the data points
	
returns a (n+1) x 1 weight vector that may separate data with hyperplane w^T x = 0
 
