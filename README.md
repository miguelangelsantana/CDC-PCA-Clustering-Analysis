# Mental Illness, Aging and Self Reported Health in Baby Boomers
## Identifying Mental Health Trends in Aging Adults

Author: Miguel Angel Santana II

Blog Post: [Medium](https://miguelangelsantana.medium.com/mental-illness-aging-and-self-reported-health-in-baby-boomers-5b267a148bea)

### Introduction

The baby boomer generation (individuals 55-75 years old) is often under served as our society has become entangled with technology. Research illustrates an increase in diagnosis of depression and other mental illness in aging adults. Additional research on these trends is available via The Family Institute at [Northwestern.](https://counseling.northwestern.edu/blog/boom-in-aging-adults-could-overwhelm-mental-health-care-field/)

Due to COVID-19's effect on mental health around the world, it is especially important to understand what trends effect our elders in an attempt to work toward favorable living conditions for all. The Centers for Disease Control and Prevention released the following [Alzheimer's Disease and Healthy Aging Dataset.](https://catalog.data.gov/dataset/alzheimers-disease-and-healthy-aging-data)

Our analysis will look for commonalities across individuals based on ethnicity, age, gender and geographic region. While no definitive conclusions will be drawn due to limitations of the dataset, K-Means clustering algorithms will help identify highly related features and insight into baby boomers as they age in our society. 

## Methodology
The OSEMN framework was used to structure this analysis. Each step will be identified below:

* Obtain
* Scrub
* Explore
* Model
* Interpret

## Data (Obtain)
**Centers for Disease Control and Prevention [Alzheimer's Disease and Healthy Aging Data.](https://catalog.data.gov/dataset/alzheimers-disease-and-healthy-aging-data)**

## Scrub
### Simplify | Rename | Reduce

**Decisions:**

* Reducing the data set from 38 columns to 13 columns | addressing redundancies
* Renaming existing generic column labels
* Simplifying additional labels
* Carefully clarifying topic values due to length and complexity
	* The majority of the clustering analysis was done on these factors
* Filling null values with placeholders (to be dropped during analysis)
* Narrowing our dataset to values occuring in West Coast states
	* Arizona, California, Colorado, Nevada, Oregon, Washington

## Exploratory Data Analysis

**Overview of class/theme distributions on HQs**
![](/images/ClassDistribution.png)

### Overall (By State)

**General West Coast Obersvations**
![](/images/state.png)

Three key data stratifications exist: ethnicity, gender and age. 

### Ethnicity 

In the following illustration, all states (West Coast) and all ages were represented with the only stratification being ethnicity. 

![](/images/ethnicity.png)

Unfortunately, the last row of features includes several ethnicities that were not represented across each of the topics. Next, age and gender are considered.

### Age

The data frame was subdivided into age categories '50–64' and '65+'

![](/images/age.png)

### Gender

The data frame was subdivided into gender categories ‘Male’ and ‘Female’

![](/images/gender.png)

Health questionnaires report larger female values with respect to binge drinking, lifetime depression diagnosis, high blood pressure and issues with daily activities and a need for assistance as a result of self-reported decline in cognition. These factors are respective of all ages and ethnicities (in the data).

Our clustering analysis will continue using age as it showed the most variation amongst values per feature.  


## Modeling 

### Both Age Groups – 5 Clusters

Key Decisions: 
* dropna threshold of 24
* PCA, 3 components

![](/images/pca3.png)

**Optimal Clusters Per Elbow & Silhouette Scores**
![](/images/fiveclustercountplot.png)

**Cluster Distribution**
![](/images/threecluster50bar.png)

As we tried to profile and inspect the 5 clusters, we decided the data did not draw meaningful and interpretable trends. This is in addition to any effects that may exist as a result of filling nulls with mean values and using a groupby function with a mean aggregation in order to observe trends. Ultimately, we decided to move forward with a clustering analysis per age group.

## Model | Age 50-64

Key Decisions: 
* dropna (all nulls)
* PCA, 2 components

![](/images/multi5064.png)

Our multicollinearity plot for this age group reflects a significant positive correlation between lifetime diagnosis of depression and self-reported fair-poor health. The same plot illustrated a significant negative relationship between self-reported disability and self-reported good-excellent health. 

![](/images/threecluster50.png)

**Cluster Distribution**

![](/images/threecluster50bar.png)

**Cluster Profile & Inspection**

![](/images/threeclustermeans.png)

## Model | Age 65+

Multicollinearity in features for individuals over 65 years old

![](/images/multi65.png)

**Cluster Distribution**

![](/images/threecluster65.png)

**Cluster Distribution**

![](/images/threecluster65bar.png)

**Cluster Profile & Inspection**

![](/images/threeclustermeans65.png)

## Interpretations and Limitations

The CDC's Alzheimer's Disease and Healthy Aging data set illustrates strong relationships between features in individuals age 50–64 at the time of the health questionnaire.
The clustering analysis identified a single group with high scores across the majority of the features included. High scores were observed in categories: binge drinking (in the last month), lifetime depression diagnosis, 'fair-poor' self-reported health and no leisure (in the past month).

The study is limited due to missing data. Questionnaires were conducted in varying time periods and each questionnaire appeared to address different topics. Each ethnicity was not represented in all cases and this may be due to geographic region but no additional information is available to support this. 

Additionally, values were taken through self reporting and outside factors which may have occurred immediately prior to the assessment may have influenced the results.

### Future Work

Ultimately, the analysis shows a clear trend in baby boomers who are getting closer to retirement while living on the West Coast. Future work should include a larger variety of topics, ones that may infer social factors, family features, financial health and more. As the next generation of baby boomers age closer to retirement, it is our responsibility to create a cycle of care so that future generations can worry a little less when they prepare for retirement.

### For further information

Please review the narrative of my analysis in [my jupyter notebook.](./PCA_Clustering.ipynb)

For any additional questions, please reach out via email at santana2.miguel@gmail.com, on [LinkedIn](https://www.linkedin.com/in/miguel-angel-santana-ii-mba-51467276/) or on [Twitter.](https://twitter.com/msantana_ds)


##### Repository Structure:

```

├── README.md               <- The top-level README for reviewers of this project.
├── PCA_Clustering.ipynb     <- narrative documentation of analysis in jupyter notebook
├── presentation.pdf        <- pdf version of project presentation

```

