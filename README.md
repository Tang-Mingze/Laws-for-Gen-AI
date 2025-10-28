# **Dataset Construction Based on AI Regulations (EU & China)**

This project creates datasets derived from two key AI governance documents:
the **European Union’s AI Act** and **China’s Interim Measures for the Management of Generative Artificial Intelligence Services(生成式人工智能服务管理暂行办法)**.

---

## **1. China**

* The file **`（生成式人工智能服务管理暂行办法.txt）`** in the `China` folder contains the *filtered provisions* from the regulation.
  **Link to the original text:** [https://www.moj.gov.cn/pub/sfbgw/flfggz/flfggzbmgz/202401/t20240109_493171.html](https://www.moj.gov.cn/pub/sfbgw/flfggz/flfggzbmgz/202401/t20240109_493171.html)

* **Filtering criterion:**
  Each provision included in this file must allow for at least one **prompt** that can generate both a **positive** (compliant/supporting) and a **negative** (violating/conflicting) output example with respect to that provision.

* **Dataset file:**
  The file **`Chinese_dataset.json`** contains:

  * the legal provision text,
  * a **neutral prompt**, and
  * a pair of **positive and negative output examples** illustrating compliance and non-compliance with the rule.

---

## **2. European Union**

* The file **`Selected_articles_id.json`** in the `European Union` folder lists the *articles selected* from the **AI Act**.
  **Link to the original text:** [https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng](https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng)

* **Filtering criterion:**
  Each article was evaluated as a whole to determine whether it allows for at least one **prompt** that can produce both **positive** and **negative** outputs related to compliance with the article. These selected articles were further **split into individual provisions**, stored in **`Selected_articles_split.json`**. Based on the same selection criteria as in the China section, the subset of provisions suitable for dataset construction was stored in **`Selected_articles_split_evaluated_yes.json`**.

* **Dataset file:**
  The file **`Euro_dataset.json`** is constructed based on **`Selected_articles_split_evaluated_yes.json`**, and contains:

  * the legal provision text,
  * a **neutral prompt**, and
  * a pair of **positive and negative output examples** demonstrating compliance and non-compliance with the rule.

---

## **3. Japan**

* The file **`Jp_articles`** in the `Japan` folder contains the *selected and cropped provisions* from the **Act on the Promotion of Research and Development and Utilization of AI-Related Technology (令和五年法律第五⼗三号)**.
  **Link to the original text:** [https://laws.e-gov.go.jp/law/507AC0000000053](https://laws.e-gov.go.jp/law/507AC0000000053)

* **Filtering criterion:**
  Each provision included in this file was selected based on its suitability to be paired with a single **neutral prompt** that can generate both a **positive** (compliant/supporting) and a **negative** (violating/conflicting) output example with respect to that specific provision.

* **Dataset file:**
  The file **`Jp_AI_Promotion_Act_Dataset`** is constructed based on the filtered provisions and contains:

  * the legal provision text (**content**),
  * a **neutral prompt** (**prompt**), and
  * a pair of **positive and negative output examples** (**pe** and **ne**) demonstrating compliance and non-compliance with the rule.
