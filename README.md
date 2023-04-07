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

- annotated data
- feature pipeline (python/js)
- classifier (python)
- jupyter notebook to explore model


### Full success:

- feature pipeline and classifier implemented in production on MiddCourses
- \+ all below content

### Partial success:

- annotated data
- feature pipeline in python
- classifiers in python
- notebook that explores the model

## Resources Required:

- Data: https://midd.courses/
- Computing power: laptops
- Account: MiddCourses + 2 written reviews (for accessing annotation tool)


## What You Will Learn:

### Nich:
I will research and implement NLP algorithms for feature extraction. I will work on EDA and model evaluation during feature selection steps. And I will work effectively in a group of 3. 
While this project does not directly fit into my suggested interests: recsys, information retrieval, ranking, and network algorithms, I still have strong interest in this project.

### Paul: 
In the reflective goal-setting assignment, my original goal was to do a project on prediction. However, I believe that classification is an important topic in machine learning that is 
equally interesting as prediction. I have mentioned in my goal-setting that the implementation aspect of machine learning is what I would like to focus on, and I think that this project 
would give me an opportunity to do so. Since we will be using real data for this project, it will definitely help me with the practical element of implementation. It will also allow me 
to dig deeper into the topic of NLP (natural language processing). 

### Aidan:
My goal throughout this project is to gain a deeper understanding on the various options for NLP algorithms and feature extraction in terms of text classification. Furthermore, I hope to get a better understanding of the machine learning workflow and collaborative projects through GitHub and Jupyter or VSCode. 

## Risk Statement:

It might be possible that we cannot find features that distinguish low-quality and high-quality reviews. We might not have enough data (~1600 reviews) or enough data balance to make inferences. It might also be possible that our model systematically underperforms for certain groups in a way that makes its implementation unacceptable. We will also need to carefully consider model and pipeline performance to ensure our pipeline and inference can run in production.

## Ethics Statement:

We are assuming that students would be benefited by being presented with higher quality reviews. Likewise professors would benefit by having higher quality reviews of their classes shown first.

It is possible that certain groups of students would be systematically deranked because of the features we decide are relevant. This could be especially true if we decide to opt for using NLP to decide features because it may prefer "standard" dialects of English.

Certainly professors may also be systematically affected negatively because our algorithm may present reviews that are more negative than reality if it views them as high quality.

Conversely, if it presents reviews that are more positive than reality, students may be impacted by being more likely to take a course with a professor they might not enjoy.

And we know from external research that reviews are biased against certain groups of people (women, people of color, etc). So our initial training data may be biased. We hope our annotation method would remove some of this bias.

We believe that our model will make the world (Middlebury) a better place. By identifying high and low quality reviews on MiddCourses we hope to make it easier for Middlebury students to find high quality information on the courses they are searching for. And therefore improve their ability to find courses they will enjoy. This belief assumes that:

1. Higher quality reviews lead to better outcomes for students.
2. Our classification of reviews is fair and does not unduly discriminate or disadvantage specific groups of students.

Furthermore, our model will never remove reviews, it will be used for sorting on individual pages. This means it will not restrict speech but it may change initial impressions of courses.
