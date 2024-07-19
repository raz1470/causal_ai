# Causal AI
This project introduces Causal AI and how it can drive business value.

The code found in the notebooks folder was used to help write my series of articles on Towards Data Science:

- [Using causal graphs to answer causal questions](https://medium.com/towards-data-science/using-causal-graphs-to-answer-causal-questions-5fd1dd82fa90)
- [Making causal discovery work in real world business settings](https://medium.com/towards-data-science/making-causal-discovery-work-in-real-world-business-settings-80e80c5f66b8)
- [De-biasing treatment effects with double machine learning](https://medium.com/towards-data-science/de-biasing-treatment-effects-with-double-machine-learning-63b16fcb3e97)
- [Using double machine learning and linear programming to optimise treatment strategies](https://medium.com/towards-data-science/using-double-machine-learning-and-linear-programming-to-optimise-treatment-strategies-920c20a29553)
- [Optimising non-linear treatment effects in pricing and promotions](https://medium.com/towards-data-science/optimising-non-linear-treatment-effects-in-pricing-and-promotions-011ce140d180)
- [Measuring the intrinsic causal influence of your marketing campaigns](https://medium.com/towards-data-science/measuring-the-intrinsic-causal-influence-of-your-marketing-campaigns-aa8354c26b7b)
- [Validating the causal impact of the synthetic control method](https://medium.com/towards-data-science/validating-the-causal-impact-of-the-synthetic-control-method-2f3bf185f266)
- [Enhancing marketing mix modelling with causal ai](https://medium.com/towards-data-science/enhancing-marketing-mix-modelling-with-causal-ai-77f638bce3a9)
- [Safeguarding demand forecasting with causal graphs](https://medium.com/towards-data-science/safeguarding-demand-forecasting-with-causal-graphs-591511fc8e0e)

## Executive level pitch
"Predictive models can tell you which customers are likely to leave. But by then, it might be too late. Causal AI, on the other hand, identifies the root causes of churn. This insight allows you to address issues before they escalate, which will significantly improve customer retention"

## Technical term glossary
There is a sea of technical terms to get lost in… Below I have created a technical term glossary to help you swim:

| Term                                 | Definition |
|--------------------------------------|------------|
| ATE (average treatment effect)       | The average difference in the outcome between treated and untreated groups. |
| Backdoor criterion                   | A method for identifying and controlling for confounders to estimate the causal <br>effect, typically by blocking all backdoor paths. |
| CATE (conditional average treatment effect) | The ATE for specific subpopulations defined by certain characteristics. |
| Colliders                            | A variable that is influenced by two or more other variables in a causal graph. |
| Confounder/Confounding               | A variable that is related to both the treatment and the outcome, potentially<br> biasing the estimated effect of the treatment. |
| Confounding bias                     | The bias in the estimated treatment effect caused by the presence of confounders. |
| Conditional independence             | A situation where two variables are independent given the value of a third variable. |
| Counterfactuals                      | The hypothetical scenario representing what would have happened if the <br>treatment/intervention had not been applied. |
| DAG (directed acyclic graph)         | A graphical representation of a set of variables and their causal relationships,<br> depicted with directed edges and no cycles. |
| Experimental data                    | Data collected from a randomized experiment where the treatment is randomly assigned. |
| Frontdoor criterion                  | A method using a mediator to estimate the causal effect of a treatment on an outcome. |
| Heterogeneous treatment effects      | Variations in treatment effects across different subgroups within a population. |
| ITE (individual treatment effect)    | The effect of treatment on an individual entity. |
| IV (instrumental variable)           | A variable that affects the treatment but not the outcome directly, used to estimate<br> causal effects when there are confounders. |
| Mediators                            | A variable that lies on the causal path between the treatment and the outcome. |
| Observational data                   | Data collected without random assignment of the treatment. |
| Outcome                              | The metric we are trying to measure a change in as a result of an intervention. |
| Pearl's do-calculus                  | A set of rules developed by Judea Pearl to derive causal effects from observational<br> data using a DAG. |
| Propensity score                     | The probability of a unit receiving the treatment given its observed characteristics,<br> used to control for confounding in observational studies. |
| Randomized Controlled Trial (RCT)    | An experimental design where subjects are randomly assigned to treatment or control <br>groups to measure the effect of the treatment. |
| Selection bias                       | Bias that arises when the sample is not representative of the population,<br> affecting the validity of conclusions. |
| Spurious correlation                 | A correlation between two variables that is not due to any direct causal relationship. |
| Structural Equation Modeling (SEM)   | A statistical technique that allows for the modeling of complex relationships among<br> variables, including both direct and indirect effects. |
| Treatment/Intervention               | A change or action designed to affect the outcome. |
| Unconfoundedness                     | The assumption that all confounders have been identified and accounted for. |


## Business problem -> causal solution map
Trying to map business problems to causal solutions can easily become overwhelming… The following mapping will help you find your way:

```mermaid

flowchart LR
    A[Start] --> B1[I understand the
    cause but want to 
    estimate the effect]
    A --> B2[I want to
    understand
    multiple causes]
    B1 --> C1[I have customer
    level data]
    B1 --> C2[I have geographic
    level data]
    B2 --> C4[Causal
    discovery]
    B2 --> C5[I want to
    estimate multiple
    effects]
    C1 --> D1[I only need
    the overall
    effect]
    C1 --> D2[I need the
    customer
    level effect]
    C2 --> D3[I have one 
    control unit]
    C2 --> D4[I have multiple 
    control units]
    C2 --> D5[The treatment 
    was applied at a
    global level]
    D3 --> E1[Diff-in-Diffs]
    D4 --> E4[Synthetic
    Control]
    D5 --> E6[Interrupted
    Time-Series]
    C5 --> E2[Causal
    graphs]
    D1 --> F1[Double Machine
    Learning]
    D2 --> F2[Double Machine
    Learning]

    style C4 fill:#a3e635
    style E2 fill:#a3e635
    style E1 fill:#a3e635
    style F1 fill:#a3e635
    style F2 fill:#a3e635
    style E4 fill:#a3e635
    style E6 fill:#a3e635

```

It also helps to be familiar with what problems different departments face. Below I've highlighted some examples that Causal AI can help with:

- Acquisition: Marketing optimisation.
- Retention: CRM optimisation, promotion optimisation, pricing optimisation, understanding the causes of churn.
- Commercial: Why has a KPI dropped.
- Finance: What are the drivers of profit, what was the impact of a policy change.
- Customer services: What is driving customer service contacts, how effective are CS responses.
- Operations: Route cause analysis, process optimisation.

