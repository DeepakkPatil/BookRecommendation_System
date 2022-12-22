<h1><u>BookRecommendation_System</u></h1>

Collaborative and Popularity based Recommendation System using Flask and WebDev




![1](https://user-images.githubusercontent.com/108725514/198863653-429f7531-2075-4c05-b58b-406dff48674b.png)

![image](https://user-images.githubusercontent.com/108725514/198863745-5252e70d-ee8f-4034-b5c6-6b657a93a863.png)




<h4>Developed A python App on Pycharm (app.py) using Flask and WebDev which Recommends book on the basis of Book searched.</h4>


There are 4 types of recommendation systems:

* Popularity Based : Recommendations are provided on the basis of Popularity. Trending Books are shown. This type of system uses formula for accessing popular Books.


* Content Based : Recommendations are provided on the basis of Type of content acessed by user.This is done by creating tags.


* Collaborative Filtering Based : Recommendations on the basis of common interests shared by multiple users.


* Hybrid : Which used both content and collaborative Filtering


I have used Flask Python Framework to create this Website app and used renderTemplate to showcase the html page.<br>
And pickle library to make pickle files to be used to extract  data in app.py and data is being uploaded through Book_Recommendation.ipynb

1) In app.py file :Written code to load the content from pickle file into Diff datasets

```

popular_df=pickle.load(open('popular.pkl','rb'))

pt=pickle.load(open('pt.pkl','rb'))

books=pickle.load(open('books.pkl','rb'))

similarity_scores=pickle.load(open('similarity_scores.pkl','rb'))

```

<br>
<br>

2) In Book_Recommendation.ipynb

```

#for polarity based recommendation

import pickle

pickle.dump(popular_df,open('popular.pkl','wb'))

#for the collaborative recommendation

pickle.dump(pt,open('pt.pkl','wb'))

pickle.dump(books,open('books.pkl','wb'))

pickle.dump(similarity_scores,open('similarity.pkl','wb'))

```

<h3>Deployment</h3>
I have used Heroku to deploy my project :  

Heroku requires : requirements.txt file and ProcFile (The code of each is written Down)
 
In the terminal of pycharm write following lines to deploy the project :

```
git init
heroku login
git add .
git commit -m "message"
git push heroku master

```

<h3>codes of each file </h3>

* requirements.txt

write this code in  requirements.txt file : 
```
flask
numpy
pandas
gunicorn

```

* Procfile

```
web: gunicorn app:app

```






