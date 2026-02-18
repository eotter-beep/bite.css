# 📘 **bite.css Documentation — Theme & Header System**

bite.css provides a lightweight theming system and a flexible Adobe‑style top navigation layout. This page documents the variables, dark‑mode behavior, and header structure.

---

# 🎨 1. Theme Variables

bite.css defines global CSS variables that control colors, spacing, typography, and component behavior.

```css
:root {
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;

  /* Core theme */
  --bg: white;
  --text: black;

  /* Buttons */
  --button-bg: black;
  --button-text: white;
  --button-hover-bg: white;
  --button-hover-text: black;

  /* Header + layout */
  --accent-bg: #f5f5f5;
  --accent-text: black;
  --accent: #ddd;

  --border: #ccc;
  --border-width: 1px;
  --content-width: 60ch;
  --standard-border-radius: 4px;

  --fade-speed: 0.3s;
}
```

These variables allow consistent styling across components and make theme customization simple.

---

# 🌙 2. Automatic Dark Mode

bite.css automatically adapts to the user’s system theme using `prefers-color-scheme`.

```css
@media (prefers-color-scheme: dark) {
  :root {
    --bg: #111;
    --text: #eee;

    --button-bg: #eee;
    --button-text: #111;
    --button-hover-bg: #333;
    --button-hover-text: #fff;

    --accent-bg: #222;
    --accent-text: #fff;
    --accent: #444;

    --border: #555;
  }
}
```

Dark mode overrides only the variables that need to change, keeping the rest of the system consistent.

---

# 📄 3. Global Layout

The body uses a centered, readable layout with smooth theme transitions.

```css
body { 
  width: 50%;
  margin: 0 auto;
  background-color: var(--bg); 
  color: var(--text); 
  transition: background-color var(--fade-speed), color var(--fade-speed);
  padding: 0;
}
```

---

# 🔘 4. Buttons

Buttons in bite.css are minimalist, theme‑aware, and fully unstyled by default.

```css
button {
  all: unset;
  background-color: var(--button-bg);
  color: var(--button-text);
  border-radius: var(--standard-border-radius);
  padding: 4px 8px;
  cursor: pointer;
  transition: background-color var(--fade-speed), color var(--fade-speed);
}

button:hover {
  background-color: var(--button-hover-bg);
  color: var(--button-hover-text);
}
```

---

# 🟥 5. Adobe‑Style Header Layout

bite.css includes a flexible top navigation bar inspired by Adobe’s clean, product‑focused layout.

### ✔ Features:
- Logo on the left  
- Centered navigation links  
- Utility actions on the right  
- Fully responsive flexbox layout  
- Theme‑aware colors  

```css
body > header {
  background-color: var(--accent-bg);
  border-bottom: var(--border-width) solid var(--border);
  color: var(--accent-text);

  display: flex;
  align-items: center;
  justify-content: space-between;

  padding: 0.75rem 1.5rem;
  grid-column: 1 / -1;
}
```

---

## 🔻 5.1 Logo

```css
header .logo {
  font-size: 1.4rem;
  font-weight: bold;
  color: var(--accent-text);
}
```

---

## 📚 5.2 Main Navigation

```css
header nav {
  flex: 1;
  display: flex;
  justify-content: center;
}

header nav ul {
  list-style: none;
  display: flex;
  gap: 1.5rem;
  margin: 0;
  padding: 0;
}

header nav a {
  text-decoration: none;
  color: var(--text);
  font-size: 0.95rem;
  padding: 0.25rem 0;
  transition: color var(--fade-speed);
}

header nav a:hover {
  color: var(--accent-text);
}
```

---

## ⚙️ 5.3 Header Actions

Used for icons, menus, or sign‑in buttons.

```css
header .actions {
  display: flex;
  align-items: center;
  gap: 1rem;
}

header .actions button {
  padding: 6px 10px;
  border-radius: var(--standard-border-radius);
}
```

---

# 🧩 6. Recommended HTML Structure

```html
<header>
  <div class="logo">bite.css</div>

  <nav class="actions">
    <ul>
      <li><a href="#">Nav Page 1</a></li>
      <li><a href="#">Nav Page 2</a></li>
    </ul>
  </nav>
</header>
```

# Credits

simple.css: Provides half of the header code
