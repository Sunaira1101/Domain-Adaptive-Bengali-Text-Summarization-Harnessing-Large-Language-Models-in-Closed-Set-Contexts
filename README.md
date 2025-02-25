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
| **Article**        | ভারতের অন্য অঞ্চলেও কোক, পেপসি নিষিদ্ধ করার দাবি জানাচ্ছেন কর্মীরা। স্থানীয় পণ্যের ব্যবহার নিশ্চিত করার জন্যই এই উদ্যোগ গ্রহণ করেছে ব্যবসায়ীরা। রাজ্যের শীর্ষ দুটি ব্যবসায়ী এসোসিয়েশন এই দুটি পানীয় নিষিদ্ধ করার প্রস্তাব করেছিল। তারই প্রেক্ষাপটে আজ বুধবার থেকে তামিলনাডু রাজ্যে নিষিদ্ধ হলো কোকা-কোলা ও পেপসি। প্রতিষ্ঠানগুলো বলছে, কোমল পানীয়ের প্রতিষ্ঠানগুলো নদী থেকে প্রচুর পানি ব্যবহার করে, সেকারণে কৃষকদের জমি সেচের সময়ও ব্যাপক ভোগান্তিতে পড়তে হয়। বিশেষ করে খরার সময় সেচে পানি সমস্যা প্রকট হয়ে দাঁড়ায়। রাজ্যের দশ লাখেরও বেশি দোকানদার এ নিষেধাজ্ঞা মেনে চলবে বলে ধারণা করা হচ্ছে। গত মাসে তামিলনাডুতে 'জাল্লিকাটু' নামে ঐতিহ্যবাহী ষাঁড়ের লড়াই নিষিদ্ধের বিরুদ্ধে ব্যাপক বিক্ষোভের ঘটনা দেখে রাজ্যে পেপসি, কোকা-কোলা নিষিদ্ধের প্রস্তাব করে শীর্ষ দুটি ব্যবসায়ী সংগঠন ফেডারেশন অব তামিলনাডু ট্রেডার্স এসোসিয়েশন (এফটিএনটিএ) এবং তামিলনাডু ট্রেডার্স এসোসিয়েশন। বিক্ষোভের সময় অনেকে বলছিলেন 'জাল্লিকাটু' নিষিদ্ধ করা মানে স্থানীয় ঐতিহ্য ও সংস্কৃতিকে অবমাননা করা। "আমরা কয়েক মাস আগে কোমল পানীয়ের বিরুদ্ধে আমাদের প্রচারণা শুরু করি, কিন্তু যখন আমরা 'জাল্লিকাটু' নিষিদ্ধের প্রতিবাদে বিক্ষোভ শুরু করি, কোমল পানীয়ের বিরুদ্ধে আমাদের প্রচারণাও ভিন্ন রূপ পায়"- বিবিসি তামিল সার্ভিসকে দেয়া এক সাক্ষাৎকারে বলছিলেন এফটিএনটিএ'র প্রেসিডেন্ট থা ভেলায়ান। "পেপসি এবং কোকা-কোলার মতো পানীয় কিন্তু আপনার স্বাস্থ্যের জন্য ভালো নয়। কারণ এর মধ্যে বিভিন্ন ধরনের কেমিকেল থাকে এবং অতিরিক্ত চিনি থাকে এসব পানীয়তে। আমরা ভারতীয় কোমল পানীয়ের প্রচার চালাচ্ছি এবং ফলের জুসের বিক্রি যেন আরও বাড়ে সেই চেষ্টাও আমরা চালাবো"-বলছিলেন ব্যবসায়ী থা ভেলায়ান। স্থানীয় ব্যবসা এবং কৃষকদের উন্নতির কথা ভেবে সুপারমার্কেট, রেস্টুরেন্ট ও হোটেলগুলো যেন এই নিষেধাজ্ঞা মেনে চলে সেই আহ্বানও জানিয়েছে এসোসিয়েশনগুলো। এই নিষেধাজ্ঞার বিষয়ে পেপসি ও কোকা-কোলা প্রতিষ্ঠানের পক্ষ থেকে এখনও কোনো মন্তব্য পাওয়া যায়নি। |
| **Reference Summary** | ভারতের দক্ষিণাঞ্চলীয় রাজ্য তামিলনাডুর ব্যবসায়ীরা সেখানে কোকা-কোলা ও পেপসি বিক্রি নিষিদ্ধ ঘোষণা করেছে। |
| **Text Summarization (mT5)** | ভারতের তামিলনাডু রাজ্যে কোকা-কোলা এবং পেপসি নিষিদ্ধ করেছে ব্যবসায়ীরা। এই দুটি পানীয় নদী থেকে প্রচুর পানি ব্যবহার করে, সে কারণে কৃষকদের জমি সেচের সময়ও ব্যাপক ভোগান্তিতে পড়ে। |
| **Text Summarization (flanT5)** | ভারতের অন্য ব্যবহার নিষিদ্ধ করার জন্যে এই উদ্যোগ গ্রহণ করেছে ব্যবসায়ীরা। |
| **Domain Adaptation (mT5)** | ভারতের তামিলনাডু রাজ্যে কোকা-কোলা এবং পেপসি নিষিদ্ধ করেছে ব্যবসায়ীরা। |
| **Domain Adaptation (flanT5)** | ভারতের অন্য অঞ্চলেও কোক, পেপসি নিষিদ্ধ করার দাবি জানাচ্ছেন কর্মীরা। স্থানীয় পণ্যের ব্যবহার নিশ্চিত করার জন্যই এই উদ্যোগ গ্রহণ করেছে ব্যবসায়ীরা। রাজ্যের শীর্ষ দুটি ব্যবসায়ী এসোসিয়েশন এই দুটি পানীয় নিষিদ্ধ করার প্রস্তাব করেছিল। তারই প্রেক্ষাপটে আজ বুধবার থেকে তামিলনাডু রাজ্যে নিষিদ্ধ হলো। |

