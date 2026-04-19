# Complexity Analysis (ရှုပ်ထွေးမှုအား ခွဲခြမ်းစိတ်ဖြာခြင်း)

Complexity analysis is a fundamental tool for developers to estimate the resources needed by an algorithm. It focuses on how the resources grow as the input size ($n$) increases.

Complexity Analysis ဆိုတာကတော့ Algorithm တစ်ခုဟာ Data ပမာဏ ($n$) များလာတဲ့အခါ ဘယ်လောက်အထိ အချိန်ပိုယူလာမလဲ၊ Memory ပိုယူလာမလဲဆိုတာကို ကြိုတင်ခန့်မှန်းတဲ့ နည်းလမ်းပဲ ဖြစ်ပါတယ်။

---

## 1. Why Analyze Complexity? (ဘာလို့ ခွဲခြမ်းစိတ်ဖြာဖို့ လိုတာလဲ)

In the real world, we need to balance speed and resource usage. An algorithm that works perfectly with 10 items might fail or become extremely slow with 10 million items. Analysing complexity helps us:
- Predict Scalability (လုပ်ငန်းပမာဏ တိုးချဲ့နိုင်မှုကို သိနိုင်ခြင်း)
- Compare Algorithms (Algorithm တွေကို နှိုင်းယှဉ်နိုင်ခြင်း)
- Optimize Resources (အရင်းအမြစ်တွေကို အထိရောက်ဆုံး သုံးနိုင်ခြင်း)

---

## 2. Two Main Dimensions (အဓိက အပိုင်း ၂ ပိုင်း)

Every algorithm is evaluated based on two types of complexity:

### A. Time Complexity (အချိန် ကြာမြင့်မှု)
Focuses on the **execution time** or the number of operations performed.
Algorithm တစ်ခု အလုပ်လုပ်ဖို့အတွက် ကြာမြင့်တဲ့ "အချိန်" ဒါမှမဟုတ် လုပ်ဆောင်ရတဲ့ "အဆင့်" အရေအတွက် ဖြစ်ပါတယ်။

> **Goal:** Run as fast as possible. (အမြန်ဆုံး ဖြစ်အောင် လုပ်ဆောင်ရန်။)

### B. Space Complexity (နေရာယူမှု)
Focuses on the **memory (RAM)** required to run the algorithm.
Algorithm တစ်ခု အလုပ်လုပ်ဖို့အတွက် Computer ရဲ့ Memory (RAM) ကို ဘယ်လောက် အသုံးပြုသလဲ ဆိုတာ ဖြစ်ပါတယ်။

> **Goal:** Use as little memory as possible. (Memory အနည်းဆုံး သုံးရန်။)

---

## 3. Real-World Analogy (လက်တွေ့ဘဝ ဥပမာ)

Imagine you are looking for a name in a phone book:

- **Search One by One (Linear Search):** You start from the first page and look at every name. If the book has 1,000 pages, you might look at 1,000 pages. 
    - **Complexity:** $O(n)$ - As the number of pages increases, your time increase.
- **Search by Half (Binary Search):** You open the middle, see if the name is before or after, and keep halving. Even if the book has 1,000,000 pages, you'll find it in about 20 steps!
    - **Complexity:** $O(\log n)$ - Very efficient even with massive data.

---

## 4. Complexity Comparison Table (နှိုင်းယှဉ်ချက် ဇယား)

| Type | Focuses on... | Key Question |
| :--- | :--- | :--- |
| **Time Complexity** | CPU / Speed | How many operations? (ဘယ်နှစ်ဆင့် အလုပ်လုပ်ရသလဲ?) |
| **Space Complexity** | RAM / Memory | How much storage? (ဘယ်လောက် နေရာယူသလဲ?) |

---

## 5. Conclusion (နိဂုံး)

A good algorithm is one that balances both Time and Space. In modern computing, we often prioritize **Time Complexity** (Speed) because memory is cheaper, but for embedded systems or mobile apps, **Space Complexity** remains critical.

Algorithm ကောင်းတစ်ခုဆိုတာ အချိန်နဲ့ နေရာ နှစ်ခုလုံးမှာ မျှတရပါမယ်။ အခုခေတ်မှာတော့ Memory တွေက ဈေးသက်သာလာလို့ "အမြန်နှုန်း (Time)" ကို ပိုဦးစားပေးလေ့ ရှိကြပေမယ့်၊ ဖုန်း App တွေ ဒါမှမဟုတ် စွမ်းအားနည်းတဲ့ system တွေမှာတော့ "နေရာယူမှု (Space)" ကလည်း အရမ်းကို အရေးကြီးနေဆဲ ဖြစ်ပါတယ်။
