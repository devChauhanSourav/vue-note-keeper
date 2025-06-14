
# 📝 Vue Note Keeper

A simple and elegant Note Keeper app built with Vue 3 and Tailwind CSS, using **LocalStorage** for data persistence. This beginner-friendly project demonstrates component-based UI structure, reactive data handling, and basic CRUD operations in Vue.

---

## 🚀 Features

- ✅ Create new notes with title and content
- 🗑️ Delete notes with confirmation
- ✏️ Edit/update existing notes
- 💾 Data stored using browser `localStorage`
- 🎨 Responsive modern UI with Tailwind CSS v3

---

## 🧰 Tech Stack

- [Vue 3](https://vuejs.org/)
- [Tailwind CSS v3](https://tailwindcss.com/)
- [Vite](https://vitejs.dev/)

---

## 📦 Project Setup

### 1. Clone this Repository

```bash
git clone https://github.com/devChauhanSourav/vue-note-keeper.git
cd vue-note-keeper
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Start the App

```bash
npm run dev
```

### 4. Build for Production

```bash
npm run build
```

---

## 📁 Project Structure

```
vue-note-keeper/
│
├── public/
│   └── index.html           # Main HTML file
│
├── src/
│   ├── assets/
│   │   └── main.css         # TailwindCSS styles
│   ├── components/
│   │   └── NoteCard.vue     # Reusable component for notes
│   ├── App.vue              # Main app layout and logic
│   └── main.js              # App entry point
│
├── tailwind.config.js       # Tailwind config
├── package.json             # Project metadata & scripts
└── README.md                # Project overview
```

---

## 💡 How It Works

- Notes are stored as objects in a `notes` array inside Vue's reactive state.
- On every change (add/edit/delete), the notes array is saved to localStorage.
- On app load, it reads from localStorage to repopulate the notes.

---

## 📸 Screenshots

*(Add screenshots here if needed)*

---

## ✍️ Author

**Your Name**  
🔗 [GitHub](https://github.com/devChauhanSourav)

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙋‍♀️ Want to Contribute?

Feel free to fork this repo and submit a pull request. Ideas, feedback, and improvements are always welcome!
