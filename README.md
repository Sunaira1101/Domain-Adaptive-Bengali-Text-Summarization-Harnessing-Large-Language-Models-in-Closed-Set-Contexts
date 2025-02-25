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
 
<h1><b>Example of Generated Summaries Using the Two Models</b></h1>
## Example of Generated Summaries Using the Two Models  

| **Section**         | **Content** |
|---------------------|------------|
| **Article**        | ভারেতর অনয্ অঞ্চেলও েকাক, েপপিস িনিষদ্ধ করার দািব জানােচ্ছন কমীর্রা। স্থানীয় পেণয্র বয্বহার িনিশ্চত করার জনয্ই এই উেদয্াগ গ্রহণ কেরেছ বয্বসায়ীরা। রােজয্র শীষর্ দুিট বয্বসায়ী এেসািসেয়শন এই দুিট পানীয় িনিষদ্ধ করার প্রস্তাব কেরিছল। তারই েপ্রক্ষাপেট আজ বুধবার েথেক তািমলনাডু রােজয্ িনিষদ্ধ হেলা েকাকা-েকালা ও েপপিস। প্রিতষ্ঠানগুেলা বলেছ, েকামল পানীেয়র প্রিতষ্ঠানগুেলা নদী েথেক প্রচুর পািন বয্বহার কের, েসকারেণ কৃষকেদর জিম েসেেচর সময়ও বয্াপক েভাগািন্তেত পড়েত হয়। িবেশষ কের খরার সময় েসেেচ পািন সমসয্া প্রকট হেয় দঁাড়ায়। রােজয্র দশ লােখরও েবিশ েদাকানদার এ িনেষধাজ্ঞা েমেন চলেব বেল ধারণা করা হেচ্ছ। গত মােস তািমলনাডুেত 'জািল্লকাটু' নােম ঐিতহয্বাহী ষঁােড়র লড়াই িনিষেদ্ধর িবরুেদ্ধ বয্াপক িবেক্ষােভর ঘটনা েদেখ রােজয্ েপপিস, েকাকা-েকালা িনিষেদ্ধর প্রস্তাব কের শীষর্ দুিট বয্বসায়ী সংগঠন েফডােরশন অব তািমলনাডু েট্রডাসর্ এেসািসেয়শন (এফিটএনিটএ) এবং তািমলনাডু েট্রডাসর্ এেসািসেয়শন। |
| **Reference Summary** | ভারেতর দিক্ষণাঞ্চলীয় রাজয্ তািমলনাডুর বয্বসায়ীরা েসখােন েকাকা-েকালা ও েপপিস িবিক্র িনিষদ্ধ েঘাষণা কেরেছ। |
| **Text Summarization (mT5)** | ভারেতর তািমলনাডু রােজয্ েকাকা-েকালা এবং েপপিস িনিষদ্ধ কেরেছ বয্বসায়ীরা। এই দুিট পানীয় নদী েথেক প্রচুর পািন বয্বহার কের, েসে কারেণ কৃষকেদর জিম েসেেচর সময়ও বয্াপক েভাগািন্তেত পেড়। |
| **Text Summarization (flanT5)** | ভারেতর অনয্ বয্বহার িনিষদ্ধ করার জেনয্ এই উেদয্াগ গ্রহণ কেরেছ বয্বসায়ীরা। |
| **Domain Adaptation (mT5)** | ভারেতর তািমলনাডু রােজয্ েকাকা-েকালা এবং েপপিস িনিষদ্ধ কেরেছ বয্বসায়ীরা। |
| **Domain Adaptation (flanT5)** | ভারেতর অনয্ অঞ্চেলও েকাক, েপপিস িনিষদ্ধ করার দািব জানােচ্ছন কমীর্রা। স্থানীয় পেণয্র বয্বহার িনিশ্চত করার জনয্ই এই উেদয্াগ গ্রহণ কেরেছ বয্বসায়ীরা। রােজয্র শীষর্ দুিট বয্বসায়ী এেসািসেয়শন এই দুিট পানীয় িনিষদ্ধ করার প্রস্তাব কেরিছল। তারই েপ্রক্ষাপেট আজ বুধবার েথেক তািমলনাডু রােজয্ িনিষদ্ধ হেলা। |

