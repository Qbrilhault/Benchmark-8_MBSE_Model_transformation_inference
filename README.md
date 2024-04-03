# Benchmark-8: MBSE Model transformation inference

The inference of model transformation has made significant strides thanks to recent progress in the fields of *machine learning* and *deep learning*. The proposed benchmark is dedicated to comparing and studying the performance of various approaches for automatically inferring a transformation model.

## Requirements

The inference of model transformation requires solving the *learning problem for transformation models*, which consists in the automatic derivation of transformation rules between two or more metamodels. The learning problem of the transformation model can be defined by the following equations $MT: M_s \rightarrow M_t$ where $𝑀𝑇$ is a learned transformation model  that takes a source model $𝑀_s$ as input and returns a target model $𝑀_t$. The $𝑀𝑇$ transformation model consists of transformation rules $𝑅$ that establish a mapping between $𝑀_s$ and $𝑀_t$ elements, such as $𝑀𝑇 = 𝑅_1◦𝑅_2◦...◦𝑅_n$. A rule specifies the transformation of a group of elements that correspond to a portion of the structure of the source metamodel (source pattern $P_s$) into a group of elements that correspond to a portion of the structure of the target metamodel (target pattern $P_t$). A rule can thus be described as $R: P_s \rightarrow P_t$.

## Glossary

* **Metamodel**: A metamodel is an abstract representation that defines the structure and terminology of concepts and relationships within a DSL (Domain-Specific Language);
* **Model** ($M$): A model instantiated from a metamodel is a concrete representation of a system or object, constructed based on the concepts defined within the metamodel. A model encapsulates certain properties and information of an object of the real world;
* **Model transformation**: Model transformations are employed to convert a source model $𝑀_s$ into a target model $𝑀_t$, typically for tasks such as translating between different domain-specific modeling languages;
* **Transformation model**: Transformation models define the rules necessary to convert elements in a source model into corresponding elements in a target model. These models are typically defined in a dedicated transformation language specifically designed to describe rules between different models;
* **Transformation pattern**: ransformation patterns are generic structures involved in model transformations. Each transformation rule can be described by a transformation pattern, consisting of a source pattern  $P_s$ (elements of the source metamodel) and a target pattern  $P_t$ (elements of the target metamodel).

## Object of study

Given the benchmark's particular emphasis on model transformation mechanisms within the context of Model-Driven Architecture (MDA), its main focus is on transformation models that encapsulate the transformation rules.

## Characteristics and behavior of the object of study

A common framework of understanding is needed to facilitate the comparison of approaches to learning transformation models in order to highlight their advantages and weaknesses. The characterization grids below can serve as a common framework for describing the transformation patterns present in the transformation model. Each transformation pattern can be characterized by various structural and terminological features. Characterizing transformation patterns is useful for several reasons:

* Gain a better understanding of the transformation patterns involved in model transformation;
* To compare the ability of the approaches to address specific types of transformation patterns;
* To compare approaches that may not necessarily rely on the same validation datasets.

Thanks to the characterization, two transformation models that share the same features regardless of the domain-specific metamodel are considered equivalent and can be compared in a benchmark study. A deeper understanding of the conflicts or "mismatches" to be resolved, which are caused by the heterogeneity of the metamodels is need to identify structural and terminological features.

### Structural features

<img src="images/Structural features.png" alt="structural_features" title="Structural features" style="width: 70%; height: auto;">

**Table 1: Structural features**

Some transformation patterns may be subject to conditions that can guide the transformation of a element or a group of elements. The transformation is thus based on the so-called concept-specific features. Three types of conditions have been identified: conditions for references, attributes and neighboring classes

<img src="images/Transformation conditions.png" alt="transformation_conditions" title="Transformation conditions" style="width: 70%; height: auto;">

**Table 2: Transformation conditions**

### Terminological features

<img src="images/Terminological features.png" alt="terminological_features" title="Terminological features" style="width: 50%; height: auto;">

**Table 3: Terminological features**

## Performances measurement

Performance criteria were established to measure the ability of the approaches to solve specific types of transformation patterns. The following performance criteria were used during the learning phase:

* Since the goal of a transformation model is to minimize the loss of information when transforming a model, metrics such as *recall* (R), *accuracy* (A) and *F-measure* were used to measure the validity of the models obtained after the transformation and to assess whether the transformation rules have been learned correctly during the learning phase. $A$ is the ratio between the number of expected generated elements and the total number of generated elements, and R the ratio between the expected number of generated elements and the total number of expected elements, such as:

$$F-measure=\frac{(1+\beta^2).A.R}{\beta^(2)*A+R} $$ 

