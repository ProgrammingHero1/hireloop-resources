# HireLoop — Framer Motion গাইড
---

## Framer Motion কী?

Framer Motion হলো React-এর জন্য একটি **animation library**। সহজ কথায়, এটি দিয়ে তুমি যেকোনো HTML element-কে নাড়াচাড়া করাতে পারো — যেমন fade in, slide up, hover effect ইত্যাদি — মাত্র কয়েকটা prop লিখে।

---

## ইনস্টলেশন

```bash
npm install framer-motion
```

এই প্রজেক্টে ইতিমধ্যে `package.json`-এ add করা আছে:

```json
"framer-motion": "^12.40.0"
```

---

## Import করার নিয়ম

```jsx
import { motion } from 'framer-motion';
```

`motion` হলো Framer Motion-এর মূল জিনিস। যেকোনো সাধারণ HTML tag-এর আগে `motion.` লাগালেই সেটা animate করা যায়।

| সাধারণ HTML | Framer Motion version |
|---|---|
| `<div>` | `<motion.div>` |
| `<section>` | `<motion.section>` |
| `<button>` | `<motion.button>` |

---

## এই প্রজেক্টে কোথায় কোথায় ব্যবহার হয়েছে

### ১. `FeaturesSection.jsx`
### ২. `Pricing.jsx`

---

## মূল Concepts — সহজ ভাষায়

### ১. `initial` — শুরুর অবস্থা

Element টি প্রথমে কেমন দেখাবে সেটা বলে দেয়।

```jsx
<motion.div initial={{ opacity: 0, y: 30 }}>
```

এখানে:
- `opacity: 0` → element টি সম্পূর্ণ অদৃশ্য থাকবে
- `y: 30` → element টি ৩০px নিচে থাকবে

---

### ২. `animate` / `whileInView` — শেষের অবস্থা

Element টি কোথায় গিয়ে থামবে সেটা বলে দেয়।

```jsx
<motion.div
  initial={{ opacity: 0, y: 30 }}
  whileInView={{ opacity: 1, y: 0 }}
>
```

`whileInView` মানে — **যখন element টি screen-এ দেখা যাবে, তখন animate হবে।** Page scroll করলে এই effect দেখা যায়।

---

### ৩. `transition` — কতটা সময় লাগবে

Animation কতক্ষণ ধরে চলবে এবং কেমন গতিতে চলবে সেটা বলে দেয়।

```jsx
transition={{ duration: 0.6, ease: [0.22, 1, 0.36, 1] }}
```

- `duration: 0.6` → ০.৬ সেকেন্ড সময় লাগবে
- `ease` → animation-এর গতির ধরন (শুরুতে ধীরে, শেষে দ্রুত)

---

### ৪. `viewport` — কখন trigger হবে

```jsx
viewport={{ once: true, amount: 0.2 }}
```

- `once: true` → animation মাত্র একবারই চলবে, বারবার না
- `amount: 0.2` → element-এর ২০% screen-এ দেখা গেলেই animation শুরু হবে

---

### ৫. `variants` — animation গুলো আলাদা করে সাজানো

বড় বড় animation বারবার লেখার বদলে একটা object-এ সংরক্ষণ করা যায়।

এই প্রজেক্টে এভাবে ব্যবহার হয়েছে:

```jsx
// FeaturesSection.jsx এবং Pricing.jsx-এ
const fadeInUp = {
  initial: { opacity: 0, y: 30 },
  whileInView: { opacity: 1, y: 0 },
  viewport: { once: true, amount: 0.2 },
  transition: { duration: 0.6, ease: [0.22, 1, 0.36, 1] },
};

// ব্যবহার করার সময়
<motion.div {...fadeInUp}>
  কন্টেন্ট এখানে
</motion.div>
```

`{...fadeInUp}` মানে হলো object-এর সব property গুলো একসাথে spread করে দেওয়া।

---

### ৬. `staggerChildren` — একটার পর একটা animate করা

একটা parent-এর ভেতরে অনেক child element থাকলে, সেগুলো একসাথে না এসে একটার পর একটা আসবে।

```jsx
const staggerContainer = {
  initial: { opacity: 0 },
  whileInView: { opacity: 1 },
  transition: {
    staggerChildren: 0.08,  // প্রতিটা child ০.০৮ সেকেন্ড পরে আসবে
    delayChildren: 0.1,     // প্রথম child আসার আগে ০.১ সেকেন্ড অপেক্ষা
  },
};
```

এই প্রজেক্টে Features grid এবং Pricing cards এভাবে একটার পর একটা animate হয়।

---

### ৭. `whileHover` — mouse hover করলে কী হবে

```jsx
// FeaturesSection.jsx-এ feature card hover
<motion.div
  whileHover={{ y: -4 }}
  transition={{ type: "spring", stiffness: 300, damping: 20 }}
>
```

Mouse রাখলে card টি ৪px উপরে উঠে যাবে।

```jsx
// Pricing.jsx-এ button hover
<motion.button
  whileHover={{ x: 4 }}
>
```

Mouse রাখলে button টি ৪px ডানে সরে যাবে।

---

### ৮. `type: "spring"` — স্প্রিং-এর মতো নাড়াচাড়া

```jsx
transition={{ type: "spring", stiffness: 300, damping: 20 }}
```

- `type: "spring"` → animation টি একটা স্প্রিং-এর মতো একটু bounce করবে
- `stiffness: 300` → স্প্রিং কতটা শক্ত (বেশি হলে দ্রুত)
- `damping: 20` → bounce কতটা কমবে (বেশি হলে কম bounce)

---

## সম্পূর্ণ উদাহরণ — FeaturesSection.jsx থেকে

```jsx
// ১. Import
import { motion } from 'framer-motion';

// ২. Animation object তৈরি
const fadeInUp = {
  initial: { opacity: 0, y: 30 },       // শুরুতে অদৃশ্য, নিচে
  whileInView: { opacity: 1, y: 0 },    // দেখা গেলে স্বাভাবিক হবে
  viewport: { once: true },
  transition: { duration: 0.6 },
};

// ৩. ব্যবহার
<motion.section
  initial={{ opacity: 0 }}
  whileInView={{ opacity: 1 }}
  viewport={{ once: true }}
  transition={{ duration: 0.5 }}
>
  <motion.h2 {...fadeInUp}>
    Everything you need to succeed
  </motion.h2>

  {features.map((feature, index) => (
    <motion.div
      key={index}
      {...fadeInUp}
      whileHover={{ y: -4 }}            // hover করলে উপরে উঠবে
    >
      {feature.title}
    </motion.div>
  ))}
</motion.section>
```

---

## সংক্ষেপে মনে রাখার উপায়

| Prop | কাজ | উদাহরণ |
|---|---|---|
| `initial` | শুরুর অবস্থা | `{ opacity: 0, y: 30 }` |
| `animate` | সরাসরি animate | `{ opacity: 1, y: 0 }` |
| `whileInView` | scroll করে দেখা গেলে animate | `{ opacity: 1, y: 0 }` |
| `whileHover` | hover করলে animate | `{ y: -4 }` |
| `transition` | সময় ও গতি | `{ duration: 0.6 }` |
| `viewport` | কখন trigger হবে | `{ once: true }` |
| `variants` | animation object আলাদা রাখা | `{...fadeInUp}` |

---

## গুরুত্বপূর্ণ নোট

- `"use client"` directive অবশ্যই দিতে হবে, কারণ Framer Motion browser-এ চলে, server-এ না।
- `whileInView` ব্যবহার করলে `viewport={{ once: true }}` দেওয়া ভালো, নাহলে scroll করলে বারবার animate হবে।

---
