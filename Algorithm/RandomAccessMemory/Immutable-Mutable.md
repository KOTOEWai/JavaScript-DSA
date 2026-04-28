# Immutable vs Mutable ဆိုတာဘာလဲ?

Programming မှာ data types တွေကို ပြုပြင်ပြောင်းလဲလို့ ရနိုင်မှုအပေါ် မူတည်ပြီး **Immutable** နဲ့ **Mutable** ဆိုပြီး အမျိုးအစား (၂) မျိုး ခွဲခြားနိုင်ပါတယ်။

---

## ၁။ Immutable (ပြုပြင်ပြောင်းလဲ၍ မရသော အရာများ)
**Immutable** ဆိုတာကတော့ တစ်ကြိမ် တည်ဆောက် (Create) ပြီးသွားရင် အဲဒီ data ရဲ့ တန်ဖိုးကို တိုက်ရိုက် ပြုပြင်လို့ မရတော့တာကို ဆိုလိုပါတယ်။

### JavaScript ရှိ Immutable Data Types များ
JavaScript ရဲ့ **Primitive Data Types** အားလုံးဟာ Immutable ဖြစ်ပါတယ်။
*   Numbers
*   Strings
*   Booleans
*   null
*   undefined
*   Symbols

### ဥပမာ - String သည် Immutable ဖြစ်ခြင်း
```javascript
let name = "Mg Mg";
name[0] = "K"; // error မပြပေမယ့် ဘာမှ ပြောင်းလဲသွားမှာ မဟုတ်ပါဘူး
console.log(name); // "Mg Mg" ပဲ ထွက်နေဦးမှာပါ
```
တကယ်လို့ `name = "Ko Ko"` လို့ ပြန်ပေးလိုက်ရင် "Mg Mg" က ပြောင်းသွားတာ မဟုတ်ဘဲ memory ထဲမှာ "Ko Ko" ဆိုတဲ့ နေရာသစ်တစ်ခုကို ထပ်ယူပြီး variable က အဲဒီနေရာသစ်ကို လှမ်းညွှန်လိုက်တာ ဖြစ်ပါတယ်။

---

## ၂။ Mutable (ပြုပြင်ပြောင်းလဲ၍ ရသော အရာများ)
**Mutable** ဆိုတာကတော့ data ကို တည်ဆောက်ပြီးသွားရင်လည်း အဲဒီ data ရဲ့ အစိတ်အပိုင်းတွေကို စိတ်ကြိုက် ပြုပြင်ပြောင်းလဲ (Modify) လို့ ရတာကို ဆိုလိုပါတယ်။

### JavaScript ရှိ Mutable Data Types များ
JavaScript ရဲ့ **Reference Data Types** တွေဟာ Mutable ဖြစ်ပါတယ်။
*   Objects
*   Arrays
*   Functions

### ဥပမာ - Object သည် Mutable ဖြစ်ခြင်း
```javascript
let user = { name: "Mg Mg", age: 20 };
user.name = "Kyaw Kyaw"; // တန်ဖိုးကို တိုက်ရိုက် ပြောင်းလို့ရပါတယ်

console.log(user.name); // "Kyaw Kyaw"
```
ဒီနေရာမှာ memory ထဲက object အစစ်အမှန် တည်ရှိတဲ့နေရာမှာတင် သွားရောက် ပြုပြင်လိုက်တာ ဖြစ်ပါတယ်။

---

## Memory အလုပ်လုပ်ပုံ ကွာခြားချက်

| အချက်အလက် | Immutable (Primitives) | Mutable (Reference Types) |
| :--- | :--- | :--- |
| **Memory နေရာ** | Stack ထဲမှာ တန်ဖိုးကို တိုက်ရိုက်သိမ်းတယ် | Heap ထဲမှာ သိမ်းပြီး Stack ထဲမှာ Address (လိပ်စာ) ကို သိမ်းတယ် |
| **ပြုပြင်ခြင်း** | တန်ဖိုးသစ်တစ်ခု အစားထိုးမှ ရတယ် (Re-assignment) | ရှိပြီးသား data ထဲမှာတင် ပြင်လို့ရတယ် (Modification) |
| **နှိုင်းယှဉ်ခြင်း** | တန်ဖိုး (Value) အချင်းချင်း နှိုင်းယှဉ်တယ် | Memory address (Reference) အချင်းချင်း နှိုင်းယှဉ်တယ် |

### အရေးကြီးသော မှတ်ချက် (Side Effects)
Mutable data တွေကို သုံးတဲ့အခါ variable တစ်ခုကို ပြင်လိုက်ရင် အဲဒီ data ကို လှမ်းညွှန်ထားတဲ့ တခြား variable တွေမှာပါ လိုက်ပြောင်းသွားတတ်ပါတယ်။

```javascript
let arr1 = [1, 2, 3];
let arr2 = arr1; // address ကို share လုပ်လိုက်တာ

arr2.push(4); 

console.log(arr1); // [1, 2, 3, 4] ဖြစ်သွားမယ် (arr1 ကို မပြင်ပေမယ့် လိုက်ပြောင်းသွားတာပါ)
```

---

## ဘယ်ဟာကို သုံးသင့်သလဲ?

*   **Immutable** ကို သုံးခြင်းဖြင့် code ကို ပိုပြီး ခန့်မှန်းရလွယ်ကူစေပါတယ် (Predictable)။ State management (ဥပမာ - Redux, React) တွေမှာ Immutable ပုံစံကို အလေးပေး သုံးကြပါတယ်။
*   **Mutable** ကတော့ memory နေရာ အသစ်ထပ်မယူဘဲ ရှိပြီးသားနေရာမှာ ပြင်တဲ့အတွက် data အများကြီးနဲ့ အလုပ်လုပ်တဲ့အခါ (ဥပမာ - Large Arrays) performance ပိုကောင်းနိုင်ပါတယ်။

> [!TIP]
> JavaScript မှာ Object တွေကို Immutable ဖြစ်အောင် လုပ်ချင်ရင် `Object.freeze()` ကို အသုံးပြုနိုင်ပါတယ်။
