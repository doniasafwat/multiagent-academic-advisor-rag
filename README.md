# 🎓 Multi-Agent Academic Advisor

An AI-powered academic course advisor that combines Large Language Models (LLMs), Retrieval-Augmented Generation (RAG), semantic search, and course recommendation to help users find relevant online courses based on their preferences.

---

## 📌 Project Overview

This project implements an intelligent academic course advisory system that understands natural-language course requests, retrieves relevant courses from a dataset, and generates recommendations and answers using an LLM.

The system works with the Udemy Courses Dataset and uses course information such as:

- Course title
- Category
- Topic
- Language
- Price
- Course duration
- Course description

The goal is to provide users with a more natural and intelligent way to search for and receive recommendations for online courses.

---

## ✨ Features

- 🗣️ Natural-language course requests
- 🔍 Semantic course search
- 🧠 Large Language Model-based responses
- 📚 Retrieval-Augmented Generation (RAG)
- 🎯 Course recommendation
- 💬 Course-related Q&A
- 💰 Price-based filtering
- 🌍 Language-based filtering
- ⏱️ Course duration filtering
- 🏷️ Category and topic filtering
- 👍 User feedback component
- 🖥️ Interactive Gradio interface

---

## 🧠 System Architecture

The overall workflow is:

**User Query → Input Understanding → Course Retrieval → Recommendation / Q&A → Response**

The system consists of several main components:

### 1. Input Agent

The Input Agent processes the user's natural-language request and extracts useful filters, including:

- Category
- Topic
- Language
- Maximum price
- Maximum course duration

For example, a user can provide a request such as:

> "I want a business course under $30 in English."

The agent analyzes the request and extracts the relevant constraints.

---

### 2. Course Data Processing

The system preprocesses the course dataset by:

- Handling missing values
- Removing duplicate records
- Cleaning column names
- Converting numerical fields
- Creating a combined course description

The processed course information is then used for retrieval and recommendation.

---

### 3. Semantic Search

Course information is transformed into vector embeddings using **Sentence Transformers**.

These embeddings represent the semantic meaning of the course information and allow the system to retrieve courses that are relevant to the user's query.

---

### 4. FAISS Retrieval

**FAISS** is used to perform similarity search over the generated embeddings.

The system retrieves the most relevant courses based on the similarity between the user's query and the available course information.

---

### 5. LLM-Based Q&A

The retrieved course information is provided to a Large Language Model.

The LLM uses the retrieved information to generate responses and answer course-related questions.

---

### 6. Course Recommendation

The recommendation component uses the user's requirements together with the retrieved course information to generate relevant course recommendations.

---

### 7. Feedback Component

A feedback component is included to capture user feedback about the generated recommendations and responses.

---

### 8. Gradio Interface

A **Gradio** interface provides an interactive way for users to communicate with the academic advisor.

Users can enter their course requirements and receive recommendations or answers through the interface.

---

## 🔎 Retrieval-Augmented Generation (RAG)

The project uses a Retrieval-Augmented Generation approach.

The RAG pipeline follows these steps:

1. Receive the user's natural-language query.
2. Process the query.
3. Convert course information into vector embeddings.
4. Perform similarity search using FAISS.
5. Retrieve the most relevant courses.
6. Provide the retrieved information to the LLM.
7. Generate a response based on the retrieved course data.

This approach allows the generated response to be grounded in the available course information.

---

## 🤖 AI Components

The project combines several AI techniques:

| Component | Purpose |
|---|---|
| Input Agent | Understands user requirements |
| Sentence Transformers | Generates semantic embeddings |
| FAISS | Performs similarity-based retrieval |
| LLM | Generates natural-language responses |
| Recommendation Component | Suggests relevant courses |
| Feedback Component | Collects user feedback |
| Gradio | Provides the interactive interface |

---

## 🛠️ Technologies

### Programming Language

- Python

### Data Processing

- Pandas
- NumPy

### Natural Language Processing & LLMs

- Transformers
- Large Language Models (LLMs)
- Sentence Transformers

### Retrieval

- FAISS
- Vector Embeddings
- Semantic Search
- Retrieval-Augmented Generation (RAG)

