# Yelp Image Classification - CNNs

#### Project by: Bruno Santos

### Contents

- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Data](#Data)
- [Conclusion and Recommendations](#Conclusion-and-Recommendations)

## Problem Statement

In a world of ever-advancing technology, image recognition has become a very hot topic - whether you're aware of it or not. Odds are image recognition is evolving right under your very nose and you may not even recognize it's happening. In many cases, image recognition is evolving in a seemingly harmless way by companies you would never expect. In other cases, it's being developed and put into use by government agencies and contractors in matters of national security.

Just how complicated are these models to build and train, and what goes into doing so? How important is the data, both in terms of quality of data as well as how much data is available? Finally, how accurately can we train image recognition software to be? Utilizing a set of 200,000 photos from Yelp, I will aim to answer these questions and more during the course of this project.

## Executive Summary

Have you ever posted a picture to Facebook only to have Facebook not only recognize where people's faces are - but also suggest WHO the person in question is? Maybe instead you're a Snapchatter, and you love to make use of their face augmentation filters. Perhaps you simply store all of your personal pictures on Google Cloud and use their search tools to find specific pictures of that beach trip you took by passing through certain search queries. Have you ever wondered how it's possible for these apps to just know where people are in pictures, know what parts of your face to augment, or be able to parse your queries despite a tag never having been added to specific pictures?

The answer is image and pattern recognition, and highly sophisticated computer models. What you may not realize as you upload that set of 100 pictures you took over the weekend to Google or Facebook is that you've allowed these corporations to use your data to train their models. Just about every company these days is collecting as much data as they can on their users, and in most cases you're giving it to them freely and unprompted so they can build and perfect these ever-advancing models.

"But how does a computer know what a face looks like, or what a beach looks like," you may be asking yourself. The short answer is: it doesn't. At least not in the same way that you and I know what these are. While computers haven't advanced to the level of a human brain in that we can see an image and immediately know what we're seeing, computers are able to process an image and translate it into a series of numbers representing the pixels in the image. By processing these images and learning patterns that it frequently sees, a computer can "learn" what patterns represent certain real-world objects such as people's faces, beaches, animals, etc.

In this project, I was provided 200,000 photos from Yelp over five different categories - Food, Drink, Inside, Outside, and Menu photos of different restaurants. The images were split in an unbalanced way; while I had over 110,000 images of food, there were only about 3,600 photos of menus. This split makes sense to me as my generation lives on their phones and food pictures are some of the most common pictures any millenial can hope to take. As the saying goes whenever a group tries a new restaurant - "Phone eats first".

My goal was to find out just how "easy" it is to build one of these image and pattern recognition models using Convolutional Neural Networks. Just how long does it take the average person to not only build one of these models, but run through all of the images and truly train a model? How complex does a model have to be in order to really learn what images look like, and how do those changes impact the time it takes one of these models to finish training. Given the imbalance of our data, how much can a model really learn from 3600 images? Given the diversity in image sizes and quality, there was significant image processing that had to occur in order to feed through our model in a uniform manner.

## Data

The 200,000 photos we used are available to download through Yelp [here](https://www.yelp.com/dataset). Due to size contraints and Yelp restrictions, I will not be uploading these.

The CSVs that I used are available [here](./Data)

## Conclusion and Recommendations

In conclusion, despite the models all evaluating at a very high "accuracy" (roughly 90% throughout all of our models save for the "balanced model"), the models were not able to accurately predict the classes that the pictures belong to. This seems to be due in large part to the severely unbalanced classes, where over 57% of the pictures belong to the "food" class. In addition, the pictures do not have any uniformity  throughout them, which causes pictures from different classes to have similar features to other classes (background "noise", overlapping features from different classes, etc.).

In future iterations of this project, it would likely be beneficial to remove some complexity from the project itself (start with predicting food / not food, and then move on to more classes). Additionally, it would be beneficial to have more complex sets of models, although computational and time limitations would add certain layers of difficulty to this. Finally, having more data is always something that can be used to improve models. It's clear why corporations like Google and Facebook allow (and encourage) their users to upload as much data as possible, as it's data that will be used to train their models and make them more efficient and accurate.

One thing to keep in mind is the scale of corporations that are developing and perfecting image recognition models, such as Facebook, Snapchat, Google, Tesla, and several government contractors. These institutions have significantly more access to personnel to work on such projects, as well as computational power, time, and money. The hope is that the companies / corporations developing these large-scale projects use them for "good", and in ethical ways. It stands to reason that a single person with limited computational power and time-constraints would not be able to build models that are as accurate as corporations spending millions on these projects. That said, the models constructed in this project serve as a "proof of concept" that computers are able to learn patterns in pictures and identify these trends and patterns.