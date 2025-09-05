---

### 📝 **Mitigating uncertainty in data-driven marketing: Operational learning pipeline**

---

### 📝 **Mitigating uncertainty in data-driven marketing: Operational learning pipeline**

### **Project Overview**

This project focuses on the automatic classification of social media posts and groups from "VKontakte" to identify marketing-oriented content. It compares the performance of classic neural network architectures (CNN, LSTM, GRU) against fine-tuned Large Language Models (LLMs) for these classification tasks. The main goal is to determine the most effective approach for automated lead generation and analysis of a potential client base on social media.

This repository contains the code and resources for the research paper, providing a comprehensive framework for reproducing the study's findings and building upon them.

### **⚠️ Prerequisites**

- VK API Token: To run the data collection scripts (notebooks/Get_Data.ipynb), you must obtain a VKontakte API access token.
    
- GPU Requirements: To run the notebooks involving Large Language Models (Classification_Posts_LLM.ipynb and Selecting_Target_Groups_LLM.ipynb), a GPU with at least 16 GB of VRAM is required.
    

### **Project Structure**

```
├── data/
│   ├── vk_groups_dataset.xlsx
│   └── vk_posts_dataset.xlsx
├── notebooks/
│   ├── classification_posts/
│   │   ├── Classification_Posts.ipynb
│   │   └── Classification_Posts_LLM.ipynb
│   └── classification_groups/
│   │   ├── Selecting_Target_Groups.ipynb
│   │   └── Selecting_Target_Groups_LLM.ipynb
│   └── Get_Data.ipynb
├── README.md
└── requirements.txt
```

### **Datasets**

The repository contains two main datasets for different classification tasks.

#### **`vk_groups_dataset.xlsx`**

This dataset is used for classifying VK groups. It is a xlsx file with the following columns:

|   |   |   |
|---|---|---|
|**Column Name**|**Description**|**Data Type**|
|`ID_группы`|Unique identifier for the VK group.|Integer|
|`Название`|The name of the VK group.|String|
|`ID_города`|Unique identifier for the city.|Integer|
|`Город`|The name of the city where the group is based.|String|
|`Описание`|The description of the VK group.|String|
|`Признак`|The target label for binary classification (e.g., `1` for target, `0` for non-target).|Integer|

#### **`vk_posts_dataset.xlsx`**

This dataset, with approximately 2500 entries, is used for classifying posts. The structure is designed for a **multi-class classification** task.

|   |   |   |
|---|---|---|
|**Column Name**|**Description**|**Data Type**|
|`text`|The text of the social media post.|String|
|`class`|The target label for multi-class classification. For example, `1` might represent a 'promotion' and `2` a 'giveaway'.|Integer|

### **Installation**

To set up the environment and run the notebooks, it is recommended to use a virtual environment.

**Install all required dependencies** using the `requirements.txt` file:

```
pip install -r requirements.txt
```

### **Notebooks Description**

Each directory within the `notebooks/` folder contains Jupyter notebooks designed for specific tasks.

- Get_Data.ipynb: A utility script for collecting public data about groups and their posts from the VK API.
    

#### **`classification_posts/`**

- Classification_Posts.ipynb: This notebook trains and evaluates classic neural network models (CNN, LSTM, GRU) for multi-class post classification (e.g., "discount," "gift," "delivery info").
    
- Classification_Posts_LLM.ipynb: This notebook demonstrates fine-tuning a Large Language Model (LLM) using the Unsloth library for the same post classification task.
    

#### **`classification_groups/`**

- Selecting_Target_Groups.ipynb: This notebook trains and evaluates classic neural network models (CNN, LSTM, GRU) for the binary classification task of identifying whether a group belongs to the "food delivery" sector.
    
- `Selecting_Target_Groups_LLM.ipynb`: This notebook demonstrates fine-tuning an LLM using the **Unsloth** library to perform binary classification on VK groups based on their name and description.