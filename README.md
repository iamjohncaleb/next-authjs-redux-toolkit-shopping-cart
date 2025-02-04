# 🛒 Next.js Shopping Cart with NextAuth.js & Redux Toolkit  

This is a fully functional **shopping cart** application built with **Next.js, Redux Toolkit, and NextAuth.js**. The project demonstrates **state management, authentication, and e-commerce functionality** in a modern web stack.  

---

## 🚀 Features  

✅ **User Authentication**: Secure login with NextAuth.js (Google, GitHub, or custom credentials)  
✅ **Redux Toolkit**: Efficient state management for the shopping cart  
✅ **Cart Persistence**: Items remain in the cart even after page reload  
✅ **Product Management**: Display product listings with dynamic routes  
✅ **Add/Remove from Cart**: Update cart in real-time with Redux  
✅ **Checkout Process**: Simulated checkout flow with Stripe integration (optional)  
✅ **Responsive Design**: Optimized for mobile and desktop  

---

## 🛠 Tech Stack  

- **Frontend**: [Next.js](https://nextjs.org/), React, Tailwind CSS  
- **State Management**: Redux Toolkit  
- **Authentication**: NextAuth.js  
- **Database (Optional)**: MongoDB / PostgreSQL  
- **Payment Integration (Optional)**: Stripe  

---

## 📦 Installation & Setup  

### **1. Clone the Repository**  

git clone https://github.com/yourusername/nextjs-shopping-cart.git
cd nextjs-shopping-cart


### **2. Install Dependencies**  

npm install
# or
yarn install


### **3. Set Up Environment Variables**  
Create a `.env.local` file in the root directory and add the following:  

NEXTAUTH_SECRET=your_secret_key
NEXTAUTH_URL=http://localhost:3000
GITHUB_CLIENT_ID=your_github_client_id
GITHUB_CLIENT_SECRET=your_github_client_secret
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
STRIPE_SECRET_KEY=your_stripe_secret_key (optional)


### **4. Start the Development Server**  

npm run dev
# or
yarn dev

Visit [http://localhost:3000](http://localhost:3000) in your browser.  

---

## 📂 Folder Structure  

├── app                // Next.js app directory
│   ├── components     // Reusable UI components
│   ├── features       // Redux slices (cartSlice.js, authSlice.js)
│   ├── hooks          // Custom hooks (useCart, useAuth)
│   ├── pages          // Next.js pages (Home, Cart, Auth)
│   ├── public         // Static assets
│   ├── styles         // Global styles
│   ├── utils          // Helper functions
│   ├── api            // (Optional) API routes for checkout
├── store.js           // Redux store setup
└── README.md          // Project documentation


## 🔥 Redux Toolkit Cart Implementation  

**Cart Slice (Redux State Management):**  

import { createSlice } from "@reduxjs/toolkit";

const initialState = {
  cartItems: [],
  totalPrice: 0,
};

export const cartSlice = createSlice({
  name: "cart",
  initialState,
  reducers: {
    addToCart: (state, action) => {
      const existingItem = state.cartItems.find(item => item.id === action.payload.id);
      if (existingItem) {
        existingItem.quantity += 1;
      } else {
        state.cartItems.push({ ...action.payload, quantity: 1 });
      }
      state.totalPrice += action.payload.price;
    },
    removeFromCart: (state, action) => {
      state.cartItems = state.cartItems.filter(item => item.id !== action.payload.id);
      state.totalPrice -= action.payload.price;
    },
  },
});

export const { addToCart, removeFromCart } = cartSlice.actions;
export default cartSlice.reducer;


## 🔗 Deployment  

- **Hosting**: [Vercel](https://vercel.com/) (Recommended)  
- **Database**: Supabase / Prisma with PostgreSQL  
- **Environment Variables**: Add `.env` variables in the deployment dashboard  

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:
Let me know if you'd like adjustments or additional sections! 😊

1. Fork this repository.
2. Create a branch for your feature or bug fix.
3. Submit a pull request with a detailed description of your changes.

---

### License
This project is licensed under the [MIT License](LICENSE).

---

Let me know if you'd like to refine it further! 🚀
- Name: Caleb John
- Email: [My-email](mailto:johncaleb022@gmail.com)  
- LinkedIn: [My LinkedIn](https://www.linkedin.com/in/caleb-john-48a1bb29a)
