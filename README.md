## Abstract

Low quality reviews present a challenge to the value of review-based sites. We will use NLP techniques and feature engineering to classify low-quality reviews on MiddCourses. Our model's accuracy will be tested against an anonymous, annotated dataset from MiddCourses.

![](model_drawing.png)


## Motivation and Question:
**We have user information for which predictive models would help us give users better experiences.**


We want to determine the estimated quality of reviews on MiddCourses to improve user experience. Low quality reviews provide little (or even negative) value to users. This in turn decreases the value of MiddCourses as a whole. A **classifier** for automatically detecting such reviews would be useful for sorting tasks and as a potential flag to make finding fraudulent reviews easier.

Such reviews can take several forms:

1. Low-effort reviews where the reviewer put limited time into accurately reviewing the course. This is characterized by many sliders and values left at default positions and a short and general review content.
2. Fraudulent reviews where the reviewer never took the indicated course. This is often characterized by randomness or conflicting features in the review and very general text.
3. Overly-negative (hyperbolic) or review bombing reviews that offer a very limited negative perspective on a course/instructor that is unlikely to be accurate.

We will approach this problem by experimenting with feature engineering and NLP-methods to find a set of features which would be effective in classifying reviews based on quality and creating a classification model that would accurately predict review quality using the feature set.

The first step of our process will involve **triple-annotating** the entire dataset (midd.courses/annotate) and turning these annotations into classification labels. Since we don’t naturally have labels for review quality we use annotations as a ground truth. Since this process is inherently subjective, we will each annotate the data to reduce bias.

We will then perform **feature engineering and selection** to gather a list of features to use for our final classification step.

We will implement a **pipeline** that generates the features and we will build our **classifier**.

We hope to also implement a production pipeline and export the trained classifier’s weights to use similarly.


We will measure how our model stacks up against our goal by measuring its accuracy on an annotated test data set. We will carefully consider model sensitivity and specificity. Since we do not have demographic data on any reviews, it will not be possible to check our model’s bias against demographic factors.


## Planned Deliverables:
### We intend to deliver:
annotated data
feature pipeline (python/js)
classifier (python)
jupyter notebook to explore model


### Full success:
feature pipeline and classifier implemented in production on MiddCourses
+ all below content
### Partial success:
annotated data
feature pipeline in python
classifiers in python
notebook that explores the model
