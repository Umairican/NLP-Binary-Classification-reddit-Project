# Binary Classification and Natural Language Processing with reddit

---

### Table of Contents

* [Problem Statement](#user-content-problem-statement)
* [Executive Summary](#user-content-executive-summary)
* [Conclusions and Recommendations](#user-content-conclusions-and-recommendations)
* [Additional Information](#user-content-additional-information)


### Problem Statement

Can I create an effective model to tell from which subreddit it is?

The baseline for comparison with my models is simple; since this is a binary classification project: can my model outperform the age-old decision metric of flipping a coin (can my model beat 50/50)?




### Executive Summary

This project explores using different Natural Language Processing models to attempt a binary classification of the age-old question, "which subreddit is this coming from?"

For those of you who don't know, reddit(include link here)

Some words about this project go here.

My first run-through of this project centered on the following subreddits:

LifeProTips:

Some yada about the subreddit


ShittyLifeProTips:

Some yada about the subreddit


/r/LifeProTips and /r/ShittyLifeProTips -> testing for sarcasm detection in natural language processing.



My second run-through of this project centered on the following subreddits:

AskMen:


AskMenOver30:


/r/AskMen and /r/AskMenOver30 -> exploring the difference in language with age, and whether my models could detect this.



My third run-through of this project centered on the following subreddits:

/r/MadMen:

A subreddit dedicated to one of TV's greatest shows. Don Draper, oozing with his effortless charm and complete disregard for the feelings of partners, 

/r/TheSopranos:

A subreddit dedicated to arguably the greatest TV series of all time.




---

### Conclusion and Recommendations

The more robust of my analyses, classifying The Sopranos and Mad Men, showed that using CountVectorizer and Logistic Regression could reliably predict the correct subreddit for 90% of cases, with false positives and false negatives being roughly equal.

The use of additional stop words was important. For each iteration where I added a few more stop words to my list, the train and test scores would increase. With a train score of 0.98 and a test score of 0.90, we can see that my pipeline of CountVectorizer and Logistic Regression (although overfit) is quite good at predicting which subreddit on text alone.

Given more time, I would explore either including more stop words, or classifying using "definers": words that definitely state that it is one subreddit over another. I believe this would increase the overall accuracy of the scores of my top model.





---

### Additional Information

Don Draper Many Faces https://screenrant.com/mad-men-hilarious-memes-true-fans/

Tony Soprano Home Wear https://dankanator.com/62146/best-tony-soprano-memes-from-the-sopranos/

