<h1 align="center"><b>Domain Adaptive Bengali Text Summarization Harnessing Large Language Models in Closed Set Contexts</b></h1>

<h1><b>Abstract</b></h1>
With the increasing volume of Bengali textual information, effective summarization tools are essential for extracting key insights efficiently. This project develops a domain-adaptive Bengali text summarization model using Large Language Models (LLMs), specifically mT5 and flanT5, trained and fine-tuned on both general and domain-specific datasets. The goal is to enhance the accuracy of summarization for specific content, addressing the scarcity of Bengali text summarization models in a low-resource language setting.

<h1><b>Methodoogy</b></h1>
### 1. Data Collection & Preprocessing  
The model was trained on the **XLSUM Bengali dataset**, followed by fine-tuning with a **custom dataset of 21,512 rows**, collected through web scraping from multiple Bengali news sources (**The Daily Star, Prothom Alo, Jugantor, Ittefaq**).  

The dataset was manually categorized into **seven distinct domains**:  
1. Sports  
2. State  
3. International  
4. Entertainment  
5. Education  
6. Economy  
7. Technology  

Domain adaptation was applied to **three domains**:  
- **State**  
- **International**  
- **Sports**  

### 2. Training & Model Selection  
Both **flanT5** and **mT5** models were trained on the **XLSUM Bengali dataset**.  

The **mT5 model outperformed flanT5** on standard summarization tasks, achieving:  
- **ROUGE-1:** 0.21  
- **ROUGE-2:** 0.09  
- **ROUGE-L:** 0.20  
- **BLEU:** 0.17  
- **BERTScore:** 0.72  

### 3. Domain Adaptation  
The models were fine-tuned on **specific domains** (State, International, Sports) using a **closed-set domain adaptation technique**.  

- **Fine-tuning Results:**  
  - **flanT5** achieved the highest **ROUGE (0.79)** and **BERTScore (0.86)** in the **state** domain.  
  - **mT5** showed stronger performance in **zero-shot settings** for **unseen domain-specific data**.  

### 4. Evaluation & Results  
- **flanT5** excelled in **fine-tuning**, while **mT5** demonstrated stronger adaptability in **zero-shot learning**, especially in the **state domain**.  
- Models were evaluated using **ROUGE, BLEU, and BERTScore**, showing **high-quality, domain-specific summarization capabilities**.  

### 5. Web Interface Development  
A **Flask-based web application** was created to enable users to input Bengali text and receive concise summaries.  

- **Features of the Web Interface:**  
  - Simple UI for easy use.  
  - Real-time Bengali text summarization.  
