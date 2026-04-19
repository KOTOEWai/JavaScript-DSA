# Big O of Objects and Arrays (Object နှင့် Array များ၏ Big O)

In JavaScript, choosing between an Object and an Array can significantly impact the performance of your application. Let's look at the Big O of each.

JavaScript မှာ Object သို့မဟုတ် Array ကို ရွေးချယ်အသုံးပြုခြင်းဟာ သင့် App ရဲ့ စွမ်းဆောင်ရည်အပေါ် များစွာ သက်ရောက်မှု ရှိပါတယ်။ သူတို့ တစ်ခုချင်းစီရဲ့ Big O ကို အသေးစိပ် ကြည့်ကြရအောင်။

---

## 1. Objects (အချက်အလက်များကို နာမည်ဖြင့် သိမ်းဆည်းခြင်း)

Objects are unordered collections of key-value pairs. They are perfect when you don't need a specific order and want fast access.
Object တွေက အစဉ်လိုက် ဖြစ်နေစရာ မလိုဘဲ Key-Value pairs တွေနဲ့ သိမ်းတာ ဖြစ်ပါတယ်။ အချက်အလက်တွေကို အမြန်ဆုံး ရှာဖွေ၊ ရယူချင်တဲ့ အခါမျိုးမှာ သုံးပါတယ်။

### Performance (စွမ်းဆောင်ရည်)
- **Insertion (အသစ်ထည့်ခြင်း):** $O(1)$
- **Removal (ဖယ်ရှားခြင်း):** $O(1)$
- **Access (တိုက်ရိုက်ရယူခြင်း):** $O(1)$
- **Searching (ရှာဖွေခြင်း):** $O(n)$ (Value ကို လိုက်ရှာရရင် element တိုင်းကို စစ်ရလို့ပါ။)

### Built-in Methods
| Method | Complexity | Burmese Explanation |
| :--- | :--- | :--- |
| `Object.keys()` | $O(n)$ | Key အားလုံးကို ထုတ်ယူခြင်း။ |
| `Object.values()` | $O(n)$ | Value အားလုံးကို ထုတ်ယူခြင်း။ |
| `Object.entries()` | $O(n)$ | နှစ်ခုလုံးကို အတွဲလိုက် ထုတ်ယူခြင်း။ |
| `hasOwnProperty()` | $O(1)$ | Key ရှိမရှိ စစ်ဆေးခြင်း (အရမ်းမြန်ပါတယ်)။ |

---

## 2. Arrays (အချက်အလက်များကို အစဉ်လိုက် သိမ်းဆည်းခြင်း)

Arrays are ordered collections. They are used when the order of elements matters.
Array တွေကတော့ အချက်အလက်တွေကို အစဉ်လိုက် (Index နံပါတ်တွေနဲ့) သိမ်းဆည်းတာ ဖြစ်ပါတယ်။

### Performance (စွမ်းဆောင်ရည်)
- **Access (ရယူခြင်း):** $O(1)$ (Index သိရင် တန်းယူလို့ရပါတယ်။)
- **Searching (ရှာဖွေခြင်း):** $O(n)$
- **Insertion (ထည့်သွင်းခြင်း):** It depends!
    - **Push (အဆုံးမှာ ထည့်ခြင်း):** $O(1)$
    - **Unshift (အစမှာ ထည့်ခြင်း):** $O(n)$ (ကျန်တဲ့ element တွေ အကုန်လုံးကို Index အသစ်တွေ ပြန်ပေးရလို့ပါ။)
- **Removal (ဖယ်ရှားခြင်း):** It depends!
    - **Pop (အဆုံးမှ ဖယ်ခြင်း):** $O(1)$
    - **Shift (အစမှ ဖယ်ခြင်း):** $O(n)$ (Index တွေ အကုန်လုံးကို ပြန်ပြင်ရလို့ပါ။)

> [!IMPORTANT]
> Adding or removing elements from the **start** of an array is more expensive than adding/removing from the **end** because the computer has to re-index every other element.
> Array တစ်ခုရဲ့ **အရှေ့ဆုံး** ကနေ Data ထည့်တာ (သို့) ဖယ်တာက **အနောက်ဆုံး** ကနေ လုပ်တာထက် ပိုကြာပါတယ်။ ဘာလို့လဲဆိုတော့ ကျန်တဲ့ Data တွေ အကုန်လုံးကို နေရာ (Index) အသစ်တွေ ပြန်ချပေးရလို့ ဖြစ်ပါတယ်။

### Built-in Methods
| Method | Complexity | Burmese Explanation |
| :--- | :--- | :--- |
| `push` / `pop` | $O(1)$ | အနောက်မှာ ထည့်/ဖယ်ခြင်း။ |
| `shift` / `unshift` | $O(n)$ | အရှေ့မှာ ထည့်/ဖယ်ခြင်း။ |
| `concat` / `slice` / `splice` | $O(n)$ | Array တွေကို ပေါင်းခြင်း သို့မဟုတ် အပိုင်းဖြတ်ခြင်း။ |
| `sort` | $O(n \log n)$ | အစဉ်လိုက် စီခြင်း (အချိန်အသင့်တင့် ယူပါတယ်)။ |
| `forEach` / `map` / `filter` | $O(n)$ | တစ်ခုချင်းစီကို Loop ပတ်ပြီး အလုပ်လုပ်ခြင်း။ |

---

## Summary 

*   **Objects:** Use when you need fast **Insertion/Removal/Access** and don't care about the order.
*   **Arrays:** Use when you need to keep things in **Order**, but be careful with adding/removing from the beginning.

*   **Objects:** အချက်အလက်တွေကို အမြန် ထည့်ချင်၊ ထုတ်ချင်၊ ဖတ်ချင်တဲ့အခါ သုံးပါ။ အစဉ်လိုက် ဖြစ်စရာ မလိုပါ။
*   **Arrays:** အချက်အလက်တွေကို အစဉ်အတိုင်း သိမ်းချင်တဲ့အခါ သုံးပါ။ ဒါပေမဲ့ အရှေ့ဆုံးကနေ Data တွေ ခဏခဏ ပြင်တာမျိုးကိုတော့ ရှောင်သင့်ပါတယ်။
