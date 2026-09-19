# 🛍️ ShopEase — E-Commerce Web App with AI Shopping Assistant

A responsive, multi-page e-commerce web app with UPI payment checkout, an admin dashboard for order and product management, and a built-in AI shopping assistant. Built with vanilla HTML, CSS, and JavaScript — no frameworks, no build step.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

**🔗 [Live Demo](https://lingeshwaran-j.github.io/ShopEase/)**

<!--
SCREENSHOTS — add 3–4 images to a /screenshots folder, then delete this comment line and the closing arrow below.

## 📸 Screenshots

| Home | Product Catalog |
|------|-----------------|
| ![Home](screenshots/home.png) | ![Products](screenshots/products.png) |

| AI Assistant | Admin Dashboard |
|--------------|-----------------|
| ![Chatbot](screenshots/chatbot.png) | ![Admin](screenshots/admin.png) |
-->

---

## ✨ Features

### Customer
- Browse a product catalog across 4 categories (Electronics, Fashion, Home & Kitchen, Sports) with live search and category filters
- Product detail pages with ratings, badges (Best Seller, New, Hot, Sale, Limited), and related products
- Shopping cart with quantity controls, persisted between visits
- Checkout flow with shipping details and an order summary
- **UPI payment**: dynamically generated UPI QR code for the exact order amount, followed by UTR (transaction reference) submission
- Order history with status tracking (Awaiting Payment → Payment Submitted → Confirmed → Shipped → Delivered)
- Fully responsive layout for desktop, tablet, and mobile

### Admin Dashboard
- Overview stats: total orders, pending UTR verifications, shipped/delivered counts, and verified revenue
- Verify or reject customer UTR payments
- Update order status through the full fulfilment lifecycle
- Add, edit, and delete products (including image upload)
- Configure the store's UPI ID
- Role-based access: admin pages are only available to the admin account

### 🤖 AI Shopping Assistant
- Floating chat widget available on every page
- Finds products by name, category, or budget (e.g. *"show me headphones under 30000"*)
- Tracks orders by order number (e.g. *ORD-20240401-001*) or lists the logged-in user's recent orders
- Answers store FAQs: shipping, returns, payment, and support
- Recommends top-rated products
- Uses the store's live product and order data, so answers always match what's on the site

---

## 🧰 Tech Stack

| Area | Technology |
|------|------------|
| Markup & Styling | HTML5, CSS3 (Grid, Flexbox, custom properties, media queries) |
| Logic | Vanilla JavaScript (ES6+), client-side page router |
| Data Persistence | Browser `localStorage` |
| Payments | UPI deep-link QR codes via [QR Server API](https://goqr.me/api/) |
| Fonts & Images | Google Fonts (DM Sans), Pexels product images |

---

## 🔑 Demo Accounts

> ⚠️ These credentials are for **demo purposes only**. Authentication in this project runs entirely in the browser and is not secure for production use.

| Role | Email | Password |
|------|-------|----------|
| Customer | `rohan@shopease.in` | `rohan123` |
| Customer | `priya@shopease.in` | `priya123` |
| Admin | `admin@shopease.in` | `admin123` |

---

## 🚀 Getting Started

No installation or build tools required.

```bash
# 1. Clone the repository
git clone https://github.com/lingeshwaran-j/ShopEase.git

# 2. Open the project folder
cd ShopEase

# 3. Open index.html in your browser
```

Or simply download `index.html` and double-click it.

---

## 🧠 How the AI Assistant Works

The assistant is a **rule-based conversational engine** that runs fully in the browser:

1. **Intent detection** — regex and keyword matching classify each message (greeting, order tracking, budget search, category browsing, FAQ, etc.)
2. **Data lookup** — product and order queries are matched against the store's live data
3. **Response rendering** — results are returned as chat messages with clickable product cards

It also includes an optional hook (`CHAT_CONFIG` and `askLLM()`) to connect a real LLM through a backend endpoint. If that call is unavailable or not configured, the built-in assistant answers instead, so the chat never goes silent.

> 🔐 Never place a secret API key directly in client-side code. Route LLM calls through your own backend.

---

## ⚠️ Current Limitations

- Data (users, cart, orders, products) lives in `localStorage`, so it is per-browser and not shared across devices
- Login uses hardcoded demo accounts with no real backend authentication
- UPI payments are verified manually by the admin via the UTR number; there is no automated payment confirmation

## 🗺️ Planned Improvements

- [ ] Backend with Node.js/Express or Spring Boot and a real database
- [ ] JWT-based authentication with user registration
- [ ] Payment gateway integration with automated verification
- [ ] Connect the assistant to an LLM through a secure backend proxy
- [ ] Split the single file into modular components (or migrate to React)
- [ ] Unit tests and CI with GitHub Actions

---

## 📚 What I Learned

This was my first full project. It helped me practice:

- Structuring a multi-page app and building a client-side router without a framework
- Managing application state and persistence with `localStorage`
- Designing role-based flows (customer vs. admin) and an order lifecycle
- Building responsive layouts with CSS Grid, Flexbox, and media queries
- Writing intent-matching logic for a conversational assistant
- Escaping user input to prevent XSS in dynamically rendered HTML

---

## 👤 Author

**Lingeshwaran J**
B.E. Computer Science, Erode Sengunthar Engineering College

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/lingeshwaranj)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/lingeshwaran-j)
[![LeetCode](https://img.shields.io/badge/LeetCode-FFA116?style=flat&logo=leetcode&logoColor=black)](https://leetcode.com/u/Lingeshwaran-dev)

If you found this project useful, consider giving it a ⭐
