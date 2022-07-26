# YELPSENTIMENTANALYSIS
YELP SENTIMENT ANALYSIS

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

