## NAME : KARTHICK KISHORE T
## REG NO : 212223220042
<H3>DATE:</H3>
<H1 ALIGN =CENTER>Heart attack prediction using MLP</H1>
<H3>Aim:</H3>  To construct a  Multi-Layer Perceptron to predict heart attack using Python
<H3>Algorithm:</H3>
Step 1:Import the required libraries: numpy, pandas, MLPClassifier, train_test_split, StandardScaler, accuracy_score, and matplotlib.pyplot.<BR>
Step 2:Load the heart disease dataset from a file using pd.read_csv().<BR>
Step 3:Separate the features and labels from the dataset using data.iloc values for features (X) and data.iloc[:, -1].values for labels (y).<BR>
Step 4:Split the dataset into training and testing sets using train_test_split().<BR>
Step 5:Normalize the feature data using StandardScaler() to scale the features to have zero mean and unit variance.<BR>
Step 6:Create an MLPClassifier model with desired architecture and hyperparameters, such as hidden_layer_sizes, max_iter, and random_state.<BR>
Step 7:Train the MLP model on the training data using mlp.fit(X_train, y_train). The model adjusts its weights and biases iteratively to minimize the training loss.<BR>
Step 8:Make predictions on the testing set using mlp.predict(X_test).<BR>
Step 9:Evaluate the model's accuracy by comparing the predicted labels (y_pred) with the actual labels (y_test) using accuracy_score().<BR>
Step 10:Print the accuracy of the model.<BR>
Step 11:Plot the error convergence during training using plt.plot() and plt.show().<BR>

<H3>Program: </H3>

```
import numpy as np
import pandas as pd
from sklearn.neural_network import MLPClassifier
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.metrics import accuracy_score
import matplotlib.pyplot as plt
data = pd.read_csv("/content/heart.csv")
x = data.iloc[:,:-1].values
y= data.iloc[:,-1].values
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=42)
scaler = StandardScaler()
x_train=scaler.fit_transform(x_train)
x_test =scaler.transform(x_test)
mlp=MLPClassifier(hidden_layer_sizes=(100,100),max_iter=1000,random_state=42)
training_loss = mlp.fit(x_train,y_train).loss_curve_
y_pred=mlp.predict(x_test)
accuracy = accuracy_score(y_test,y_pred)
print("Accuracy:",accuracy)
plt.plot(training_loss)
plt.title("MLP Training Loss Convergence")
plt.xlabel("lteration")
plt.ylabel("Training Loss")
plt.show()
import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.neural_network import MLPClassifier
from sklearn.metrics import accuracy_score,classification_report,confusion_matrix
from sklearn.datasets import load_breast_cancer
data = load_breast_cancer()
x=pd.DataFrame(data.data,columns=data.feature_names)
y=pd.Series(data.target)
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=42)
scaler=StandardScaler()
x_train_scaled=scaler.fit_transform(x_train)
x_test_scaled=scaler.transform(x_test)
mlp_classifier=MLPClassifier(hidden_layer_sizes=(64,),max_iter=1000,random_state=42)
mlp_classifier.fit(x_train_scaled,y_train)
y_pred=mlp_classifier.predict(x_test_scaled)
accuracy=accuracy_score(y_test,y_pred)
cont_matrix=confusion_matrix(y_test,y_pred)
classification_rep=classification_report(y_test,y_pred)
print("Accuracy:{accuracy}")
print("\nConfusion Matrix:")
print("conf_matrix")
print("\nClassification Report:")
print(classification_rep)

```
<H3>Output:</H3>


![323846134-ca59d71b-71db-42bd-a280-7a6a3acba4bb](https://github.com/Sangavi-suresh/EX-6-NN/assets/118541861/14784e82-eb11-4c37-aa0a-748c058f8e43)




<H3>Results:</H3>
Thus, an ANN with MLP is constructed and trained to predict the heart attack using python.
