# Introduction

During the period of political campaign, twitter is one of the powerful 6 platforms. During this period a large number of politically active individuals post their views. The proposed system helps in fields such as elections wherein political parties can detect the tendency of their fellow members, political leaders can get the public opinion to design the campaign strategies. The work presented compares multiple machine learning models,deep learning models for prospective identification. When tested on human annotated twitter data, the system shows the best F-score for Bi-LSTM with Word2Vec embedding as 0.8630. This shows 13.8% improvement over existing systems in F-Score.

# Dataset

Data used in this work contains  tweets from users. The tweets have been collected using Twitter API. During data collection, 33,820 tweets were collected related to political topics. The tweet belonged to six different categories as mentioned earlier. A Pro person is in favour of a particular party while Anti is against the favour of that party. Since, Twitter doesn’t have any attribute which tells about users political orientation. The users were labelled manually by analyzing their tweets to make a conclusion about their political orientation. The data has been collected with following criteria :

-  The user whose data is to be collected should not be a leader of any political party 
  - User should have tweeted at least 5 political tweets
  - The tweets are in Major Indic Languages namely Hindi and Marathi  along with English

Following figure shows distribution of Dataset:

![alt text](https://github.com/sp31051998/Political-Orientation-of-user-using-Tweet/blob/master/Images/Dataset%20Distribution.png)

# Classification of political orientation

In order to classify user orientation, we used variations of both machine learning algorithms as well as deep neural network models. Deep neural network with Word2Vec Embedding gave the best result. Figure 3 shows the architecture diagram for Tweet Classification. First layer is the input layer which accepts a sequence of words which is then passed through the embedding layer which converts word into fixed sized vector representation. Next layer is Bi-directional LSTM with 100 neurons to capture complex structure followed by a fully connected layer. The last layer is the output layer to which a softmax function is applied which converts output to 6 class probabilities.The loss function which we used is binary cross entropy and optimizer as ADAM optimizer. Following figure shows achitecture of Deep Learning Model:

![alt text](https://github.com/sp31051998/Political-Orientation-of-user-using-Tweet/blob/master/Images/Model%20Architecture.png)

# Results & Discussions

In order to determine political orientation we used both machine learning as well as deep learning models. The test data contained 6764 Tweets along with their labels about political orientation.

#### Machine Learning Model

The preprocessed test data was evaluated on different machine learning algorithms. Among them, Ensemble model(Support Vector Classifier + Random Forest Classifier)had the highest precision of 0.8823 while the Support Vector Classifier had recall and f-score values of 0.8421 and 0.8551 respectively. Overall, the Support Vector Classifier performed best. Figure below contains Precision, Recall and Fscore and  values of machine learning models.

![alt text](https://github.com/sp31051998/Political-Orientation-of-user-using-Tweet/blob/master/Images/ML%20Model%20Comparision.png)

#### Deep Learning Model

For the same test data, the three deep learning models namely LSTM, Bi-LSTM andCNN were implemented with various types of word embeddings.  The word embeddings used were Glove, Word2Vec and FastText. Among, all different models Bi-directional LSTM with Word2Vec embeddings got highest precision value of 0.8740 while Unidirectional LSTM with Word2Vec embeddings got highest recall value of 0.8585 and Bi-directional LSTM with Word2Vec embeddings got highest fscore value of 0.8630 Overall, considering all 3 values Bi-directional LSTM with Word2Vec embeddings model performed best. Figure below contains Precision, Recall and Fscore and  values of deep learning models.

![alt text](https://github.com/sp31051998/Political-Orientation-of-user-using-Tweet/blob/master/Images/DL%20Model%20Comparision.png)

On comparing the existing system average values of Precision, Recall and F-Score with the proposed system,improvement by 18.72%, 9.61% and 13.82% respectively is observed. Figure 6 compares the same among existing and proposed model

![alt text](https://github.com/sp31051998/Political-Orientation-of-user-using-Tweet/blob/master/Images/Exisiting%20System%20vs%20Proposed%20System.png)

# Conclusion
The research belonged to a multi-text classification problem. In this work, we analyzed 33820 tweets which belonged to one of the six classes namely BJP Pro, BJP Anti, Congress Pro, Congress Anti, Shiv Sena Pro, Shiv Sena Anti. Various ML and NN models with word embeddings namely Glove, Word2Vec and FastText, were evaluated for classification of these tweets. The test data contained 735, 1304, 2459, 1149, 885, 232 tweets belonging to Bjp Pro, Bjp Anti, Congress Pro, Congress Anti, Shiv Sena Pro, Shiv Sena Anti respectively. Out of which  596, 1138, 2143, 979, 854, 182 were classified correctly by or system.From the results achieved using different models for different configurations, we have concluded that Bi-directional LSTM with Word2Vec embeddings model performed best with the F-score of 0.8630. During the process of collecting users we found that few users had tweeted their views with Pro orientation with respect to one political party while Anti orientation with respect to another political party. While few users were ambiguous with respect to their political orientation meaning they had tweets having both positive as well as negative views about the same party.