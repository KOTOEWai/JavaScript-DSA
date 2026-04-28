# Stack နှင့် Heap ဆိုတာဘာလဲ? (Understanding Stack vs Heap Memory)

ကွန်ပျူတာ ပရိုဂရမ်တစ်ခု အလုပ်လုပ်တဲ့အခါ RAM ကို အဓိကအားဖြင့် အပိုင်း (၂) ပိုင်း ခွဲခြားပြီး အသုံးချပါတယ်။ အဲဒါတွေကတော့ **Stack** နဲ့ **Heap** တို့ ဖြစ်ပါတယ်။

---

## ၁။ Stack Memory (စနစ်တကျ စီထားသော မှတ်ဉာဏ်)
Stack ဟာ **LIFO (Last-In-First-Out)** စနစ်နဲ့ အလုပ်လုပ်ပါတယ်။ နောက်ဆုံးမှ ဝင်လာတာက အရင်ဆုံး ပြန်ထွက်ရတဲ့ ပုံစံမျိုးပါ။

*   **ဘာတွေသိမ်းလဲ:** Local variables (function အတွင်း ကြေငြာထားသော အရာများ) တွေ၊ Function call  တွေနဲ့ Primitive data types (ဥပမာ - numbers, booleans) တွေကို သိမ်းပါတယ်။
*   **ထူးခြားချက်:** အလွန်မြန်ဆန်တယ်၊ နေရာအကန့်အသတ်ရှိတယ်၊ အလိုအလျောက် သိမ်းဆည်း/ဖျက်သိမ်းပေးတယ် (Automatic management)။

## ၂။ Heap Memory (လွတ်လပ်သော မှတ်ဉာဏ်)
Heap ဟာ ကြီးမားတဲ့ data တွေကို သိမ်းဆည်းဖို့အတွက် အသုံးပြုတဲ့ နေရာလွတ်ကြီးတစ်ခုလို ဖြစ်ပါတယ်။

*   **ဘာတွေသိမ်းလဲ:** Objects တွေ၊ Arrays တွေနဲ့ Reference types တွေကို သိမ်းပါတယ်။
*   **ထူးခြားချက်:** နေရာအများကြီးရှိတယ်၊ Stack ထက် နှေးတယ်၊ Memory ကို manual စီမံရတယ် (သို့မဟုတ်) Garbage Collector က သိမ်းဆည်းပေးရတယ်။

---

## ဘယ်လို အလုပ်လုပ်သလဲ? (Step-by-Step Example)

အောက်ပါ JavaScript code လေးကို ဥပမာကြည့်ရအောင် -

```javascript
function calculate() {
  let a = 10;                // Primitive (Stack)
  let user = { name: "Mg Mg" }; // Object (Heap, Reference in Stack)
}
calculate();
```

### အဆင့် (၁) - Function ကို ခေါ်လိုက်ခြင်း (Function Call)
ပရိုဂရမ်က `calculate()` ကို ခေါ်လိုက်တဲ့အခါ Stack ထဲမှာ အဲဒီ function အတွက် နေရာလွတ်တစ်ခု (**Stack Frame**) စတင် တည်ဆောက်ပါတယ်။

### အဆင့် (၂) - Primitive Variable သိမ်းဆည်းခြင်း
`let a = 10;` ဆိုတဲ့ code အလုပ်လုပ်တဲ့အခါ `a` ရဲ့ တန်ဖိုး `10` ဟာ Stack ထဲမှာ တိုက်ရိုက် သိမ်းဆည်းခံရပါတယ်။ ဒါဟာ မြန်ဆန်ပြီး နေရာသိပ်မယူပါဘူး။

### အဆင့် (၃) - Object (Reference Type) သိမ်းဆည်းခြင်း
`let user = { name: "Mg Mg" };` အလုပ်လုပ်တဲ့အခါ-
1.  `{ name: "Mg Mg" }` ဆိုတဲ့ object အချက်အလက်အစစ်အမှန်ကို **Heap** ထဲမှာ နေရာသွားယူပြီး သိမ်းပါတယ်။
2.  အဲဒီ object ရှိတဲ့ **Memory Address (လိပ်စာ)** ကိုတော့ **Stack** ထဲက `user` ဆိုတဲ့ variable ထဲမှာ သိမ်းလိုက်ပါတယ်။
*(ဆိုလိုတာက Stack ထဲမှာ Object မရှိပါဘူး၊ Object ရှိတဲ့ နေရာရဲ့ လိပ်စာပဲ ရှိတာပါ)*

### အဆင့် (၄) - Function အလုပ်ပြီးဆုံးခြင်း
`calculate()` function အလုပ်ပြီးသွားတဲ့အခါ Stack ထဲက Stack Frame တစ်ခုလုံးကို **Pop (ဖျက်ထုတ်)** လိုက်ပါတယ်။ `a` နဲ့ `user` (reference address) တို့ဟာ Stack ပေါ်ကနေ ချက်ချင်း ပျောက်သွားပါတယ်။

### အဆင့် (၅) - Garbage Collection
Stack ထဲက `user` ရဲ့ လိပ်စာ ပျောက်သွားပေမယ့် Heap ထဲမှာ object က ကျန်နေပါသေးတယ်။ အဲဒီ object ကို ဘယ်သူမှ မသုံးတော့ဘူးဆိုတာ သေချာသွားတဲ့အခါ **Garbage Collector** က Heap ထဲကနေ လာရောက် ဖျက်သိမ်းပေးပါတယ်။

---

## နှိုင်းယှဉ်ချက် ဇယား (Comparison Table)

| အချက်အလက် | Stack | Heap |
| :--- | :--- | :--- |
| **အလုပ်လုပ်ပုံ** | LIFO (စနစ်တကျ) | Random (လွတ်လပ်စွာ) |
| **မြန်ဆန်မှု** | အလွန်မြန်သည် | အနည်းငယ် နှေးသည် |
| **သိမ်းဆည်းမှု** | Local variables, Primitives | Objects, Arrays |
| **အရွယ်အစား** | ကန့်သတ်ချက်ရှိသည် (သေးသည်) | ကြီးမားသည် |
| **စီမံခန့်ခွဲမှု** | Automatic (အလိုအလျောက်) | Manual/Garbage Collector |

---
> [!TIP]
> Stack ထဲမှာ နေရာမလောက်တော့တဲ့အထိ data တွေ အများကြီး ထည့်မိရင် **Stack Overflow** ဆိုတဲ့ error ဖြစ်တတ်ပါတယ်။ ဥပမာ - recursive function တစ်ခု အဆုံးမရှိ ပတ်နေတာမျိုးပါ။