* The human effort required to create and validate the resulting transformation models is quantified in terms of: (1) the required pre-processing, i.e. the number of models that need to be provided for optimal training, as well as the additional elements required such as pre-alignments; (2) the post-processing required to validate the obtained transformation rules;
* The training time required to learn the transformation rules is also measured.

## Datasets

Each of the datasets presented below can be used to evaluate the capability of approaches to tackle specific transformation patterns. Therefore, the selection of a dataset for validating an approach depends on the transformation patterns you intend to address. A dataset comprises several elements:

* Source and target metamodels;
* Source and target model instances;
* Transformation rules that convert any source model instance into a target model instance.

Datasets could be found into the folder ```datasets```. 

<table>
    <thead>
        <tr>
            <th align="center"></th>
            <th colspan="7" align="center">Structural features</th>
            <th colspan="4" align="center">Terminological features</th>
        </tr>
    </thead>
    <thead>
        <tr>
            <th align="center"></th>
            <th colspan="4" align="center">Transformation patterns</th>
            <th colspan="3" align="center">Transformation conditions</th>
            <th colspan="4" align="center"></th>
        </tr>
    </thead>
    <thead>
        <tr>
            <th align="center">Transformation</th>
            <th align="center">[1-1]</th>
            <th align="center">[1-n]</th>
            <th align="center">[n-1]</th>
            <th align="center">[n-m]</th>
            <th align="center">&sigma;<sub>c</sub></th>
            <th align="center">&sigma;<sub>a</sub></th>
            <th align="center">&sigma;<sub>r</sub></th>
            <th align="center">C</th>
            <th align="center">R</th>
            <th align="center">A</th>
            <th align="center">V</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="center"><em>Families2Persons [1]</em></td>
            <td align="center">-</td>
            <td align="center">-</td>
            <td align="center">(c2)</td>
            <td align="center">-</td>
            <td align="center">-</td>
            <td align="center">-</td>
            <td align="center">x</td>
            <td align="center">(e4)</td>
            <td align="center">(e4)</td>
            <td align="center">(e3)</td>
            <td align="center">-</td>
        </tr>
        <tr>
            <td align="center"><em>Class2Relational [2]</em></td>
            <td align="center">(c1)</td>
            <td align="center">(c5)</td>
            <td align="center">-</td>
            <td align="center">(c4;c6)</td>
            <td align="center">x</td>
            <td align="center">x</td>
            <td align="center">-</td>
            <td align="center">(e6)</td>
            <td align="center">(e6)</td>
            <td align="center">(e6)</td>
            <td align="center">(d2;d5)</td>
        </tr>
    </tbody>
</table>

**Table 4: Datasets features**

## Experimental collection

An experimental collection lists all approaches dedicated to the investigation of a problem. The following approaches will form part of the comparative study :

* Inductive Logic Programming (ILP) [3];
* Relational Concept Analysis (RCA) [4];
* Search-based approache [5, 6, 7, 8];
* LSTM encoder/decoder [9];
* Q-learning [10].

## Benchmarking

The aim of this comparative study is to measure and compare the performance of different learning approaches for transformation models for deriving functional transformation rules in order to identify weaknesses and optimization areas for future work. The Table 5 below provides a comprehensive summary. The synthesis of the results follows 4 levels of analysis:

* 0: the results are difficult to use or not clearly defined;
* 1: the results are usable, but calculations have been made;
* 2: the results were taken as they are presented in the article;
* 3: each of the algorithms was executed to obtain the results.

The datasets used to compare the approaches is the transformation *Class2Relational*.

