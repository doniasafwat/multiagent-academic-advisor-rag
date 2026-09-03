Multi-Agent Academic Advisor 🎓🤖

An AI-powered academic advisor that uses Large Language Models (LLMs), Retrieval-Augmented Generation (RAG), semantic search, and course recommendation to help users find relevant online courses based on their preferences.

📌 Project Overview

This project implements an academic course advisory system that understands natural-language course requests, retrieves relevant courses from a dataset, and generates recommendations and answers using an LLM.

The system works with the Udemy Courses Dataset and focuses on course information such as:

Course title
Category
Topic
Language
Price
Course duration
Course description
🧠 System Architecture

The overall workflow is:

User Query → Input Understanding → Course Retrieval → Recommendation / Q&A → Response

The project combines multiple components:

1. Input Agent

Processes the user's natural-language request and extracts useful filters such as:

Category
Topic
Language
Maximum price
Maximum course duration
2. Semantic Search & RAG

Course information is converted into vector embeddings using Sentence Transformers.

FAISS is then used to perform similarity search and retrieve the most relevant courses.

3. LLM-Based Q&A

The retrieved course information is provided to a language model to generate responses and answer course-related questions.

4. Course Recommendation

The system generates course recommendations based on the user's requirements and the retrieved course information.

5. Feedback Component

A feedback mechanism is included to capture user feedback about the generated recommendations.

6. Gradio Interface

A Gradio-based interface provides an interactive way for users to enter course requests and receive recommendations.

🔎 Retrieval-Augmented Generation (RAG)

The RAG pipeline follows these steps:

Receive the user's query.
Convert course data into embeddings.
Perform similarity search using FAISS.
Retrieve relevant course information.
Provide the retrieved information to the LLM.
Generate a response based on the retrieved courses.

This helps ground the generated responses in the available course data.

🛠️ Technologies
Python
Pandas
NumPy
Transformers
Sentence Transformers
FAISS
Gradio
Large Language Models (LLMs)
Retrieval-Augmented Generation (RAG)
Semantic Search
📊 Dataset

This project uses the Udemy Courses Dataset (2022).

The notebook uses Course_info.csv.

The dataset can be obtained from Kaggle:
https://www.kaggle.com/datasets/hossaingh/udemy-courses

Dataset Setup

The dataset is not included in this repository.

After downloading the dataset, place Course_info.csv in the same directory as the notebook.

🚀 How to Run
Download or clone this repository.
Download the Udemy Courses Dataset from Kaggle.
Place Course_info.csv next to the notebook.
Install the required Python packages.
Open the notebook.
Run the notebook cells in order.
Launch the Gradio interface to interact with the academic advisor.
📁 Project Structure

multiagent-academic-advisor-rag/

├── multiagent-academic-advisor-rag.ipynb
├── README.md
├── requirements.txt
└── .gitignore

🎯 Key Concepts

This project demonstrates practical implementation of:

Natural Language Processing
Large Language Models
Semantic Search
Vector Embeddings
Retrieval-Augmented Generation (RAG)
FAISS Similarity Search
Course Recommendation
Multi-component AI Agent Architecture
Interactive AI Applications
👩‍💻 Author

Donia Safwat

AI Engineer | Machine Learning | Deep Learning | Computer Vision

GitHub: https://github.com/doniasafwat
LinkedIn: https://www.linkedin.com/in/doniasafwat1/
