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
header: 'Lecture 6: Machine learning for materials sience pt. 2'
---

## Lecture #6: Atomic structures encoding

<footer>Slides by <a href="https://github.com/dembart">Artem Dembitskiy</a></footer>

---
<style scoped>section{font-size:24px;}</style>

### Previously on

- Supervised machine learning 
- Ridge regression
- Random forest
---
<style scoped>section{font-size:24px;}</style>
### Goals/Agenda

- Heirarchy of crystal/molecular structure descriptors

- Feature importance

- Crystal structure fingerprints


---

![bg center: 80%](https://ars.els-cdn.com/content/image/1-s2.0-S0010465519303042-gr1_lrg.jpg)

---

<style scoped>section{font-size:22px;}</style>

### Features
- In classical ML we use features
- to represent materials in a machine-readable format

- Think of it like a fingerprint

![bg right:70% 100%](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41524-017-0056-5/MediaObjects/41524_2017_56_Fig2_HTML.jpg?as=webp)


<footer>Machine learning in materials informatics: 
 <a href="https://www.nature.com/articles/s41524-017-0056-5">recent applications and prospects </a></footer>



---
<style scoped>section{font-size:26px;}</style>
The better you find this representation for a particular problem, the better your model fits the data.

---

## Geometrical and compositional encoding of atomic structure



---
<style scoped>section{font-size:22px;}</style>


### Heirarchy of features
Depending on the resolution we have: 

- Local descriptors
  - site
- Fragment descriptors
  - bond
  - polyhedron
- Global descriptors
  - chemical family
  - structural type
  - density

![bg right:60% 90%](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fncomms15679/MediaObjects/41467_2017_Article_BFncomms15679_Fig1_HTML.jpg?as=webp)

<footer>Universal fragment descriptors for predicting properties of  <a href="https://www.nature.com/articles/ncomms15679">inorganic crystals </a></footer>


---

<style scoped>section{font-size:22px;}</style>


### Geometrical (Structural) features

- Atomic packing (e.g. volume per atom, density)

- Voronoi polyhedra features
  - area, volume, face distance, solid angle
- bond distance/angle

**Can be calculated for sublattices**

**Min/max/mean statistics**

![bg right:50% 100%](https://www.researchgate.net/publication/366457335/figure/fig5/AS:11431281208402314@1701392346180/The-schematic-diagram-of-Voronoi-polyhedrons-for-common-crystal-structure-a-BCC-b_W640.jpg)


<footer>Image <a href="https://www.researchgate.net/publication/366457335_Atomic_structure_of_intermetallic_compound_Nb5Si3_by_new_cluster_transformation_analysis_method">source </a></footer>

---
<style scoped>section{font-size:22px;}</style>



#### Voronoi polehdra features can be collected by pymatgen's methodology

```python
from pymatgen.analysis.local_env import VoronoiNN

features = VoronoiNN().get_voronoi_polyhedra(structure, site_id)
```

---
<style scoped>section{font-size:22px;}</style>

### Compositional (elemental/atomic) features

Aggregation over
- Atomic numbers
- Valence electrons
- Covalent radii
- Atomic fraction of each element in a composition
- Stoichiometry related
- Electron affinity
- Ionic radii
- Oxidation states
- Electronegativity
- ...

![bg right:60% 100%](https://github.com/enze-chen/mi-book/blob/master/assets/fig/week_1/04/magpie_features.png?raw=1)


<footer>Image 
 <a href="https://colab.research.google.com/github/enze-chen/mi-book/blob/master/week_2/08/matminer_features_blank.ipynb#scrollTo=e7a14866">source </a></footer>


---
<style scoped>section{font-size:22px;}</style>

### Atomic structure fingerprints
(not taught in the course)

- Atom-centered Symmetry Functions
- Smooth overlap of atomic positions
- Many-body tensor representations
- Pair distribution function
- X-ray diffraction pattern



![bg right:50% 90%](https://ars.els-cdn.com/content/image/1-s2.0-S0010465519303042-gr3_lrg.jpg)



---


### Feature engineering

- Primary descriptors are used to design more complex features

- e.g. by applying set of mathematical operators

See SISSO [paper](https://arxiv.org/abs/1710.03319)

![bg right:60% 100%](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41524-017-0056-5/MediaObjects/41524_2017_56_Fig3_HTML.jpg?as=webp)



<footer>Machine learning in materials informatics: 
 <a href="https://www.nature.com/articles/s41524-017-0056-5">recent applications and prospects </a></footer>

<style scoped>section{font-size:24px;}</style>

---
<style scoped>section{font-size:24px;}</style>

### Pros

- Better performance compared to primary descriptors

### Cons

- Increased computational complexity

- Garbage feature needs to be filtered

- Lack of interpretability

---
<style scoped>section{font-size:24px;}</style>

### Permutation feature importance

**We want to know which features most influence model prediction**

Given dataset {$X, y$}
- Fit the model
- Get scores
- Randomly shuffle one of the feature vectors $x_i$
- Refit model 
- Get scores
- The higher degradation of the model performance the more important the feature


<footer>Permutation importance <a href="https://scikit-learn.org/1.5/modules/permutation_importance.html">in sklearn </a></footer>




---
![bg center: 80%](https://scikit-learn.org/1.5/_images/permuted_predictive_feature.png)

---

![bg center: 80%](https://scikit-learn.org/1.5/_images/permuted_non_predictive_feature.png)

---
<style scoped>section{font-size:24px;}</style>

### Pros

- Works for any model
- Yields variance of the feature importance

### Cons

  - Computational complexity
    - Requires refitting the model for each feature
  - Wrong output for correlated features 

---
<style scoped>section{font-size:24px;}</style>

### Intuition behind the impurity-based feature importance

Decision tree: 

- Selects the best feature for splitting at each node

- Best split is measured by gain in purity (Gini impurity or Entropy)

- The higher gain the higher importance of the feature

In the case of Random Forest the feature importances are "computed as the mean and standard deviation of accumulation of the impurity decrease within each tree."

![bg right:50% 100%](https://scikit-learn.org/stable/_images/sphx_glr_plot_forest_importances_001.png)


<footer>Feature importances with a forest of trees<a href="https://scikit-learn.org/stable/auto_examples/ensemble/plot_forest_importances.html">in sklearn </a></footer>

---


### Pros

- You have this information after fitting the model
- Yields variance of the feature importance

### Cons

- Wrong output for high-cardinality features 




<style scoped>section{font-size:24px;}</style>
---

<style scoped>section{font-size:24px;}</style>

### Feature selection

- Drop features with low variance
- Backward/Forward feature selection
- LASSO
- Tree-based feature selection

### Why?
- Remove redundant features
- Develop robust model
- The less features the less compute is needed
- Feature collection = time = money
  - save your resources

---

<style scoped>section{font-size:22px;}</style>

### Forward feature selection algorithm

![bg right:70% 100%](https://editor.analyticsvidhya.com/uploads/243325.png)




<footer>Image <a href="https://www.analyticsvidhya.com/blog/2022/11/feature-selection-101-the-manual-for-beginners/">source </a></footer>


---
<style scoped>section{font-size:22px;}</style>

### How to collect features? 

Design your own Featurizer
  - You are an expert in your field
  - Consider essential descriptors of your target
  - Use pymatgen/ase/etc. 

Ready-to-use Featurizers
  - [Matminer](https://hackingmaterials.lbl.gov/matminer/) Python Library
  - [Dscribe](https://singroup.github.io/dscribe/latest/) Python library

Gross level features
  - Generate gross level features non-specific to your task
  - Select the best candidates

![bg right:55% 100%](https://hackingmaterials.lbl.gov/matminer/_images/featurizer_diagram.png)

---
<style scoped>section{font-size:22px;}</style>

### The most important properties of an ideal descriptor:

- Invariant with respect translation of the coordinate system

- Invariant with respect to rotation of the coordinate system

- Invariant with respect to permutation of atomic indices: changing the enumeration of atoms does not affect the target

- Unique: single way to construct a descriptor and the descriptor itself corresponds to a single property

- Continuous: small changes in the atomic structure -> small changes in the descriptor

- Compact

- Computationally cheap

From [DScribe: Library of descriptors for machine learning in materials science](https://www.sciencedirect.com/science/article/pii/S0010465519303042?via%3Dihub) by Lauri Himanen at al. (Computer Physics Communications, 2020)

---
<style scoped>section{font-size:20px;}</style>

### Which features to consider?

- What accuracy do I need? 
- At which scale your property is defined?
  - Site (i.e. defect formation energy)
  - Bond (i.e. migration barrier)
  - Structure (i.e. hardness)
- Size of the chemical space?
  - Several elements or the whole periodic table
- Diversity of crystal structures? 
  - Fixed structural type? Not fixed?

- Do we know (expect) any relashionship?
- How many samples do I have?
  - ~100? ~100,000?

---

### You can find the right feature design by answering these questions

---

### Example

![bg right:70% 100%](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs43246-023-00373-4/MediaObjects/43246_2023_373_Fig1_HTML.png?as=webp)


---
### Considered features

![bg right:55% 100%](figures/eg_double_perovskite%20_features.png)

---
<style scoped>section{font-size:20px;}</style>

### Features for Eg prediction
![bg right:75% 90%](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs43246-023-00373-4/MediaObjects/43246_2023_373_Fig4_HTML.png?as=webp)

<footer>Band gap predictions of double perovskite oxides using<a href="https://www.nature.com/articles/s43246-023-00373-4#MOESM4"> machine learning </a></footer>

---


# Thank you for your attention!

