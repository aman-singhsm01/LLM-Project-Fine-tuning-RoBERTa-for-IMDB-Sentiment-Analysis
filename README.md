# 📌 LLM Project — Fine-tuning RoBERTa for IMDB Sentiment Analysis  
code link -https://colab.research.google.com/drive/1Z4vz5bN4TewCacyQ9Lo-0awnKxzKADeF#scrollTo=m4lhdl2UNKNq
## 📖 Project Description  
This project demonstrates the **fine-tuning of a Large Language Model (LLM)** — **RoBERTa-base** 🤖 — for **sentiment analysis** on movie reviews.  
The model classifies IMDB reviews as either **Positive** or **Negative** using supervised fine-tuning with a **classification head**.  

By leveraging **transfer learning** and **Hugging Face Transformers**, the model achieves **94% accuracy** on the test set 🎯.  
An **interactive interface** was also built using `ipywidgets` to allow users to enter a review and instantly get predictions.  

---

## 📂 Dataset Description  
- **Dataset Name:** IMDB Movie Reviews (Kaggle version)  
- **Size:** 5,000 reviews  
- **Labels:**  
  - `0` → Negative  
  - `1` → Positive  
- **Columns:**  
  - `review` → The movie review text  
  - `sentiment` → Sentiment label (positive/negative)  

---

## ⚙️ Methodology / Workflow  
1. **Dataset Preprocessing**  
   - Loaded the dataset using `datasets` library  
   - Cleaned text and mapped labels (positive → 1, negative → 0)  
   - Train/Test split  

2. **Tokenization**  
   - Used Hugging Face `RobertaTokenizer`  
   - Max sequence length: **512** tokens  

3. **Model Setup**  
   - Base model: **RoBERTa-base**  
   - Added a **classification head** (dense layer) for binary classification  
   - Used `AutoModelForSequenceClassification`  

4. **Training Configuration**  
   - Optimizer: AdamW  
   - Learning Rate: `2e-5`  
   - Batch Size: `16`  
   - Epochs: `3`  
   - Loss: CrossEntropyLoss  
   - Trainer API from Hugging Face used for training and evaluation  

5. **Evaluation**  
   - Metric: Accuracy  
   - Achieved **94% accuracy** on the test set 🎯  

6. **Interactive Interface**  
   - Built using `ipywidgets`  
   - Users can input a review and get predictions (Positive/Negative) with probabilities  

---

## 🧑‍💻 Technologies Used  
- **Language:** Python 🐍  
- **Libraries:**  
  - PyTorch  
  - Hugging Face Transformers  
  - Datasets  
  - Evaluate  
  - Accelerate  
  - ipywidgets  

---

## 📊 Results  
- **Accuracy:** 94%  
- **Sample Output:**  

```text
Review: "The movie was fantastic, I loved it!"
Prediction: Positive ✅
Probability: [Negative: 0.12, Positive: 0.88]
