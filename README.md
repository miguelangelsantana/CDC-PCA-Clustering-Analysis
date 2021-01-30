# Incomplete / Pending

# Mental Illness, Aging and Self Reported Health in Baby Boomers
## Identifying Mental Health Trends in Aging Adults

Author: Miguel Angel Santana II

Blog Post: **[HERE]**

### Abstract
**[HERE]**

### Introduction

The baby boomer generation (individuals 55-75 years old) is often under served as our society has become entangled with technology. Research illustrates an increase in diagnosis of depression and other mental illness in aging adults. Additional research on these trends is available via The Family Institute at [Northwestern.](https://counseling.northwestern.edu/blog/boom-in-aging-adults-could-overwhelm-mental-health-care-field/)

Due to COVID-19's effect on mental health around the world, it is especially important to understand what trends effect our elders in an attempt to work toward favorable living conditions for all. The Centers for Disease Control and Prevention released the following [Alzheimer's Disease and Healthy Aging Dataset.](https://catalog.data.gov/dataset/alzheimers-disease-and-healthy-aging-data)

Our analysis will look for commonalities across individuals based on ethnicity, age, gender and geographic region. While no definitive conclusions will be drawn due to limitations of the dataset, K-Means clustering algorithms will help identify highly related features and insight into baby boomers as they age in our society. 

## Methodology
The OSEMN Process was used throughout this project. Each step will be identified below:

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

![](/images/ClassDistribution.png)

Three key data stratifications exist: ethnicity, gender and age. 

### Ethnicity 

![](/images/ethnicity.png)

### Age

![](/images/age.png)

### Gender

![](/images/gender.png)

## Modeling 

### Both Age Groups – 5 Clusters

![](/images/pca3.png)

![](/images/fiveclustercountplot.png)

![](/images/threecluster50bar.png)

## Model | Age 50-64

![](/images/multi5064.png)

![](/images/threecluster50.png)

![](/images/threecluster50bar.png)

![](/images/threeclustermeans.png)

## Model | Age 65+

![](/images/multi65.png)

![](/images/threecluster65.png)

![](/images/threecluster65bar.png)

![](/images/threeclustermeans65.png)

## Interpretations and Limitations

### For further information

Please review the narrative of my analysis in [my jupyter notebook](./PCA_Clustering.ipynb) or review my [presentation](./presentation.pdf).

For any additional questions, please reach out via email at santana2.miguel@gmail.com, on [LinkedIn](https://www.linkedin.com/in/miguel-angel-santana-ii-mba-51467276/) or on [Twitter.](https://twitter.com/msantana_ds)


##### Repository Structure:

```

├── README.md               <- The top-level README for reviewers of this project.
├── PCA_Clustering.ipynb     <- narrative documentation of analysis in jupyter notebook
├── presentation.pdf        <- pdf version of project presentation

```

