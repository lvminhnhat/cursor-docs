# ReactJS Project Development Standards with Tailwind CSS and Vite

Below are the clear standards and requirements for organizing and writing code in a ReactJS project using Tailwind CSS and Vite.

## 1. Folder Structure

Standard sample folder structure:

```plaintext
my-project/
├── public/              
├── src/                 
│   ├── assets/          
│   ├── components/      
│   ├── layouts/         
│   ├── pages/           
│   ├── hooks/           
│   ├── utils/           
│   ├── styles/          
│   ├── App.jsx          
│   └── main.jsx         
├── tailwind.config.js   
├── postcss.config.js    
├── vite.config.js       
├── package.json         
├── .gitignore           
└── README.md            
```

## 2. Code Convention

### 2.1. React (JSX/TSX)

* **Functional Components and Hooks:** Always use functional components combined with React Hooks (`useState`, `useEffect`).
* **One component per file:** Each component should be placed in a separate file with PascalCase naming.
* **Variable and function names:** Use camelCase. React components use PascalCase.
* **Concise JSX:** Avoid complex logic in JSX, extract into variables or separate functions.
* **Separation of concerns:** Each component should perform only one single task.
* **Custom Hooks:** Create custom hooks for reusable logic, starting with `use`.
* **Limit Prop Drilling:** Use Context API when data needs to be passed through multiple component levels.
* **Linting and Formatting:** Use ESLint and Prettier for consistent code formatting.

### 2.2. Tailwind CSS

* **Prioritize utility classes:** Limit manual CSS writing, prioritize using Tailwind classes.
* **Class ordering:** Order classes by group: layout → spacing → colors → typography.
* **Use shorthand:** Leverage shorthand classes like `mx-2`, `py-4`.
* **Limit `@apply` usage:** Only use when truly necessary, avoid losing Tailwind advantages.
* **Use design variables:** Define design tokens in `tailwind.config.js`.
* **Mobile-first and responsive:** Use prefixes like `sm:`, `md:` for responsive design.
* **Control CSS size:** Ensure Tailwind JIT scans source files correctly.

## 3. Vite Configuration

* **Project initialization:** Use command `npm create vite@latest`.
* **Tailwind CSS installation:**

  ```bash
  npm install -D tailwindcss @tailwindcss/vite postcss autoprefixer
  npx tailwindcss init -p
  ```
* **Configure `tailwind.config.js`:**

  ```js
  module.exports = {
    content: ["./src/**/*.{js,jsx,ts,tsx}"],
    theme: { extend: {} },
    plugins: [],
  }
  ```
* **Tailwind CSS file:**

  ```css
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
  ```
* **Vite configuration (`vite.config.js`):**

  ```js
  import { defineConfig } from 'vite';
  import react from '@vitejs/plugin-react';
  import tailwindcss from '@tailwindcss/vite';

  export default defineConfig({
    plugins: [react(), tailwindcss()],
  });
  ```

## 4. UI/UX Best Practices

* **Build Design System:** Define in `tailwind.config.js`.
* **Consistency:** Use utility classes consistently.
* **Reusable components:** Create separate components for complex UI elements.
* **Accessibility:** Ensure support for users with disabilities (ARIA, contrast, semantic HTML).
* **Responsive and Mobile-friendly:** Design with priority for good display on all devices.
* **Use UI kits:** Reference Tailwind UI, DaisyUI, Flowbite when appropriate.

## 5. Component, Hook, and State Organization

* **Group components:** Organize by function or feature (feature-based).
* **Local and global state:**

  * Local state used within components (`useState`).
  * Global state using Context API or libraries like Redux, Zustand.
* **Custom hooks:** Organize in `hooks/` folder.
* **Separate UI and logic:** Distinguish presentational components (dumb) and container components (smart).
* **Use Context wisely:** Avoid "provider hell", nest contexts appropriately and reasonably.
* **Configuration and constants:** Use separate files (`config.js`, `constants.js`).
* **Control re-renders:** Use `React.memo`, `useMemo`, and `useCallback`.
