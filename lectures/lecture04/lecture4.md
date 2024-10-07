---
marp: true
theme: default
#class: invert
paginate: true
size: 16:9
style: |
  img {background-color: transparent!important;}
  a:hover, a:active, a:focus {text-decoration: none;}
  header a {color: #ffffff !important; font-size: 100 px;}
  footer {color: grey; font-size: 100 px;}
header: 'Lecture 4: Exploratory data analysis '
---
## Lecture #4: Exploratory data analysis (EDA)

<footer>Slides by <a href="https://github.com/dembart">Artem Dembitskiy</a></footer>


---
### Previously on

- Python for atomistic modeling
  - ASE's Atoms and Pymatgen's Structure
  - Neighbor list
  - Voronoi partitioning
- Data in materials informatics
  - Computational data
  - The Materials project API

---
### Goals/Agenda

- Explain why visualizing data is important when analyzing data
- Provide tips on how to use visualization to explore data

---

### Attribution

- Parts of these slides are adopted from the excellent lecture on exploratory data analsysis from the course CS 109A: Introduction to Data Science by Pavlos Protopapas & Kevin Rader shared under MIT licence

  - https://harvard-iacs.github.io/2018-CS109A/lectures/lecture-3/presentation/lecture3.pdf

- Consider the following materials your reading homework
---
### The data science workflow

![bg right:60% 90%](figures/datascience_workflow.png)


<footer>From CS 109a: Data Science,
Effective Exploratory Data
Analysis and Visualization by Pavlos Protopapas & Kevin Rader<a href="https://harvard-iacs.github.io/2018-CS109A/lectures/lecture-3/presentation/lecture3.pdf"> slide #2</a></footer>

---
### Descriptive statistics 

"...is a summary statistic that quantitatively describes or summarizes features from a collection of information"

https://en.wikipedia.org/wiki/Descriptive_statistics


---
### Sample size

Number of observations in a dataset (study)

```python
len(data)
```

---

### Mean
<style scoped>section{font-size:24px;}</style>

```python
np.mean(data)
```

![bg right:50% 80%](https://wikimedia.org/api/rest_v1/media/math/render/svg/4e3313161244f8ab61d897fb6e5fbf6647e1d5f5)

---
<style scoped>section{font-size:24px;}</style>

### Median

```python
np.median(data)
```


"The median of a set of numbers is the value separating the higher half from the lower half of a data sample, a population, or a probability distribution."

![bg right:50% 80%](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cf/Finding_the_median.png/1920px-Finding_the_median.png)


---
<style scoped>section{font-size:24px;}</style>

### Standard deviation

"...is a measure of the amount of variation of the values of a variable about its mean."

![bg right:50% 90%](https://wikimedia.org/api/rest_v1/media/math/render/svg/98f02417b7c2830d941364f6b40e22ea63a9dd1f)

---
<style scoped>section{font-size:24px;}</style>

### Correlation coefficient

[The Pearson correlation coefficient](https://en.wikipedia.org/wiki/"Pearson_correlation_coefficient) measures the linear relationship between two datasets. Like other correlation coefficients, this one varies between -1 and +1 with 0 implying no correlation."

[scipy docs](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.pearsonr.html#r8c6348c62346-1)


![bg right:60% 100%](figures/pearson.png)

---
### Descriptive statistics of band gap (Eg) distribution in the Materials Project

- Sample size
  - 103,217
- Mean of Eg
  - 0.79
- Standard deviation of Eg:  
  - 1.37

---
### Is it what you expected?
- What's wrong with this distribution?
![bg right:50% 100%](figures/eg_fake_distribution.png)

---
### Any ideas?
- Sample size
  - 103,217
- Median of Eg: 
  - 0.0 <--- ???

---
### This is the real distribution

-  Metals have a zero Eg
![bg right:50% 100%](figures/eg_distribution.png)

> Median(Eg) = 0.0 says that metals represent at least half of the sample
---
### Why is visual inspection of data important?

- Same descriptive statistics
- Very different distributions


https://en.wikipedia.org/wiki/Anscombe%27s_quartet

![bg right:50% 100%](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ec/Anscombe%27s_quartet_3.svg/638px-Anscombe%27s_quartet_3.svg.png)

---
### Visulaization goals

<style scoped>section{font-size:24px;}</style>


Communicate (Explanatory)
- Present data and ideas
- Explain and inform
- Provide evidence and support
- Influence and persuade

Analyze (Exploratory)
- Explore the data
- Assess a situation
- Determine how to proceed
- Decide what to do


<footer> From CS 109a: Data Science,
Effective Exploratory Data
Analysis and Visualization by Pavlos Protopapas & Kevin Rader<a href="https://harvard-iacs.github.io/2018-CS109A/lectures/lecture-3/presentation/lecture3.pdf"> slide #23</a></footer>

---
<style scoped>section{font-size:24px;}</style>

### Communicate 

![bg:](figures/medvedev2017.png)

<footer>Density functional theory is straying from the path toward<a href="https://www.science.org/doi/10.1126/science.aah5975"> the exact functional</a></footer>


---
### Explore
<style scoped>section{font-size:24px;}</style>


![bg 60%](figures/maltsev2023.png)

<footer>Order–Disorder Phase Transition and Ionic Conductivity in a<a href="https://pubs.acs.org/doi/10.1021/acsami.3c07242"> Li2B12H12 Solid Electrolyte</a></footer>

---


### Exploratory data analysis pipeline

- Build data 
- Clean data
- Explore global features
- Explore group features
---

### Build (read) data in a structured format 
  - Pandas DataFrame
  - One row per variable

```python
df = pd.read_csv('eg_data.csv')
```
---

### Clean the data
  - outliers
  - NaNs (missing values)
  - constant rows
  - duplicates
```python
df.dropna()
```
- plus visual support: histogram, box plot

--- 

### Study the global summary statistics
```python
df.describe()
```

```python
df.aggregate(
                {
                "column_name": ["min", "max", "median", "skew"]
                }
)
```
- plus visual support: histogram, scatter plot, bar plot
---

### Study the summary statistics of the subgroups

```python
df[["bandgap, chemsys"]].groupby("chemsys").mean()
```
- plus visual support: histogram, scatter plot, bar plot

---

## Some principles for effective EDA

---
### Avoid misleading graphs

- Do not distort scales
- Do not truncate graph when comparing the data
  -  or indicate the truncation
- Avoid 3D charts
- Do not change y(or x)-axis maximum 
- Aspect ratio determines the perception of steepness in [slope](https://graphworkflow.com/enhancement/aspect/)
  - be proportional

Have a look at this page: https://en.wikipedia.org/wiki/Misleading_graph

---
<style scoped>section{font-size:24px;}</style>
### Lie factor

![bg right:70% 100%](figures/lie_factor.png)

---
<style scoped>section{font-size:20px;}</style>

### Use the right display 

![bg right:78% 100%](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh3nVdA7gB1FN5DSm56f1j3Xto1gwkKOQREgJYFiIlV00RpZGReq9C9TfSoubkq77fFWic2xHrUxgV87V5UxwKbXXT8FzKhYQVyyLvwCkwYpd2u776hZsCEWGpemrOINGGEz5TpwvIUWoY/w2400/)

---

### Correlations

- scatter plot, correlation matrix

![bg right:70% 90%](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41467-023-40669-0/MediaObjects/41467_2023_40669_Fig6_HTML.png?as=webp)

**Is it a good graph? Why?**

<footer>Design principles for NASICON  <a href="https://www.nature.com/articles/s41467-023-40669-0"> super-ionic conductors</a></footer>

---
### Distribution

- histogram, density plot

**Is it a good graph? Why?**

![bg right:50% 100%](figures/eg_distribution.png)


---
### Comparison

- bar plot, box plot

**Is it a good graph? Why?**


![bg right:60% 100%](figures/eg_family_barplot.png)

---
### Box plot
![bg right:60% 80%](https://upload.wikimedia.org/wikipedia/commons/thumb/1/1a/Boxplot_vs_PDF.svg/1024px-Boxplot_vs_PDF.svg.png)

---

# Don't use pie charts

Barplots are easier to compare

![bg right:50% 100%](https://images.theconversation.com/files/556773/original/file-20231031-25-9vdsm4.png?ixlib=rb-4.1.0&q=30&auto=format&w=600&h=430&fit=crop&dpr=2)



<footer>Here’s why you should (almost) never use a pie chart <a href="https://theconversation.com/heres-why-you-should-almost-never-use-a-pie-chart-for-your-data-214576"> for your data</a></footer>



---
<style scoped>section{font-size:22px;}</style>

### Use color

![bg right:60% 100%](https://blog.datawrapper.de/wp-content/uploads/2021/01/Artboard-89-copy-20.png)

Have a look at this page: https://blog.datawrapper.de/colors/

---
<style scoped>section{font-size:22px;}</style>

### But consider a better alternative if possible

- the simpler the better

![bg right:50% 100%](https://blog.datawrapper.de/wp-content/uploads/2021/01/rule7.png)

Have a look at this page: https://blog.datawrapper.de/colors/

---
<style scoped>section{font-size:20px;}</style>
#### My favorite

![bg right:68% 100%](figures/dont.png)

<footer>From CS 109a: Data Science,
Effective Exploratory Data
Analysis and Visualization by Pavlos Protopapas & Kevin Rader<a href="https://harvard-iacs.github.io/2018-CS109A/lectures/lecture-3/presentation/lecture3.pdf"> slide #55</a></footer>

---

### Take home message

- Visualizing data helps you
  - Present data and ideas
  - Analyze results
  - Define future steps

- The data is more important than the design
  - Represent the data in a right way
  - Avoid misleading graphs

---
### Resources:

https://harvard-iacs.github.io/2018-CS109A/lectures/lecture-3/presentation/lecture3.pdf

https://en.wikipedia.org/wiki/Misleading_graph

https://en.wikipedia.org/wiki/Anscombe%27s_quartet

https://blog.datawrapper.de/colors/


---

# Thank you for your attention!





