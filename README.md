# Machine-Learning-Assignment1
This Repository consists of source code of the assignment

Question 10 –
 

Given data set and the respective labels are as following:
Data = [1,2,3,6,6,7,10,11]
Labels = [0,0,1,1,1,0,0,0] let’s assume ‘dots’ as ‘class 0’&‘X’ as ‘class 1’

1.	Now, lets divide the data in to two equal parts one for training and one for testing.
Training_data=[1,3,6,7]
Test_data = [2,6,10,11]

With given KNN classifier, K=3 we need to identify K samples closest to the test data and assume the label of the majority as the test data’s label.

Distance can be calculated by Euclidean distance: square_root((x1-x2)**2 + (y1-y2)**2)
Here in our case since y-axis is not present, we can assume y1=y2=0.
So, the distance will be |x1-x2|.

For test data ‘2’.Distances will be:	d(2,1) = |2-1| = 1
d(2,3) = |2-3| = 1
d(2,6) = |2-6| = 3
d(2,7) = |2-7| = 4
Now the closest K (K=3)neighbors of ‘2’ are 1,3,6 and majority are of ‘class 1’. So, we assign ‘class1’ to test sample ‘2’.

Similarly, we find for rest of the test data 6, 10, 11.
For test data ‘6’. Distances will be:	d(6,1) = |6-1| = 5
d(6,3) = |6-3| = 3
d(6,6) = |6-6| = 0
d(6,7) = |6-7| = 1
Now the closest K (K=3) neighbors of ‘6’ are 3,6,7 and majority are of ‘class 1’. So, we assign ‘class1’ to test sample ‘6’.

For test data ‘10’. Distances will be:	d(10,1) = |10-1| = 9
d(10,3) = |10-3| = 7
d(10,6) = |10-6| = 4
d(10,7) = |10-7| = 3

Now the closest K (K=3) neighbors of ‘10’ are 3,6,7 and majority are of ‘class 1’. So, we assign ‘class1’ to test sample ‘10’.

For test data ‘11’. Distances will be:	d(11,1) = |11-1| = 10
d(11,3) = |11-3| = 8
d(11,6) = |11-6| = 5
d(11,7) = |11-7| = 4
Now the closest K (K=3) neighbors of ‘11’ are 3,6,7 and majority are of ‘class 1’. So, we assign ‘class1’ to test sample ‘11’.

So, the predicted labels for the test data are predicted_labels =[1,1,1,1].
However actual labels are actual_labels = [0,1,0,0].

2.	The confusion Matrix for the predictions of test data is as follows:

		Predicted labels
		Class 0	Class 1


Actual labels	
 Class 0	
0	
3

	
Class 1	
0	
1


So, the True Positives TP = 1
	True Negatives TN =0
	False Positives FP =3
	False Negatives FN =0

From this we can get, Positives P = TP+FN =1
			Negatives N = TN+FP = 3

Now, to calculate accuracy, we can use formula Accuracy = (TP+TN)/(P+N)
							           = ¼ = 0.25 or 25%
To calculate Sensitivity(true positive rate TPR), we can use the formula 
Sensitivity (TPR) = TP/(TP+FN) = TP/P
		   = 1/1 = 1
	To calculate Specificity (true negative rate TNR), we can use the formula
Specificity (TNR) = TN/(FP+TN) = TN/N
= 0 (since there are no true negatives in this case)

Usually, based ontest and training datasets chosen the predictions and the accuracy, sensitivity, specificity valuesvary accordingly.



