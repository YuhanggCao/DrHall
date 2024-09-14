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
We've conducted experiments on the following datasets:
---

### TruthfulQA Dataset Overview

- **Purpose**: TruthfulQA is designed to evaluate the truthfulness of Large Language Models (LLMs) in generating answers to questions.
- **Composition**: The dataset contains 817 questions across 38 categories of potential falsehoods, such as misconceptions and fiction.
- **Truth Assessment**: Answers' truthfulness is judged using fine-tuned GPT-3-13B models, classifying each response as true or false.

### Pre-requisites for Using the TruthfulQA Dataset

Before utilizing the TruthfulQA dataset, certain preparatory steps are required:

1. **Model Fine-Tuning**:
   - Follow the guide on [Inference-Time Intervention: Eliciting Truthful Answers from a Language Model](https://github.com/likenneth/honest_llama#truthfulqa-evaluation) to create GPT-JUDGE, a fine-tuned GPT-3 model.

2. **Dataset Preparation:**
   - Run the `add_scores_to_truthful_qa.py` script to process the dataset. 
   - Make sure to update the `file_name` and `file_with_score` variables in the script with the correct file paths.

   Execute the following command in your terminal:
   ```bash
   python add_scores_to_truthful_qa.py
   ```

## RQ3

### **Model Abstraction**

The process of abstracting the behavior and properties of a system into a simplified representation that retains only the essential characteristics of the original system. In the context of this framework, model abstraction is done based on state and probabilistic models.

#### **1. ProbabilisticModel (from probabilistic_abstraction_model.py)**
- **Purpose**: Provides a base for creating probabilistic models based on abstracted states.
  
- **Usage Examples**:
  ```python
  # Initialize the ProbabilisticModel
  prob_model = ProbabilisticModel(args)
  
  # Evaluate LLM performance on a dataset task
  prob_model.eval_llm_performance_on_dataset_task()
  
  # Compose scores with ground truths
  prob_model.compose_scores_with_groundtruths_pair()
  ```

#### **2. AbstractStateExtraction (from state_abstraction_utils.py)**
- **Purpose**: Extracts abstract states from provided data instances.
  
- **Usage Examples**:
  ```python
  # Initialize the AbstractStateExtraction
  state_extractor = AbstractStateExtraction(args)
  
  # Perform PCA on data
  state_extractor.perform_pca()
  
  # (Additional method usage examples would be included if available in the file)
  ```

### **Metrics Calculation**

Metrics provide a quantitative measure to evaluate the performance and characteristics of models. In our framework, metrics evaluate the quality and behavior of abstracted models.

#### **1. MetricsAppEvalCollections (from metrics_appeval_collection.py)**
- **Purpose**: Acts as a central utility for metric evaluations based on state abstractions.
  
- **Usage Examples**:
  ```python
  # Initialize the MetricsAppEvalCollections
  metrics_evaluator = MetricsAppEvalCollections(args_obj1, args_obj2, train_data, val_data, test_data)
  
  # Retrieve evaluation results
  aucroc, accuracy, f1_score, _, _, _ = metrics_evaluator.get_eval_result()
  
  # Calculate the preciseness of predictions
  preciseness_mean, preciseness_max = metrics_evaluator.preciseness()
  ```