### User Interface

- Gradio

---

## 📊 Dataset

This project uses the **Udemy Courses Dataset (2022)**.

The notebook uses:

**`Course_info.csv`**

The dataset contains information about Udemy courses, including course titles, categories, topics, languages, prices, and course duration.

### Dataset Source

The dataset is available on Kaggle:

https://www.kaggle.com/datasets/hossaingh/udemy-courses

### Dataset Setup

The dataset is **not included in this repository**.

After downloading the dataset, place `Course_info.csv` in the same directory as the notebook.

```text
multiagent-academic-advisor-rag/
│
├── multiagent-academic-advisor-rag.ipynb
└── Course_info.csv
```

---

## 🚀 How to Run

### 1. Download the Repository

Download or clone this repository to your local machine.

### 2. Download the Dataset

Download the Udemy Courses Dataset from Kaggle:

https://www.kaggle.com/datasets/hossaingh/udemy-courses

### 3. Add the Dataset

Place the following file in the project directory:

```text
Course_info.csv
```

### 4. Install Dependencies

Install the required Python packages listed in `requirements.txt`.

```bash
pip install -r requirements.txt
```

### 5. Open the Notebook

Open:

```text
multiagent-academic-advisor-rag.ipynb
```

using Jupyter Notebook, JupyterLab, Google Colab, or VS Code.

### 6. Run the Notebook

Run the notebook cells in order.

### 7. Launch the Interface

After running the required cells, launch the Gradio interface and interact with the academic advisor.

---

## 📁 Project Structure

```text
multiagent-academic-advisor-rag/
│
├── multiagent-academic-advisor-rag.ipynb
│
├── README.md
│
├── requirements.txt
│
└── .gitignore
```

### Dataset

`Course_info.csv` is intentionally not included in the repository and should be downloaded separately from Kaggle.

---

## 🎯 Key Concepts Demonstrated

This project demonstrates practical implementation of:

- Natural Language Processing
- Large Language Models
- AI Agents
- Semantic Search
- Vector Embeddings
- Retrieval-Augmented Generation
- FAISS Similarity Search
- Course Recommendation
- Question Answering
- Data Preprocessing
- Interactive AI Applications

---

## 🔄 End-to-End Workflow

```text
                    User Query
                         │
                         ▼
                ┌─────────────────┐
                │   Input Agent   │
                └────────┬────────┘
                         │
                         ▼
                Extract User Filters
                         │
                         ▼
                ┌─────────────────┐
                │ Semantic Search  │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │      FAISS      │
                │    Retrieval    │
                └────────┬────────┘
                         │
                         ▼
              Relevant Course Data
                         │
                         ▼
                ┌─────────────────┐
                │       LLM       │
                └────────┬────────┘
                         │
                         ▼
             Recommendation / Q&A
                         │
                         ▼
                ┌─────────────────┐
                │ Gradio Interface│
                └─────────────────┘
```

---

## 💡 Example Queries

The system can process natural-language requests such as:

```text
I want a business course under $30 in English.
```

or:

```text
Show me data science courses in Arabic under 2 hours.
```

The Input Agent extracts relevant constraints from the request and uses them as part of the retrieval and recommendation process.

---

## 🔐 Security & Data Privacy

No authentication tokens, API keys, passwords, or other sensitive credentials are included in this repository.

The dataset is also excluded from the repository and must be downloaded separately.

---

## 🔮 Future Improvements

Possible future improvements include:

- More advanced natural-language query understanding
- Improved filtering and ranking
- More sophisticated recommendation strategies
- Additional course metadata
- Improved conversational memory
- Evaluation metrics for retrieval and recommendation quality
- Deployment as a web application
- Support for additional course platforms and datasets

---

## 👩‍💻 Author

### Donia Safwat

**AI Engineer | Machine Learning | Deep Learning | Computer Vision**

🔗 GitHub: https://github.com/doniasafwat

🔗 LinkedIn: https://www.linkedin.com/in/doniasafwat1/

---

## ⭐ Project Focus

**Artificial Intelligence • Machine Learning • NLP • LLMs • RAG • AI Agents • Semantic Search**
