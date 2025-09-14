# React Side Effects

##  Side Effect কী?
React কম্পোনেন্টের মূল কাজ হলো `props` আর `state` থেকে UI রেন্ডার করা।  
কিন্তু যখন কোনো কম্পোনেন্ট **UI রেন্ডারের বাইরে** কিছু করে, সেটাকেই **Side Effect** বলা হয়।  

---

##  সাধারণ উদাহরণ
- API থেকে ডেটা ফেচ করা  
- `localStorage` এ ডেটা রাখা  
- ব্রাউজারের `document.title` পরিবর্তন করা  
- `setInterval` / `setTimeout` ব্যবহার করা  
- ইভেন্ট লিসেনার যোগ/সরানো  

---

##  React এ কিভাবে করা হয়?
Functional Component এ side effect হ্যান্ডল করার জন্য `useEffect` হুক ব্যবহার করা হয়।

```jsx
import { useEffect } from "react";

function MyComponent() {
  useEffect(() => {
    console.log("Component mounted!");

    return () => {
      console.log("Cleanup on unmount!");
    };
  }, []); // dependency array
}

