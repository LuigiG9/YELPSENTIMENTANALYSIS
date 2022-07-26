# YELPSENTIMENTANALYSIS

# Business Recommendation

The file "analisi-yelp.ipynb" contains an analysis of the Yelp Dataset with the aim of recommending 10 businesses to a specific user.
We've used the "business.json","review.json" and "user.json" files from the Yelp Dataset.
First of all they've been calculated some stathistics , such as :
-The total number of users
-The average number of reviews made by the users
-The average number of compliments recieved by the users
-The average number of fans for users
-The average number of elité years


![image](https://user-images.githubusercontent.com/58850870/180992367-763e9237-90ca-4322-a42c-c46693f714d1.png)

At this point, We've selected the % of users that are above or not this stathistics, obtaining the following results:

![image](https://user-images.githubusercontent.com/58850870/180992679-644e15e0-2f86-4de7-a0ac-0f6226e88fd9.png)

We can see that the majority of the users places under these average values.

This is the augmented dataset after this phase of preprocessing.

![image](https://user-images.githubusercontent.com/58850870/180993430-5dc7d34b-6f1f-40b6-9aeb-229a0c3dfdb4.png)

Now, we've selected the "good Users" : these are the  users that have all of these previous stathistics above the average values.

At the same time, we've obtained the "good Locals" , such as the locals that have been reviewed positively from the good users:
![image](https://user-images.githubusercontent.com/58850870/181014000-18fd0f85-25b8-4a94-893f-776dad065858.png)

For each user we've obtained the number of friends:
![image](https://user-images.githubusercontent.com/58850870/181014106-9a90b942-2fda-4829-9d2a-98e94ae2247a.png)

Then we've distinguished 2 cases:
-The user hasn't got any friend : in this scenario the algorithm selects 10 locals ( that hasn't been reviewed negatively from the user) from the "Good Locals"
-The user has at least 1 friend: in this case the algorithm firstly selects the list of friends, then selects the businesses that this friends have reviewed positively
deleting the ones that our user has reviewd negatively. If the number of this locals is less than 10 , the algorithm selects the missing businesses from the Good Locals.

![image](https://user-images.githubusercontent.com/58850870/181015202-969e2d61-5340-4cdd-9b43-2dd02024d0f2.png)

At the end , we've obtained also a map with all of these locals:
![image](https://user-images.githubusercontent.com/58850870/181015352-c02e52a1-e507-4f67-b3d8-64fd0e93f386.png)

__________________________________________________________________________________________________________

# YELP SENTIMENT ANALYSIS WITH MULTICLASS CLASSIFICATION

The file "big-data-final-project.ipynb" has been used to make a Sentiment Analysis of the reviews from the YELP dataset using SparkNLP and MLlib.

The aim was to distinguish the reviews in 3 Classes: Positive (>3 Stars) , Neutral (=3 Stars) , Negative (<3 Stars). So, we've evaluated 5 different approaches to create a Multiclass Classifier, such as: Logistic Regression, Random Forest, Naive Bayes, Universal Sentence Encoder, BERT.

![image](https://user-images.githubusercontent.com/58850870/181016403-8586ff11-e87f-40fa-90c8-d98d378ca7a8.png)
In this picture we can see the flow of our project. First of all the dataset was uploaded into Neo4j DB (just the "review.json" file).
![image](https://user-images.githubusercontent.com/58850870/181016670-35f44a8f-e5ba-4326-9be1-b51fff81e022.png)
Then we've imported the data ( selecting only the fields : "text","stars") into Kaggle, and at the end we've saved the output into MongoDB.

We've also made a simple analysis of the dataset, focusing on : the length of the reviews, the number of words and the most frequent words.
![image](https://user-images.githubusercontent.com/58850870/181017414-adee8e67-9be4-4609-b831-0c0553f3987b.png)
![image](https://user-images.githubusercontent.com/58850870/181017468-704c1f49-642b-403b-8d02-98ca4d0ac051.png)
![image](https://user-images.githubusercontent.com/58850870/181017527-23c778e3-2399-4881-a954-de2e1e049264.png)
We've obtained the following results about the accuracy:
![image](https://user-images.githubusercontent.com/58850870/181017750-b77bc87d-e71e-4987-8a0c-d65a2dbd7ebd.png)
And we also wanted to show the average number of errors ( based on each class) of these 5 approaches:
![image](https://user-images.githubusercontent.com/58850870/181018043-b77ab869-605b-4c2c-96fe-a7ce6f258700.png)


_______________________________________________________________________________
If you want to read more about the documentation you can see the pdf files in the repository.
