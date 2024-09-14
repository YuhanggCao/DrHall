#  Detecting and Reducing the Factual Hallucinations of Large Language Models with Metamorphic Testing

Question answering (QA) is a fundamental task of a large language model (LLM), which requires LLM to automatically answer human-posed questions in natural language. However, LLMs are known to distort facts and make non-factual statements (hallucination) when dealing with QA tasks, which may affect the deployment of LLMs in real-life situations. In this work, we present DrHall, a method for the detection of factual errors in black-box large language models inspired by metamorphosis testing in software testing. We believe that the model's hallucination answer is unstable. It is easier to produce different answers to the hallucination by using metamorphic relation (MR) to make the model take different execution paths for re-execution. We empirically evaluate DrHall on three datasets covering natural and code language data, finding that it outperforms existing methods and baselines, often by a large gap. In addition, by transforming DrHall using diverse path sampling, we obtain error correction methods with higher success rates. Our results demonstrate the potential of using MR to mitigate LLM hallucination.

## Table of Contents

- [RQ1](#RQ1)
- [RQ2](#RQ2)
- [RQ3](#RQ3)

## RQ1

### FactHalluQA Dataset Overview

- **Purpose**: FactHalluQA is designed to assess the hallucination in the Large Language Model (LLM) while mitigating the potential influence of benchmark leakage on the assessment process.
- **Composition**: The dataset consists of more than eight hundred questions in English, divided on the basis of disciplines, covering questions on physics, chemistry, biology, geography, history, literature, and so on.
- **Path**: The dataset is stored in this repository in the ```./RQ1/FactHalluQA``` path.


### **Data Examples**
We show some data examples of HalluQA here.
![](img/examples.png)

---


## RQ2
We present DrHall, a method for the detection of factual errors in black-box large language models inspired by metamorphic testing in software testing.
### Requirements


### Folder Structure


### Usage


## RQ3
By transforming DrHall using diverse path sampling, we obtain error correction methods with higher success rates. Our results demonstrate the potential of using MR to mitigate LLM hallucination.

### Requirements


### Folder Structure


### Usage


