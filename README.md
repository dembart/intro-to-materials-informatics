## Introduction to Materials Informatics


## Contents
- [About](#about)
- [Timeline](#timeline-and-location)
- [Schedule](#approximate-schedule)
- [Classes](#classes)
    - [Class #1: What is materials informatics + Python crash course](#1)
    - [Class #2: Python libraries for atomistic modelling of materials](#2)
    - [Class #3: Data in materials science](#3)
    - [Class #4: Data exploration, visualization, and fitting](#4)
    - [Class #5: Classical ML for materials science pt.1](#5)
    - [Class #6: Classical ML for materials science pt.2](#6)
    - [Class #7: Graph neural networks for materials science pt.1](#7)
    - [Class #8: Graph neural networks for materials science pt.2](#8)
    - [Class #9: Machine learning for molecular simulation](#9)
    - [Class #10: Working on final projects in class](#10)
    - [Class #11: Selected topics in materials informatics](#11)
    - [Class #12: Final project presentations](#12)
- [Intended Learning Outcomes](#intended-learning-outcomes)
- [Course prerequisites](#course-prerequisites)

- [Course navigation](#course-navigation)
- [Assessment criteria](#assessment-criteria)
- [Final project description](#approximate-final-project-description)
- [References](#references-materials-inspiration)
- [Data](#data)
 

## About

The course is an overview of data-driven techniques for accelerating materials design with a focus on the atomistic scale and inorganic compounds. In general, each lecture is a short overview + minimum required theory. The seminars are the main part of the course. During the course we will: learn Python libraries for atomistic materials modelling, get an overview of materials science databases and learn how to use the Materials project API, apply machine learning algorithms to predict materials properties, and perform molecular dynamics simulations with deep learning interatomic potentials. 

It is expected that students will better understand the concepts through learning by doing. At the end of the course, students will present a final project in the form of an article based on the homework they have completed.

## Timeline and location

Term 1B, Sept. 30 - Oct. 25, MON THU FRI 16:00-19:00 


## (Approximate) Schedule: 

* Week #1 (easy)
    * What is materials informatics? 
    * Python for atomistic modeling of materials
    * Data in materials science
* Week #2 (medium)
    * Exploratory data analysis
    * Classical ML for materials science pt.1
    * Classical ML for materials science pt.2
* Week #3 (hard)
    * Graph neural networks for materials science pt.1
    * Graph neural networks for materials science pt.2
    * Machine learning for molecular simulation
* Week #4 (easy)
    * Working on final projects in class
    * Selected topics of materials informatics
    * Final projects presentation



## Classes

The format of each class is the relatively short lecture plus the relatively long (coding) seminar. All class materials are stored in the [lectures](lectures) and [seminars](seminars) folders. Each class begins with "Previously on...", "Class Goals" and "Agenda" and ends with a "Take Home Message".


| Class | Lecture | Seminar | Homework | Supplementary materials |
|------|----------|----------|----------|-------|
|<a id="1">1</a>. <br> (Date: Sep. 30)| Lecture 1<br> Agenda: Materials informatics overview. Motivation, navigation. ILOs and assessment. HWs and FP description.|Seminar 1<br> Agenda: Google Colab, reminder of the key libraries used in science: numpy, pandas, scipy, matplotlib.| HW1 <br> Agenda: Python basics, numpy, pandas, scipy, matplotlib. Python for atomistic modeling. The Materials project API <br>Deadline: Oct., 10, 2024, 15:59 MSK |   |
|<a id="2">2</a> <br> (Date: Oct. 3)| Lecture 2 <br> Agenda: Python in materials science.|Seminar 2 <br> Agenda: The ase and pymatgen python libraries. Molecules and crystals. Various text formats of a material representation. Local coordination, nearest neighbors list building, Voronoi partitioning, symmetry.|       |       |
|<a id="3">3</a> <br> (Date: Oct. 4)| Lecture 3 <br> Agenda: Data in materials science. FAIR principles. The Materials Project and its API.|Seminar 3 <br> Agenda: Screening of solid-state electrolytes using The Materials Project's API and pymatgen.|       |     |
|<a id="4">4</a> <br> (Date: Oct. 7)| Lecture 4 <br> Agenda: Data exploration, fitting, and visualization. Assessing the fit. Metrics. Overfitting.|Seminar 4 <br> Agenda: scipy, matplotlib.|       |     |
|<a id="5">5</a> <br> (Date: Oct. 10)| Lecture 5 <br> Agenda: ML for materials science. Types of tasks. Property and descriptor. |Seminar 5 <br> Agenda: scikit-learn python library, regression models for predicting mechanical and thermodynamic properties of materials. HW1 review.|HW2 <br> Agenda: sklearn, regression, band gap prediction, feature importances and feature selection.<br> Deadline: Oct., 18, 2024, 15:59 MSK<br>FP announcement<br>[Agenda](#approximate-final-project-description).  <br> Deadline: Oct., 25, 2024, 23:59 MSK|     |
|<a id="6">6</a> <br> (Date: Oct. 11)| Lecture 6 <br> Agenda:  Feature design in materials science. Geometrical and compositional features. Hierarchy of the crystal structure descriptors. Crystal structure fingerprint. Feature importance|Seminar 6 <br> Agenda: matminer and dscribe python libraries. Reproduce an article on feature design.|    |     |
|<a id="7">7</a> <br> (Date: Oct. 14)| Lecture 7 <br> Agenda: Artificial neural networks. Loss function. Backpropagation.  Graph representation of materials. How to deal with periodicity. Crystal Graph Convolutional Neural Networks (CGCNN).  Message passing.|Seminar 7 <br> Agenda: github, CGCNN for predicting formation energy of crystals.|    |     |
|<a id="8">8</a> <br> (Date: Oct. 17)| Lecture 8 <br> Agenda: Invariance and Equivariance. E(3)-equivariant graph neural networks|Seminar 8 <br> Agenda: torch, training loop, NequIP - E(3)-equivariant graph neural network|    |     |
|<a id="9">9</a> <br> (Date: Oct. 18)| Lecture 9 <br> Agenda: Machine learning for molecular simulation. Interatomic potential. Energy and forces. Molecular dynamics employing GNNs. Active learning. Foundation models.|Seminar 9 <br> Agenda: M3GNet model for molecular dynamics simulation of Li-ion diffusion in Li3PS4.  HW2 review.|HW3 <br>Agenda: Band gap prediction with GNN, molecular dynamics simulation using universal interatomic potentials <br> Deadline: Oct., 24, 2024, 15:59 MSK|     |
|<a id="10">10</a> <br> (Date: Oct. 21)| Lecture 10 <br> Agenda: The course wrap up. Tips to complete a final project. Formulation of the problem. Data collection/analysis. Data splitting. Feature design. Model selection. Bias/Overfitting. Common practices of a model assessment. Results analysis. Common mistakes, good and bad practices in employing ML for materials science.|Seminar 10 <br> Agenda: Working on final projects|    |     |
|<a id="11">11</a> <br> (Date: Oct. 24)| Lecture 11 <br> Agenda: Several selected but not covered in seminars topics in materials informatics will be discussed (or invited speaker)|Seminar 11 <br> Agenda: Continuation of the lecture|    |     |
|<a id="12">12</a> <br> (Date: Oct. 25)| Lecture 12 <br> Agenda: Final projects presentations|Seminar 12 <br> Agenda: Final projects presentation|    |     |


## Intended learning outcomes
On completion of the course you will be able to:

- Apply python libraries and data science tools to solve materials science problems

- Critically evaluate materials informatics literature

- Collect, generate and analyse materials science datasets, including identification of structure-property relationships




## Course prerequisites
* computational materials science track
* basic knowledge of materials modeling, python (numpy, pandas), crystal chemistry, linear algebra
* laptop


## Course navigation

This github repo contains most of the course content. Quizzes and homeworks will be announced separately in the canvas and the telegram chat.

## Assessment criteria
* Attendance    0%
* Quizzes       10% 
* HW            45%
* Final project 35%
* * Written report 50%
* * Oral presentation 40-50%
* * Discussion of other projects 0-10%
* Peer reviews  10 %


## (Example) Final project description
The task is to carry out a 'small' high throughput screening of solid state electrolytes conducting a given ion (Li+, Na+, K+ etc) using data driven techniques and tools covered (or beyond) during the course.

* Given a set of chemical elements
* Formulate selection criteria for high-throughput screening of solid-state electrolytes for all-solid-state Li-ion batteries.
* Download the data from the Materials Project database according to the formulated criteria.
* Calculate the band gap of the selected materials (assuming that you do not have this data deposited at the Materials Project) using at least one classical ML and GNN model and evaluate their performance. For ML model calculate crystal structure descriptors using your own featurizer or open-source tools. Perform feature importance study.
* Select one of the most promising materials and perform a diffusion simulation using your favourite universal interatomic potential.
* Calculate the activation barrier of the mobile ion and its diffusion coefficient
* Compare your materials with existing alternatives
* Write a 3 page article style report including
    * Introduction
    * Methods
    * Results
    * Discussion
    * Conclusion
    * Bibliography
* Prepare a 5 minutes oral presentation



### Data

Data used during the seminars

|Name      |Description |Source     |
|----------|------------|-----------|
|          |            |           |




### References | Materials | Inspiration
[Mark Asta and Enze Chen](https://enze-chen.github.io/mi-book-2021/intro.html)  
[Taylor Sparks](https://github.com/sp8rks/MaterialsInformatics/tree/main)  
[Edward Kim](https://github.com/eddotman/intro-to-materials-informatics)


