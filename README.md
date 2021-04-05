# Binary Classification and Natural Language Processing with reddit



### Table of Contents

* [Problem Statement](#user-content-problem-statement)
* [Executive Summary](#user-content-executive-summary)
* [Conclusions and Recommendations](#user-content-conclusions-and-recommendations)
* [Additional Information](#user-content-additional-information)


---

### Problem Statement

Can I create an effective model to tell from which subreddit it is?

The baseline for comparison with my models is simple; since this is a binary classification project: can my model outperform the age-old decision metric of flipping a coin (can my model beat 50/50)?

---

### Executive Summary

This project explores using different Natural Language Processing models to attempt a binary classification of the age-old question, "which subreddit is this coming from?"

For those of you who don't know, reddit(include link here) is a network of communities, called subreddits, based on various interests. These range from sports teams to cities to advice regarding just about anything you can think of. In my project, I aimed to try and compare more similar subreddits to see how well machine learning models could do based on just the post title and body of text.

For all analysis, only the features for the post title (called 'title') and post body (called 'selftext') were used in trying to determine the target (subreddit).


**My first run-through of this project centered on the following subreddits:

LifeProTips: a subreddit about different tips to improve your life.

ShittyLifeProTips: a subreddit filled with sarcastic life pro tips that would be ill advised to actually attempt in real life.

The goal of this was: testing for sarcasm detection in natural language processing.


Early on in my data collection I encountered plenty of issues with my choice of subreddits. ShittyLifeProTips in particular didn't provide much text data in the body of its posts. Most of them were images instead, and would have the word [removed] in brackets instead of any useful information. Ironically, these images are almost always screenshots of text from other social media sites like twitter. Regardless, due to the amount of NaN's and empty text bodies, I decided to simply create these models based on the post titles.

I found that my models were able to score 86-88% accuracy, despite only having the title to work with. I decided to come back around to data cleaning and found that the majority of post titles include the abbreviation for the subreddit in the title (LPT: for LifeProTips and SLPT: for ShittyLifeProTips). It seemed to be a bit too easy, so I decided to use my calling function to scrape some more subreddits until I found a satisfactory pair.


**My second run-through of this project centered on the following subreddits:

AskMen: a subreddit where users can ask men just about anything.


AskMenOver30: a subreddit where users can ask slightly older men, over 30, just about anything.

The goal of this was: testing to see how different the language used in subreddits would be when focused on age as the defining point of differentiation.

Unfortunately, I ran into similar issues with my data, and didn't have much to work with, despite pulling 6,000 posts (3,000 per subreddit).

I created some basic models, but quickly decided to move on to other subreddits that I had pulled posts for.


**My third run-through of this project centered on the following subreddits:

/r/MadMen: A subreddit dedicated to one of TV's greatest shows. It is about advertising in the 1960s and the existential dread that comes from not living the life you want.

/r/TheSopranos: A subreddit dedicated to the most critically acclaimed TV series of all time. It is about the head of a mafia family in New Jersey and the existential dread that comes from having to shoot people as part of your job description.

The body of the posts of these were much more robust, giving my EDA and models much more to work with. I cleaned the body of the posts using RegEx to try and remove a number of things like hyperlinks and punctuation, choosing to focus on the language used by people posting in these subreddits.

I chose to add to the list of stop words during my data cleaning. I began with detritus that was found after Count Vectorizing: https, www, imgur, etc... I think moved on to exploring the data through bigrams and trigrams, which showed that there are a number of words that are common in both subreddits (hardly a surprise since btoh subreddits are about dark drama TV series). I added common words found in both subreddits to my list of stop words: watched, show, series, scene, etc...

I ran my models after each iteration of cleaning, with my combination of CountVectorizer and Logistic Regression improving most with each iteration. This model was able managed to be 90% accurate on the testing data, with roughly equal numbers of false positives and false negatives.

My other models, TfidfVectorizer and Bernoulli Naive Bayes, and CountVectorizer and K-Nearest Neighbors, had more issues with identifying Mad Men when the posts were The Sopranos (false negatives). Given more time, I would explore this and see what is causing the confusion for these models.



---

### Conclusion and Recommendations

The more robust of my analyses, classifying The Sopranos and Mad Men, showed that using CountVectorizer and Logistic Regression could reliably predict the correct subreddit for 90% of cases, with false positives and false negatives being roughly equal.

The use of additional stop words was important. For each iteration where I added a few more stop words to my list, the train and test scores would increase. With a train score of 0.98 and a test score of 0.90, we can see that my pipeline of CountVectorizer and Logistic Regression (although overfit) works well.

Given more time, I would explore either including more stop words, or classifying using "definers": words that definitively state that it is one subreddit over another. I believe this would increase the overall accuracy of the scores of my top model.


---

### Additional Information

*Presentation Meme Source: [Don Draper Many Faces](https://screenrant.com/mad-men-hilarious-memes-true-fans/)

*Presentation Meme Source: [Tony Soprano Home Wear](https://dankanator.com/62146/best-tony-soprano-memes-from-the-sopranos/)

