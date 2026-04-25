# Big O Notation 

Big O notation is a mathematical notation that describes the limiting behavior of a function when the argument tends towards a particular value or infinity. In Computer Science, it's used to classify algorithms according to how their run time or space requirements grow as the input size ($n$) grows.

Computer Science မှာ Big O notation ကို algorithm တစ်ခုရဲ့ စွမ်းဆောင်ရည် (performance) ကို တိုင်းတာဖို့ သုံးပါတယ်။ အဓိကအားဖြင့် Input size ($n$) များလာရင် အလုပ်လုပ်ရတဲ့ အချိန် (Time) ဒါမှမဟုတ် နေရာယူမှု (Space) က ဘယ်လောက်အထိ တိုးလာမလဲဆိုတာကို ဖော်ပြတာ ဖြစ်ပါတယ်။


---

## 1. Analysis Types 

Algorithm တစ်ခုကို ခွဲခြမ်းစိတ်ဖြာတဲ့အခါ သင်္ကေတ ၃ မျိုးကို အဓိက တွေ့ရတတ်ပါတယ် -

*   **Big O ($O$):** Worst Case Scenario (အဆိုးဆုံး အခြေအနေ) - ဒါက ကျနော်တို့ အမြဲတမ်း အဓိကထား ကြည့်ရတဲ့ အရာပါ။ Algorithm တစ်ခုက ဒီထက်တော့ ပိုမကြာတော့ဘူးလို့ အာမခံချက် ပေးတာပါ။
*   **Big Omega ($\Omega$):** Best Case Scenario (အကောင်းဆုံး အခြေအနေ) - အမြန်ဆုံး အလုပ်လုပ်နိုင်တဲ့ အချိန်ပါ။
*   **Big Theta ($\Theta$):** Average Case Scenario (ပျမ်းမျှ အခြေအနေ) - များသောအားဖြင့် ဖြစ်တတ်တဲ့ အရှိန်ပါ။

---

## 2. Common Complexity Classes (အတွေ့ရများသော ရှုပ်ထွေးမှုများ)

### $O(1)$ - Constant Time (ကိန်းသေ အချိန်)
Input size ($n$) ဘယ်လောက်ပဲ ရှိရှိ၊ အလုပ်လုပ်တဲ့ အဆင့်အရေအတွက်က အမြဲတမ်း အတူတူပဲ ဖြစ်နေတာပါ။

```javascript
function getFirstItem(array) {
  return array[0]; // array ထဲမှာ ၁ သန်း ရှိရှိ၊ ၁၀ ခု ရှိရှိ ပထမဆုံးအချက်အလက်ကို တစ်ခါတည်းနဲ့ ယူနိုင်ပါတယ်။
}
```

### $O(\log n)$ - Logarithmic Time (လော့ဂရစ်သမ် အချိန်)
Data ပမာဏ တိုးလာပေမယ့် အလုပ်လုပ်ရတဲ့ အဆင့်က တဖြည်းဖြည်းချင်းပဲ တိုးတာပါ။ Data တွေကို တစ်ဝက်စီ ခွဲခွဲပြီး ရှာတဲ့ algorithm တွေမှာ တွေ့ရပါတယ်။

```javascript
// Binary Search Example
function binarySearch(arr, target) {
  let left = 0;
  let right = arr.length - 1;

  while (left <= right) {
    let mid = Math.floor((left + right) / 2);
    if (arr[mid] === target) return mid;
    
    if (arr[mid] < target) left = mid + 1;
    else right = mid - 1;
  }
  return -1;
}
```

### $O(n)$ - Linear Time (မျဉ်းဖြောင့် အချိန်)
Input size တစ်ခု တိုးလာရင် အလုပ်လုပ်ရတဲ့ အဆင့်တစ်ခု တိုးလာတာမျိုးပါ။ Data ပမာဏနဲ့ အလုပ်လုပ်ချိန်က တိုက်ရိုက် အချိုးကျပါတယ်။

