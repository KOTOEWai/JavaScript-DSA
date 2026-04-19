#  Complexity Analysis

To measure the efficiency of an algorithm, we use two main metrics: **Time** and **Space**.

---

## 1. Time Complexity
**Definition:** The amount of time an algorithm takes to run as a function of the length of the input.
* It is NOT measured in seconds (because hardware varies).
* It IS measured by the number of operations performed.

> **Key Notation:** Big O Notation (e.g., $O(1)$, $O(n)$, $O(n^2)$).

---

## 2. Space Complexity
**Definition:** The amount of working memory (RAM) an algorithm needs to run to completion.
* This includes both the input data size and any auxiliary (extra) space used by the algorithm.

---

## 3. Comparison Table

| Metric | Focuses On... | Goal |
| :--- | :--- | :--- |
| **Time Complexity** | Speed | Minimize the number of steps. |
| **Space Complexity** | Memory | Minimize the usage of RAM. |

---


```
Time Complexity (အချိန် ကြာမြင့်မှု)

၁။ ဒါဟာ Algorithm တစ်ခု အလုပ်လုပ်ဖို့ "စက္ကန့်" ဘယ်လောက်ကြာလဲဆိုတာကို တိုင်းတာတာ မဟုတ်ပါဘူး (ဘာလို့လဲဆိုတော့ Computer တစ်လုံးနဲ့တစ်လုံး Speed မတူလို့ပါ)။

သူက Input Data (ဥပမာ- စာရင်းအင်းတွေ) များလာရင် အလုပ်လုပ်ရတဲ့ "အဆင့်" ဘယ်လောက် များလာမလဲ ဆိုတာကို တိုင်းတာတာပါ။

ဥပမာ: လူ ၁၀ ယောက်ထဲမှာ နာမည်တစ်ခု ရှာတာက မြန်ပေမဲ့၊ လူ ၁ သန်းထဲမှာ ရှာရင် ပိုကြာသွားမယ်။ အဲ့ဒီလို Data ပမာဏအပေါ် မူတည်ပြီး အချိန် ဘယ်လောက် တိုးလာမလဲဆိုတာကို O(n) လိုမျိုး Big O Notation နဲ့ ဖော်ပြပါတယ်။

၂။ Space Complexity (နေရာယူမှု)

ဒါကတော့ Algorithm တစ်ခု အလုပ်လုပ်နေတုန်းမှာ Computer ရဲ့ Memory (RAM) ကို ဘယ်လောက် သုံးသလဲဆိုတာပါ။

ဥပမာ: သင်က စာရင်းတစ်ခုကို Sort (စီ) ချင်တယ်။နဂိုစာရင်းထဲမှာတင် နေရာမပြောင်းဘဲ စီရင် Space နည်းနည်းပဲ သုံးတယ်။
 (Space Efficient ဖြစ်တယ်)ဒါပေမဲ့ စာရင်းအသစ်တစ်ခု ထပ်ဆောက်ပြီးမှ စီမယ်ဆိုရင်တော့ Memory နေရာ ပိုယူသွားပါလိမ့်မယ်။
 

၃။ ဘာလို့ နှစ်ခုလုံးကို ကြည့်ရတာလဲ? (The Trade-off)

တစ်ခါတလေမှာ Algorithm တစ်ခုက အရမ်းမြန် (Time Complexity နည်း) ပေမဲ့ Memory အရမ်းစား (Space Complexity များ) တတ်ပါတယ်။ ပြောင်းပြန်လည်း ဖြစ်နိုင်ပါတယ်။Developer တစ်ယောက်အနေနဲ့ ကိုယ့် App ရဲ့ အခြေအနေပေါ် မူတည်ပြီး မြန်အောင်လုပ်မလား ဒါမှမဟုတ် Memory သက်သာအောင် လုပ်မလား ဆိုတာကို မျှတအောင် ရွေးချယ်ရပါတယ်။

```