<table>
    <thead>
        <tr>
            <th align="center">Approaches</th>
            <th align="center">Inputs</th>
            <th colspan="4" align="center">Learning performance</th>
            <th align="center">Transformation</th>
            <th align="center">level</th>
        </tr>
    </thead>
    <thead>
        <tr>
            <th align="center"></th>
            <th align="center"></th>
            <th align="center">Time (s)</th>
            <th align="center">A</th>
            <th align="center">R</th>
            <th align="center">F</th>
            <th align="center">F</th>
            <th align="center"></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th align="center">ILP [3]</th>
            <th align="center">M<sub>s</sub> + M<sub>t</sub> + P</th>
            <th align="center">?</th>
            <th align="center">?</th>
            <th align="center">?</th>
            <th align="center">?</th>
            <th align="center">?</th>
            <th align="center">0</th>
        </tr>
        <tr>
            <th align="center">RCA [4]</th>
            <th align="center">M<sub>s</sub> + M<sub>t</sub> + P</th>
            <th align="center">?</th>
            <th align="center">0.9</th>
            <th align="center">0.8</th>
            <th align="center">0.85</th>
            <th align="center">0.93</th>
            <th align="center">1</th>
        </tr>
        <tr>
            <th align="center">GA [5]</th>
            <th align="center">M<sub>s</sub> + M<sub>t</sub></th>
            <th align="center">?</th>
            <th align="center">0.75</th>
            <th align="center">?</th>
            <th align="center">?</th>
            <th align="center">?</th>
            <th align="center">2</th>
        </tr>
        <tr>
            <th align="center">GA [6]</th>
            <th align="center">M<sub>s</sub> + M<sub>t</sub></th>
            <th align="center">3600</th>
            <th align="center">?</th>
            <th align="center">1.0</th>
            <th align="center">?</th>
            <th align="center">1.0</th>
            <th align="center">2</th>
        </tr>
        <tr>
            <th align="center">PSO+SA [7]</th>
            <th align="center">M<sub>s</sub> + M<sub>t</sub> + P</th>
            <th align="center">20 to 50</th>
            <th align="center">?</th>
            <th align="center">0.93</th>
            <th align="center">?</th>
            <th align="center">?</th>
            <th align="center">2</th>
        </tr>
        <tr>
            <th align="center">GA [8]</th>
            <th align="center">M<sub>s</sub> + M<sub>t</sub> + P</th>
            <th align="center">?</th>
            <th align="center">0.94</th>
            <th align="center">0.94</th>
            <th align="center">0.94</th>
            <th align="center">0.94</th>
            <th align="center">2</th>
        </tr>
        <tr>
            <th align="center">LSTM encoder/decoder [9]</th>
            <th align="center"> 750 M<sub>s</sub> + 750 M<sub>t</sub></th>
            <th align="center">+4000</th>
            <th align="center">1.0</th>
            <th align="center">1.0</th>
            <th align="center">1.0</th>
            <th align="center">1.0</th>
            <th align="center">3</th>
        </tr>
        <tr>
            <th align="center">Q-learing [10]</th>
            <th align="center"> 1 M<sub>s</sub> + 1 M<sub>t</sub></th>
            <th align="center">2.11</th>
            <th align="center">1.0</th>
            <th align="center">1.0</th>
            <th align="center">1.0</th>
            <th align="center">1.0</th>
            <th align="center">3</th>
        </tr>
    </tbody>
</table>

**Table 5: Benchmark results for the *Class2Relational* transformation**

For each indicator, a "?" symbol means that the value could not be determined.

## References:

[1] Zoo ATL https://eclipse.dev/atl/atlTransformations/#Families2Persons

[2] Zoo ATL https://eclipse.dev/atl/atlTransformations/#Class2Relational

[3] Z. Balogh and D. Varró. Model transformation by example using inductive logic programming. *Software & Systems Modeling*, 2009.

[4] H. Saada, X. Dolques, M. Huchard, C. Nebut, and H. Sahraoui. Generation of operational transformation rules from examples of model transformations. *15th International Conference MODELS 2012*, Innsbruck, Austria, pages 546–561, 2012.

[5] M. Faunes, H. Sahraoui, and M. Boukadoum. Generating model transformation rules from examples using an evolutionary algorithm. *27th IEEE/ACM International Conference on Automated Software Engineering*, pages 250–253, 2012.

[6] M. Faunes, H. Sahraoui, and M. Boukadoum. Genetic-programming approach to learn model transformation rules from examples. *6th International Conference, ICMT 2013*, Budapest, Hungary, pages 17–32, 2013.

[7] M. Kessentini, H. Sahraoui, M. Boukadoum, and O. B. Omar. Search-based model transformation by example. *Software & Systems Modeling*, 2012.

[8] I. Baki and H. Sahraoui. Multi-step learning and adaptive search for learning complex model transformations from examples. *ACM Transactions on Software Engineering and Methodology (TOSEM)*, 2016.

[9] L. Burgueno, J. Cabot, S. Li, and S. Gérard. A generic lstm neural network architecture to infer heterogeneous model transformations. *Software and Systems Modeling*, 2022. Github : https://github.com/modelia/ai-for-model-manipulation

[10] Q. Brilhault, E. Yahia, L. Roucoules. La continuité numérique basée sur l'apprentissage de modèles de transformation: une approche d'interopérabilité dirigée par les modèles. Manuscrit de thèse, 2023. https://pastel.hal.science/tel-04511226

## Contributors 

Quentin Brilhault, Laboratory of Physical and Digital Systems Engineering (LISPEN), Arts et Métiers Institute of Technology

Esma Yahia, Laboratory of Physical and Digital Systems Engineering (LISPEN), Arts et Métiers Institute of Technology

Lionel Roucoules, Laboratory of Physical and Digital Systems Engineering (LISPEN), Arts et Métiers Institute of Technology
