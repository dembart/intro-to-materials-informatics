![logo](https://github.com/dembart/intro-to-materials-informatics/blob/14d74726229c09e0d0bba3b79135b94f94c2c5ec/figures/logo.png?raw=True)

## Содержание

* [О курсе](#о-курсе) 
* [Результаты обучения](#результаты-обучения)
* [(Примерное) расписание](#примерное-расписание)
* [Занятия](#занятия)
  * [№1: Что такое информатика материалов + ускоренный курс Python](#1)
  * [№2: Библиотеки Python для атомистического моделирования материалов](#2)
  * [№3: Данные в материаловедении](#3)
  * [№4: Анализ, визуализация и аппроксимация данных](#4)
  * [№5: Классическое машинное обучение в материаловедении, часть 1](#5)
  * [№6: Классическое машинное обучение в материаловедении, часть 2](#6)
  * [№7: Графовые нейронные сети в материаловедении, часть 1](#7)
  * [№8: Графовые нейронные сети в материаловедении, часть 2](#8)
  * [№9: Машинное обучение для молекулярного моделирования](#9)
  * [№10: Критический разбор научных статей](#10)
  * [№11: Работа над финальными проектами](#11)
  * [№12: Презентации финальных проектов](#12)
* [Критерии оценивания](#критерии-оценивания)
* [Пример финального проекта](#пример-финального-проекта)
* [Рекомендуемая литература](#рекомендуемая-литература)
* [Используемые данные](#данные)
* [Список ресурсов по информатике материалов](#список-ресурсов-по-информатике-материалов)
* [Инструкция по внедрению курса](#инструкция-по-внедрению-курса)
* [Авторы курса](#авторы-курса)




## О курсе

Курс представляет собой обзор методов, основанных на данных, для ускорения разработки и моделирования материалов и специализируется на вопросах атомистического моделирования неорганических соединений.
Каждая лекция — это краткий обзор с минимально необходимой теорией.
Основная часть курса — это семинары. В ходе курса мы:

* изучим библиотеки Python для атомистического моделирования материалов
* познакомимся с базами данных в материаловедении и научимся использовать API проекта Materials Project
* применим алгоритмы машинного обучения для предсказания свойств материалов
* выполним моделирование молекулярной динамики с использованием межатомных потенциалов на основе графовых нейронных сетей

В конце курса студенты защищают итоговый проект на выбранную тему.

## Результаты обучения

По завершении курса студент сможет:

* применять библиотеки Python и инструменты анализа данных для решения задач материаловедения
* критически оценивать научную литературу по информатике материалов
* собирать, генерировать и анализировать датасеты для материаловедения, включая выявление связей «структура — свойство»


## Предварительные требования

* Базовые знания Python (numpy, pandas), линейной алгебры; знания кристаллохимии будут плюсом
* Ноутбук


## (Примерное) расписание

<details>
<summary>Нажмите, чтобы открыть</summary>

* Неделя №1 (легко/средне)

  * Что такое информатика материалов?
  * Python для атомистического моделирования материалов
  * Данные в материаловедении

* Неделя №2 (средне)

  * Разведочный анализ данных
  * Классическое машинное обучение в материаловедении, часть 1
  * Классическое машинное обучение в материаловедении, часть 2

* Неделя №3 (сложно)

  * Графовые нейронные сети в материаловедении, часть 1
  * Графовые нейронные сети в материаловедении, часть 2
  * Машинное обучение для молекулярного моделирования

* Неделя №4 (легко/средне)

  * Работа над финальными проектами на занятиях
  * Критический анализ научных статей
  * Презентации финальных проектов

</details>


## Занятия

Каждое занятие состоит из относительно короткой лекции и относительно длинного (кодинг) семинара. Все материалы курса хранятся в папках [lectures](lectures) и [seminars](seminars). 



| Занятие | Лекция | Семинар | Домашнее задание | Дополнительные материалы |
|------|----------|----------|----------|-------|
|<a id="1">1</a>. <br> (Дата: 29 сент.)| [Лекция 1](lectures/lecture01_Intro+Navigation.pdf)<br> План: Обзор информатики материалов. Мотивация, навигация. Цели и результаты обучения (ILO) и критерии оценивания. Описание ДЗ и финального проекта (FP).| [Семинар 1](seminars/seminar01_Python_Crash_Course.ipynb)<br>[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1z_0vCAGwOFTLK9lRdvaLrDVcFt2_Fv_e?usp=sharing#sandboxMode=true&scrollTo=ILePI3Ul3p--)<br>План: Google Colab, повторение основных библиотек, используемых в науке: numpy, pandas, scipy, matplotlib.| ДЗ 1 <br> План: Основы Python, numpy, pandas, scipy, matplotlib. Python для атомистического моделирования. API The Materials project <br>Дедлайн: 10 окт., 2026, 15:59 MSK |   |
|<a id="2">2</a> <br> (Дата: 1 окт.)| [Лекция 2](lectures/lecture02_Python_for_materials_modeling.pdf) <br> План: Python в материаловедении.|[Семинар 2](seminars/seminar02_Intro_to_ASE_and_Pymatgen.ipynb)<br>[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1NIAJ0uAaJjjL2s2cJwcEaLctOLj6onPE?usp=sharing#sandboxMode=true) <br> План: Библиотеки Python ASE и Pymatgen. Молекулы и кристаллы. Различные текстовые форматы представления материалов. Локальное окружение атомов в материале, построение списка ближайших соседей, разбиение Вороного, трансляционная симметрия.|       |  [ASE: советы и приемы](https://wiki.fysik.dtu.dk/ase/tips.html), [Туториалы по Pymatgen](https://github.com/materialsvirtuallab/matgenb/tree/master/notebooks) |
|<a id="3">3</a> <br> (Дата: 3 окт.)| [Лекция 3](lectures/lecture03_Data_in_materials_science.pdf) <br> План: Данные в материаловедении. Принципы FAIR. The Materials Project и его API.|[Семинар 3](seminars/seminar03_The_Materials_Project_API.ipynb) <br>[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1JgRRgGUu4cSuvTpKHWsyGfXdGpApTzdW?usp=sharing#sandboxMode=true)<br> План: API The Materials Project, фазовые диаграммы в Pymatgen.|       |  [Статья: FAIR](https://www.nature.com/articles/sdata201618), [Статья: MP](https://pubs.aip.org/aip/apm/article/1/1/011002/119685/Commentary-The-Materials-Project-A-materials), [MP API: Начало работы](https://docs.materialsproject.org/downloading-data/using-the-api/getting-started) |
|<a id="4">4</a> <br> (Дата: 6 окт.)| [Лекция 4](lectures/lecture04_Exploratory_data_analysis.pdf) <br> План: Разведочный анализ данных.|[Семинар 4](seminars/seminar04_EDA.ipynb)<br>[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1JgrOxXotEr2JOEma0N-ByqkfmF0JMMqH?usp=sharing#sandboxMode=true)<br> План: scipy, matplotlib, pandas, EDA|       |  [Лекция из курса CS 109a Павлоса Протопапаса и Кевина Радера](https://harvard-iacs.github.io/2018-CS109A/lectures/lecture-3/presentation/lecture3.pdf)    |
|<a id="5">5</a> <br> (Дата: 8 окт.)| [Лекция 5](lectures/lecture05_ML_for_material_science_pt1.pdf) <br> План: Машинное обучение для материаловедения. Типы задач. Свойство и дескриптор. Линейная регрессия. Функция потерь. Градиентный спуск. |[Семинар 5](seminars/seminar05_Regression.ipynb) <br>[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1c9l0gS-77rC9AvW_na-CWLjN17oY_gec?usp=sharing#sandboxMode=true) <br> План: библиотека Python scikit-learn, регрессионные модели для свойств материалов. Разбор ДЗ 1.|ДЗ 2 <br> План: sklearn, регрессия, предсказание твердости, важность признаков и отбор признаков, моделирование молекулярной динамики с использованием универсальных межатомных потенциалов. <br> Дедлайн: 21 окт., 2026, 15:59 MSK<br>Анонс финального проекта (FP).<br> Дедлайн: 25 окт., 2026, 23:59 MSK|  [Статья](https://www.nature.com/articles/s41524-019-0221-0#Abs1)   |
|<a id="6">6</a> <br> (Дата: 10 окт.)| [Лекция 6](lectures/lecture06_ML_for_material_science_pt2.pdf) <br> План: Дизайн дескрипторов (признаков) в материаловедении. Геометрические и композиционные признаки. Иерархия дескрипторов кристаллической структуры. Fingerprint кристаллической структуры. Важность признаков |[Семинар 6](seminars/seminar06_Features.ipynb)<br>[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1d6VQD2filrmfSVQkxtwxzz9pUitYmNPT?usp=sharing#sandboxMode=true) <br> План: Важность признаков, библиотека Python matminer.|    |  [Статья](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.96.024104)   |
|<a id="7">7</a> <br> (Дата: 13 окт.)| [Лекция 7](lectures/lecture07_Intro_to_Neural_Networks.pdf) <br> План: Логистическая регрессия. Нейронные сети. Обратное распространение ошибки. |[Семинар 7](seminars/seminar07_LogReg_and_MLP.ipynb) <br>[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Uehvz49TcowVQSsgvyfN4B3pLCtHLatJ?usp=sharing#sandboxMode=true)<br> План: Введение в PyTorch, цикл обучения, классификация металл/изолятор  |ДЗ 3 <br>План: Обзор статьи <br> Дедлайн: XX окт., 2026, 15:59 MSK  |     |
|<a id="8">8</a> <br> (Дата: 15 окт.)| [Лекция 8](lectures/lecture08_Graph_Neural_Networks.pdf) <br> План: Графовое представление материалов. Сверточные нейронные сети на графах кристаллов (CGCNN). Как работать с периодичностью. Передача сообщений (message passing). Инвариантность.|[Семинар 8](seminars/seminar08_Reproduce_CGCNN.ipynb) <br>[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1URYmhHonq9WS3ESbwjUcNSiWiEQPfXwq?usp=sharing#sandboxMode=true)<br> План: torch, pytorch_geometric, предсказание энергии образования.|    |  [Статья: CGCNN](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.120.145301)|
|<a id="9">9</a> <br> (Дата: 17 окт.)| [Лекция 9](lectures/lecture09_ML_for_molecular_simulation.pdf) <br> План: Машинное обучение для молекулярного моделирования. Межатомный потенциал. Энергия и силы. Молекулярная динамика с использованием GNN. Универсальные потенциалы.|[Семинар 9](seminars/seminar09_MLMD.ipynb)  <br>[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1QUUjuRUliSl_CFRyG9gXzqJ85xRbtdhY?usp=sharing#sandboxMode=true)<br> План: Универсальные потенциалы для моделирования молекулярной динамики диффузии ионов Li в Li3PS4. Разбор ДЗ 2.|| [Статья](https://arxiv.org/abs/2308.06462) <br> [Статья](https://pubs.acs.org/doi/10.1021/acs.jctc.4c00190)    |
|<a id="10">10</a> <br> (Дата: 20 окт.)| Лекция 10 <br> План: Студенты представляют свои критические обзоры статей по информатике материалов (устные презентации)|Семинар 10 <br> План: Продолжение лекции|    |     |[Статья](https://www.nature.com/articles/s41467-022-29939-5)   |
|<a id="11">11</a> <br> (Дата: 22 окт.)| Лекция 11 <br> План: Подведение итогов курса. Советы по выполнению финального проекта. Формулировка проблемы. Сбор/анализ данных. Разделение данных. Проектирование признаков. Выбор модели. Анализ результатов. Распространенные ошибки, хорошие и плохие практики применения машинного обучения в материаловедении.|Семинар 11 <br> План: Работа над финальными проектами|    |     |
|<a id="12">12</a> <br> (Дата: 24 окт.)| Лекция 12 <br> План: Презентации финальных проектов|Семинар 12 <br> План: Презентации финальных проектов|    |     |


### Критерии оценивания
* Посещаемость    0%
* Квизы            10%
* Домашние задания 45%
* Финальный проект 35%
  * * Письменный отчет 50%
  * * Устная презентация 40-50%
  * * Обсуждение других проектов 0-10%
* Рецензии студентов 10%

Мы оцениваем следующие аспекты финальных проектов студентов:  
- Ясность выступления, слайдов и отчета  
- Качество графиков и рисунков  
- Описание решаемой задачи и мотивация
- Анализ полученных результатов  
- Понимание использованных методов  
- Адекватность выбранных методов  
- Соответствие между полученными результатами, выводами и исходной задачей  

## Пример финального проекта

<details>
<summary> Пример </summary>

Задача: провести «небольшой» высокопроизводительный скрининг твердотельных электролитов для литий-ионных аккумуляторов, с использованием методов и инструментов, изученных на курсе (или выходящих за рамки курса).  

* Определить химическое пространство поиска.
* Сформулировать критерии отбора для высокопроизводительного скрининга твердотельных электролитов для твердотельных литий-ионных аккумуляторов.  
* Скачать данные из базы Materials Project согласно выбранным критериям.  
* Разработать модель для предсказания ширины запрещённой зоны выбранных материалов.
* Разработать модель для предсказания параметров литий ионной проводимости.
* Выбрать один из наиболее перспективных материалов и выполнить моделирование диффузии с использованием выбранного универсального межатомного потенциала.  
* Рассчитать барьер активации подвижного иона и его коэффициент диффузии.  
* Сравнить выбранный материал с существующими альтернативами.  
* Написать отчёт в стиле статьи на 3–5 страниц, включающий:  
  * Введение  
  * Методы  
  * Результаты  
  * Обсуждение  
  * Заключение  
  * Список литературы  
* Подготовить устную презентацию на 7 минут  

</details>

### Рекомендуемая литература
- **Книги**  
    - *Materials Informatics and Catalysts Informatics: An Introduction*, Keisuke Takahashi, Lauren Takahashi, 2026, ISBN-10: 981970216X  
    - *Deep Learning*, Ian Goodfellow, Yoshua Bengio, Aaron Courville, 2016, MIT Press, [deeplearningbook.org](https://www.deeplearningbook.org/)  

- **Статьи**  
    - Recent advances and applications of machine learning in solid-state materials science, Schmidt, J., Marques, M.R.G., Botti, S. et al., npj Comput Mater 5, 83 (2019). [https://doi.org/10.1038/s41524-019-0221-0](https://doi.org/10.1038/s41524-019-0221-0)  

### Данные
<details>
<summary>Данные, используемые для семинаров и домашних заданий</summary>

|Название      |Описание |Источник     |
|--------------|--------|------------|
|[Набор данных проводимости Li-ионов](data/seminar04/LiIonDatabase_poisoned.csv) |Набор данных экспериментально измеренной литий-ионной проводимости в кристаллических (и аморфных) керамиках. Данные включают семейство кристаллической структуры, химический состав, предсказываемое свойство, температуру измерений и источник данных. Данные содержат None и выбросы. Задача студентов — очистить набор данных и провести разведочный анализ данных.| Hargreaves, C.J., Gaultois, M.W., Daniels, L.M. и др. A database of experimentally measured lithium solid electrolyte conductivities evaluated with machine learning. npj Comput Mater 9, 9 (2023). https://doi.org/10.1038/s41524-022-00951-z |
|[Набор данных ширины запрещённой зоны Materials Project](data/seminar04/mp_eg_data.csv) |Набор данных значений ширины запрещённой зоны, рассчитанных с помощью теории функционала плотности для кристаллических структур. Задача студентов — провести разведочный анализ данных и найти корреляцию между шириной запрещённой зоны и средней электроотрицательностью структуры.| Для получения данных использовался API [The Materials Project](https://next-gen.materialsproject.org/). |
|[Набор данных ширины запрещённой зоны двойных перовскитов](data/seminar05/eg_double_perovskites.csv) |Набор данных содержит целевые значения ширины запрещённой зоны, рассчитанные с помощью теории функционала плотности, а также элементные и геометрические дескрипторы кристаллических структур. Задача студентов — провести разведочный анализ данных, найти корреляции между целевым свойством и дескрипторами, оптимизировать гиперпараметры регрессионных моделей, провести отбор признаков и анализ важности признаков.| Talapatra, A., Uberuaga, B.P., Stanek, C.R. и др. Band gap predictions of double perovskite oxides using machine learning. Commun Mater 4, 46 (2023). https://doi.org/10.1038/s43246-023-00373-4 |
|[Набор данных твердости](data/hw2/train.dat) |Набор данных экспериментально измеренной твердости материалов. Используется для ДЗ2.| Tantardini, Christian, et al. "Material hardness descriptor derived by symbolic regression." Journal of Computational Science 82 (2026): 10240, [репозиторий](https://github.com/AlexanderKvashnin/SISSO_hardness/blob/main/train.dat) |

</details>


### Список ресурсов по информатике материалов

#### Базы данных
- [База данных Materials Project](https://next-gen.materialsproject.org/)  
Самая популярная база данных кристаллических структур и их свойств, рассчитанных с помощью теории функционала плотности (DFT).

- [AFLOW](https://www.aflowlib.org/)  
База данных материалов и их свойств, рассчитанных с помощью DFT.

- [OQMD](https://oqmd.org/)  
База данных термодинамических и структурных свойств материалов, рассчитанных с помощью DFT.

#### Наборы данных

- [Набор данных по полимерам](https://datadryad.org/stash/dataset/doi:10.5061/dryad.5ht3n)  
Структуры, энергии атомизации, ширины запрещённой зоны и диэлектрические константы 1000 полимеров.

- [твердость SISSO](https://github.com/AlexanderKvashnin/SISSO_hardness/blob/main/train.dat)  
Набор данных экспериментально измеренной твердости 61 материала.

- [QM9](https://springernature.figshare.com/collections/Quantum_chemistry_structures_and_properties_of_134_kilo_molecules/978904/4)  
Свойства, рассчитанные с помощью DFT, для 134 тыс. стабильных малых органических молекул, состоящих из C, H, O, N, F.

- [Литий-ионная проводимость](https://pcwww.liv.ac.uk/~msd30/lmds/LiIonDatabase.html)  
Экспериментально измеренный набор данных Li+ проводимости для 2000 твердых материалов.

- [Набор данных по ширине запрещённой зоны двойных перовскитов](https://www.nature.com/articles/s43246-023-00373-4#MOESM4)  
Набор данных ширины запрещённой зоны для 5000 двойных перовскитов, рассчитанных с помощью DFT.

#### Курируемые списки
- [Awesome Materials Informatics](https://github.com/tilde-lab/awesome-materials-informatics?tab=readme-ov-file)  
Список известных проектов в области информатики материалов.

- [Geometric GNNs](https://github.com/AlexDuvalinho/geometric-gnns)  
Список геометрических графовых нейронных сетей для атомистического моделирования.

- [Best of Atomistic Machine Learning](https://github.com/JuDFTteam/best-of-atomistic-machine-learning?tab=readme-ov-file#datasets)  
Список open-source проектов, сгруппированных по категориям.

- [Neural Network Models for Chemistry](https://github.com/Eipgen/Neural-Network-Models-for-Chemistry/tree/main)  
Коллекция моделей нейронных сетей для химии.

#### Программное обеспечение

- [ASE](https://wiki.fysik.dtu.dk/ase/)  
Python-библиотека для настройки, управления и анализа атомистических симуляций.

- [Pymatgen](https://pymatgen.org/)  
Python-библиотека для анализа атомных структур.

- [matminer](https://hackingmaterials.lbl.gov/matminer/)  
Python-библиотека для майнинга свойств материалов.

- [DScribe](https://singroup.github.io/dscribe/latest/)  
Python-пакет для построения дескрипторов атомных структур.

- [TorchSISSO](https://github.com/PaulsonLab/TorchSISSO)  
Реализация на PyTorch алгоритма SISSO (Sure Independence Screening and Sparsifying Operator).

#### Учебные материалы
- [Pymatgen tutorials](https://github.com/materialsvirtuallab/matgenb/tree/master/notebooks)  
Различные уроки по использованию Pymatgen для атомистического моделирования и пост-обработки DFT вычислений.

- [Примеры Matminer](https://github.com/hackingmaterials/matminer_examples/tree/main/matminer_examples)  
Уроки по использованию Matminer для кодирования атомных структур (генерация дескрипторов структуры).

#### Универсальные межатомные потенциалы

- [SevenNet](https://github.com/MDIL-SNU/SevenNet)  
- [MACE_MP](https://github.com/ACEsuit/mace-mp)  
- [CHGNet](https://chgnet.lbl.gov/)  
- [M3GNet](https://matgl.ai/#m3gnet) 
- [UPET](https://github.com/lab-cosmo/upet)


## Инструкция по внедрению курса

<details>
<summary>Нажмите, чтобы открыть</summary>

- Курс рассчитан на 10–20 человек. Оптимальный формат — лекция (15–30 минут) + семинар (120 минут).

- Для закрепления материала рекомендуется в начале каждого занятия проводить квиз на 5–7 вопросов по теме предыдущего занятия.

- При выполнении заданий и расчетов в Google Colab курс не требует установки дополнительных пакетов или сред.

- Для локального запуска необходимо скопировать репозиторий и запускать Jupyter-ноутбуки в любом удобном IDE, предварительно установив требуемые библиотеки Python.

Для проведения вычислительных экспериментов в рамках курса можно использовать Yandex DataSphere — облачную среду для ML-разработки с поддержкой Jupyter-ноутбуков и доступом к GPU. Для образовательных проектов Yandex Cloud предоставляет гранты, покрывающие стоимость вычислительных ресурсов.

Подать заявку на грант: yandex.cloud/ru/research-education-program

> В заявке укажите, что грант запрашивается для ведения университетского курса, приведите количество студентов и ожидаемый объём вычислений студентами.

</details>


### Авторы курса

Курс разработан Артемом Дембицким под руководством Дмитрия Аксенова в Сколковском институте науки и технологий.