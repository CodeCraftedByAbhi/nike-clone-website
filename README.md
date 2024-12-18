<h3 align="center">🚀 Nike Store Clone 🚀</h3>

## 📌 <a name="table">Table of Contents</a>

1. 🤖 [Introduction](#introduction)
2. ⚙️ [Tech Stack](#tech-stack)
3. 🔋 [Features](#features)
4. 🤸 [Quick Start](#quick-start)
5. 🔿 [Snippets](#snippets)
6. 🔗 [Links](#links)

## <a name="introduction">🤖 Introduction</a>

🎨🎯📦 The Nike Store Clone is a dynamic e-commerce web application built using React.js with Vite for fast development. The project is styled with Tailwind CSS, ensuring a modern and responsive design. The app mimics the look and feel of the official Nike store, offering a smooth user experience with engaging animations and hover effects.

Key features of the app include:

- **State Management**: Utilized React hooks such as `useState`, `useEffect`, `useReducer`, and `useRef` to manage different aspects of the app's functionality.
- **Cart Management with Redux**: Integrated Redux Toolkit to efficiently manage and update the cart state, ensuring a seamless shopping experience.
- **Notifications**: Added real-time notifications using React Hot Toast for actions like adding/removing items from the cart.
- **Dynamic UI**: Incorporated animation and hover effects to enhance interactivity and visual appeal.

🌟📱💻 This project demonstrates advanced React techniques, state management, and user-friendly UI, providing a smooth and dynamic shopping experience.

## <a name="tech-stack">⚙️ Tech Stack</a>

🔧🔑🛠️ - React.js
- Redux Toolkit
- Vite
- Tailwind CSS
- React Hot Toast

## <a name="features">🔋 Features</a>

☑️ **Responsive Design**: Fully responsive UI ensuring consistent experience across devices.

☑️ **Efficient State Management**: Optimized cart operations with Redux Toolkit.

☑️ **Interactive Notifications**: Real-time feedback for user actions via React Hot Toast.

☑️ **Engaging Animations**: Modern animations and hover effects to enhance the shopping experience.

## <a name="quick-start">🤸 Quick Start</a>

🛠️🚀📂 Follow these steps to set up the project locally on your machine.

### **Prerequisites**

Ensure you have the following installed:

- [Git](https://git-scm.com/) (Minimum version: 2.20.0)
- [Node.js](https://nodejs.org/en) (Minimum version: 14.0.0)
- [npm](https://www.npmjs.com/) (Node Package Manager, Minimum version: 6.0.0)

### **Cloning the Repository**

```bash
git clone https://github.com/your-username/nike-store-clone.git
cd nike-store-clone
```

### **Installation**

Before running the following command, ensure the following environment variables are correctly configured if applicable:

- `NODE_ENV` for the environment setup (e.g., `development`, `production`).

Install the project dependencies using npm:

```bash
npm install
```

### **Running the Project**

```bash
npm run dev
```

🌐📖🖥️ Open [http://localhost:5173](http://localhost:5173) in your browser to view the project.

## <a name="snippets">🔿 Snippets</a>

<details>
<summary><code>tailwind.config.js</code></summary>

```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"], // The paths defined here specify the files Tailwind CSS should scan for class usage. "./index.html" is for the main HTML file, and "./src/**/*.{js,ts,jsx,tsx}" includes all JavaScript and TypeScript files in the src directory to cover dynamic class usage in components.
  theme: {
    extend: {
      colors: {
        black: "#111",
        white: "#fff",
        gray: {
          light: "#f5f5f5",
          DEFAULT: "#d4d4d4",
          dark: "#a3a3a3",
        },
        red: "#e3342f",
      },
    },
  },
  plugins: [],
};
```

</details>

<details>
<summary><code>store/cartSlice.js</code></summary>

```javascript
import { createSlice } from '@reduxjs/toolkit';

const initialState = {
  items: [],
  totalAmount: 0,
};

// The cartSlice manages the shopping cart's state in the Redux store, including items and the total amount. It plays a crucial role in providing state management for the e-commerce functionalities of this project.
const cartSlice = createSlice({
  name: 'cart',
  initialState,
  reducers: {
    addItem: (state, action) => {
      state.items.push(action.payload);
      state.totalAmount += action.payload.price;
    },
    removeItem: (state, action) => {
      const index = state.items.findIndex(item => item.id === action.payload.id);
      if (index !== -1) {
        state.totalAmount -= state.items[index].price;
        state.items.splice(index, 1);
      }
    },
  },
});

export const { addItem, removeItem } = cartSlice.actions;
export default cartSlice.reducer;
```

</details>

## <a name="links">🔗 Links</a>

🔗🔍🌍 - [Live Demo](https://nike-clone-website-six.vercel.app/)