```javascript
function findItem(arr, target) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === target) return i; // element တိုင်းကို loop တစ်ခါ ပတ်ပြီး စစ်တာမို့ O(n) ပါ။
  }
  return -1;
}
```

### $O(n \log n)$ - Linearithmic Time
ဒါကတော့ ထိရောက်တဲ့ Sorting algorithm တွေ (ဥပမာ- Merge Sort, Quick Sort) မှာ တွေ့ရတတ်ပါတယ်။ $O(n)$ ထက် နည်းနည်း ပိုကြာပေမယ့် $O(n^2)$ ထက် အများကြီး ပိုမြန်ပါတယ်။


### $O(n^2)$ - Quadratic Time (နှစ်ထပ်ကိန်း အချိန်)
Loop တစ်ခုထဲမှာ နောက်ထပ် loop တစ်ခု ထပ်ပတ်တဲ့ အခါမျိုးမှာ ဖြစ်ပါတယ်။ Data ပမာဏ များလာရင် အလုပ်လုပ်ရတဲ့ အချိန်က အဆမတန် များလာပါတယ်။

```javascript
function printAllPairs(arr) {
  for (let i = 0; i < arr.length; i++) {
    for (let j = 0; j < arr.length; j++) {
      console.log(arr[i], arr[j]); // n * n ကြိမ် အလုပ်လုပ်မှာမို့ O(n^2) ဖြစ်ပါတယ်။
    }
  }
}
```

### $O(2^n)$ - Exponential Time (အညွှန်းကိန်း အချိန်)
Input size နည်းနည်းလေး တိုးတာနဲ့ အလုပ်လုပ်ချိန်က နှစ်ဆစီ မြင့်တက်သွားတာပါ။ မသုံးသင့်ဆုံး algorithm မျိုးတွေ ဖြစ်ပါတယ်။

```javascript
// Recursive Fibonacci Example
function fibonacci(n) {
  if (n <= 1) return n;
  return fibonacci(n - 1) + fibonacci(n - 2); // logic တစ်ခုစီအတွက် နောက်ထပ် recursion နှစ်ခု ထပ်ခေါ်နေလို့ O(2^n) ဖြစ်ပါတယ်။
}
```

---

## 3. Space Complexity (နေရာယူမှု ရှုပ်ထွေးမှု)

Space Complexity is the amount of memory an algorithm needs to run to completion as a function of the input size ($n$). 

Algorithm တစ်ခု အလုပ်လုပ်ပြီးဆုံးဖို့အတွက် Computer ရဲ့ memory (RAM) ကို ဘယ်လောက် အသုံးပြုသလဲဆိုတာကို **Space Complexity** လို့ ခေါ်ပါတယ်။ သူကလည်း Input size ($n$) အပေါ်မှာပဲ မူတည်ပါတယ်။

### Key Concepts (အဓိက သဘောတရားများ)

*   **Fixed Space:** Memory that is always the same (e.g., constants, variables). (Data ဘယ်လောက်ပဲ ဖြစ်ဖြစ် အမြဲတမ်း ပုံသေ ယူထားတဲ့ နေရာ။)
*   **Auxiliary Space:** Extra or temporary space used by the algorithm. (Algorithm အလုပ်လုပ်နေတုန်း ခဏတာ ထပ်တိုး သုံးစွဲတဲ့ နေရာ။)

---

### Space Complexity Examples (ဥပမာများ)

#### $O(1)$ Space - Constant Space
Memory usage does not increase with input size.
Input data ဘယ်လောက်များများ၊ memory သုံးစွဲမှုက အမြဲတမ်း အတူတူပဲ ဖြစ်နေတာပါ။

```javascript
function swap(a, b) {
  let temp = a; // variable တစ်ခုပဲ ထပ်သုံးထားလို့ memory နေရာ အသစ် အများကြီး မယူပါဘူး။
  a = b;
  b = temp;
}
```

