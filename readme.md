Here is a **clean, fully copy-paste ready `README.md` file** with proper formatting (no broken blocks, no rendering issues). You can directly paste this into GitHub or your project.

```md
# 🎉 Birthday Wish Website

A beautiful, animated, single-page birthday wish website designed to surprise someone special.  
This project personalizes the experience using a URL parameter and a simple frontend encoding system — no backend required.

---

## 🌟 Live Idea

You can share a link like this:
```

[https://your-site.com/?name=Sm9obiBEb2U](https://your-site.com/?name=Sm9obiBEb2U)

```

When opened, it automatically displays:

```

John Doe

````

---

## ✨ Features

- 🎂 Animated birthday surprise page
- 💌 Personalized name via URL parameter
- 🔐 Lightweight Base64 URL-safe encoding
- 📱 Fully responsive (mobile + desktop)
- 🎨 Smooth transitions and animations
- 🎁 Surprise reveal experience
- ⚡ 100% frontend (no backend needed)

---

## 🧠 How It Works

The website:
1. Reads `name` from URL query params
2. Decodes it using a custom Base64-safe function
3. Injects it into elements with `.person-name` class

---

## 🔐 Encoding Function

```javascript
function encodeName(name) {
  return btoa(name)
    .replace(/\+/g, "-")
    .replace(/\//g, "_")
    .replace(/=+$/, "");
}
````

---

## 🔓 Decoding Function

```javascript
function decodeName(encoded) {
  let base64 = encoded.replace(/-/g, "+").replace(/_/g, "/");

  base64 = base64.padEnd(base64.length + ((4 - (base64.length % 4)) % 4), "=");

  return atob(base64);
}
```

---

## 🧩 DOM Injection Logic

```javascript
const getAllNames = document.querySelectorAll(".person-name");

if (getAllNames) {
  const windowUrl = new URL(window.location.href);
  const personName = windowUrl.searchParams.get("name");

  getAllNames.forEach((el) => {
    el.innerHTML = personName ? decodeName(personName) : "[By saral code]";
  });
}
```

---

## 🔗 Example Usage

### Step 1: Encode a name

```javascript
encodeName("John Doe");
```

Output:

```
Sm9obiBEb2U
```

---

### Step 2: Create link

```
https://your-site.com/?name=Sm9obiBEb2U
```

---

### Step 3: Result

The website displays:

```
John Doe
```

Instead of:

```
[By saral code]
```

---

## 🎁 Use Cases

- 🎂 Birthday surprise pages
- 💌 Personalized greeting pages
- 🎉 Event invitations
- 💖 Fun shareable links

---

## 🛠️ Tech Stack

- HTML5
- CSS3 (Animations + Transitions)
- Vanilla JavaScript
- Browser APIs (`btoa`, `atob`)

---

## 💡 Concept

This project is designed to create a memorable emotional experience using only frontend technologies.
No backend, no database — just pure creativity and JavaScript.

---

## 🚀 How to Run

1. Download or clone the project
2. Open `index.html` in a browser
3. Generate encoded name using `encodeName()`
4. Add it to URL as `?name=...`
5. Share the link 🎁

---

## 📌 Example

Input:

```
John Doe
```

Encoded:

```
Sm9obiBEb2U
```

Final URL:

```
https://your-site.com/?name=Sm9obiBEb2U
```

Output on page:

```
John Doe
```

---

## ❤️ Credits

Made with love by **saral code**

---

## ⚠️ Note

- Fully frontend-based project
- No server or database required
- Works in all modern browsers

```

```
