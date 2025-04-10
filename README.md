# 🚀 Subscription Modal – Vue 3 + SCSS

A clean, responsive subscription modal designed to make plan selection easier and more intuitive.

---

## 🧠 Why

While using **Reedsy Studio**, I found the plan presentation a bit confusing. It wasn’t immediately clear what was included in each plan, and I felt that this could potentially hurt conversion.

This project is my attempt to reimagine the UX of a subscription modal — to reduce cognitive load, make value obvious, and encourage upgrade decisions.

---

## 🧩 Assumptions

- **Essentials** is the foundation and always selected by default — users shouldn't have to choose it.
- Users can pick **one additional plan** to upgrade with (`Craft`, `Outline`, or `Craft + Outline`).
- The more clearly we show value (especially visually), the higher the chances of conversion.
- **Dark mode is not a real selling point** — it’s a nice-to-have, not a core value prop — so it’s included in the free plan.
- These assumptions should be validated — the ideal next step would be to run **A/B tests** and measure what actually drives upgrades.

---

## 🎯 UX Goals

- ✅ Communicate upgrade value visually and quickly
- ✅ Reduce friction: no need to choose a base plan
- ✅ Pair emojis + features for fast comprehension
- ✅ Highlight differences between plans at a glance
- ✅ Keep layout clean and mobile-first
- ✅ Avoid feature bloat in messaging

---

## 🚀 Next Steps

- **Accessibility Improvements**: Ensure the modal is fully accessible, including keyboard navigation and screen reader support.
- **Analytics Integration**: Add tracking to measure user interactions and conversion rates.
- **Localization**: Support multiple languages to reach a broader audience.
- **Performance Optimization**: Optimize assets and code for faster load times.
- **Dark Mode Support**: Add a toggle for users who prefer dark mode, even if it's not a core selling point.
- **User Feedback**: Collect feedback from real users to iterate and improve the design.

---

## 🔧 Tech Stack

- **Vue 3** + TypeScript (Composition API)
- **SCSS** for modular styles
- **Vite** for fast development and build tooling
- **ESLint** + **Prettier** for code quality and formatting
- **Jest** for unit testing
- **Responsive** design
- **GitHub Actions** for CI/CD

---

## 📦 Features

- ✅ Always-included `Essentials` plan (pre-selected)
- ✅ Select one upgrade plan (`Craft`, `Outline`, or both)
- ✅ Dynamic feature lists with emoji ✨
- ✅ Disabled "Start free trial" button until a plan is selected
- ✅ Responsive design for all screen sizes

---

## TODO

- Add unit tests
- Write end-to-end tests to validate user flows
- Implement error handling for edge cases
- Explore integration with third-party analytics tools

---

## 🛠 Setup

```bash
npm install
npm run dev
```