#### $O(n)$ Space - Linear Space
Memory usage increases linearly with the input size.
Input data များလာရင် memory နေရာယူမှုကလည်း လိုက်ပြီး များလာတာပါ။ (ဥပမာ- Data အသစ်တွေကို စာရင်းအသစ်တစ်ခုမှာ သိမ်းလိုက်တဲ့အခါမျိုး)

```javascript
function createArray(n) {
  let newArr = [];
  for (let i = 0; i < n; i++) {
    newArr.push(i); // n အရေအတွက်အလိုက် item တွေကို သိမ်းထားရမှာမို့ memory နေရာ n ခု ယူသွားပါလိမ့်မယ်။
  }
  return newArr;
}
```
### Note (မှတ်သားရန်)

* Primitives (Boolean, Number, Undefined, Null): ဒါတွေက များသောအားဖြင့် $O(1)$ space ယူပါတယ်။

* Strings, Arrays, Objects: ဒါတွေကတော့ သူတို့ရဲ့ length သို့မဟုတ် key အရေအတွက်အလိုက် $O(n)$ space ယူပါတယ်။

* Trade-off: တချို့နေရာတွေမှာ အချိန် (Time) မြန်အောင်လုပ်ဖို့အတွက် Memory (Space) ကို ပိုသုံးရတတ်ပါတယ်။ ဒါကို Time-Space Trade-off လို့ ခေါ်ပါတယ်။

---




## 4. Time-Space Trade-off (အချိန်နှင့် နေရာ အပေးအယူ)

Sometimes, we can make an algorithm run faster (less Time) by using more memory (more Space), or use less memory by being slower. A good developer knows how to balance these two based on the environment (e.g., a phone with limited RAM vs. a server).

တစ်ခါတလေမှာ Algorithm တစ်ခုကို ပိုမြန်အောင် လုပ်ဖို့အတွက် Memory ပိုသုံးရတတ်သလို၊ Memory သက်သာအောင် လုပ်ရင်တော့ အချိန် ပိုကြာသွားတတ်ပါတယ်။ ဒါကို **Time-Space Trade-off** လို့ ခေါ်ပါတယ်။ Developer တစ်ယောက်အနေနဲ့ ကိုယ့် App က ဘယ်နေရာမှာ အလုပ်လုပ်မှာလဲ (ဥပမာ- RAM နည်းတဲ့ ဖုန်းမှာလား၊ ဒါမှမဟုတ် စွမ်းအားမြင့်တဲ့ Server မှာလား) ဆိုတာအပေါ် မူတည်ပြီး နှစ်ခုကြားမှာ မျှတအောင် ရွေးချယ်ရပါတယ်။

---


## 5. Big O Complexity Chart

| Complexity | Name | Growth Rate |
| :--- | :--- | :--- |
| **$O(1)$** | Constant | Stable (အမြဲငြိမ်) |
| **$O(\log n)$** | Logarithmic | Very Slow Growth (အရမ်းနှေး) |
| **$O(n)$** | Linear | Steady Growth (မှန်မှန်တက်) |
| **$O(n \log n)$** | Linearithmic | Decent (သင့်တင့်) |
| **$O(n^2)$** | Quadratic | Fast Growth (အရမ်းမြန်) |
| **$O(2^n)$** | Exponential | Very Fast Growth (အမြန်ဆုံး) |

---

## Conclusion 

Big O ကို သိထားခြင်းအားဖြင့် ကိုယ်ရေးလိုက်တဲ့ code က Data များလာရင် ဘာဖြစ်သွားမလဲဆိုတာကို ကြိုတင်ခန့်မှန်းနိုင်ပါတယ်။ Developer ကောင်းတစ်ယောက် ဖြစ်ဖို့ဆိုရင် အချိန်နဲ့ နေရာ သက်သာစေမယ့် $O(1)$, $O(\log n)$ ဒါမှမဟုတ် $O(n)$ algorithm တွေကို ဦးစားပေး သုံးတတ်ဖို့ လိုအပ်ပါတယ်။
