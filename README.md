# Shopping List 📋

![Status](https://img.shields.io/badge/status-completed-green?style=for-the-badge)
![JavaScript](https://img.shields.io/badge/HTML5%20%2B%20CSS3%20%2B%20JavaScript-Frontend-yellow?style=for-the-badge)

A shopping list app built with vanilla JavaScript and ES Modules — add, edit, check off, and delete items, with automatic separation between pending and purchased items.

---

## Live Application

[Shopping List Demonstration](https://shopping-list-two-gamma.vercel.app)

---

## Overview

Shopping List is more than a simple task manager. Every list item is built entirely through JavaScript DOM manipulation — no HTML templates. Items have a custom checkbox that moves them between the pending and purchased lists when checked, an edit button that preserves the checked state, a delete button with confirmation, and a timestamp showing the day and time the item was added or last edited. The codebase is split into 7 ES Modules, each with a single responsibility.

---

## Architecture

```
shopping-list/
├── index.html                      # Page structure — two lists: pending and purchased
├── styles.css                      # All styles
├── scripts.js                      # Entry point — imports and wires up event listeners
└── js/
    ├── adicionarItem.js            # Validates input and appends new item to the list
    ├── criarItemDaLista.js         # Builds the full item DOM structure — checkbox, buttons, timestamp
    ├── editarItem.js               # Prompts for new name, updates text, preserves checked state
    ├── excluirItem.js              # Confirms and removes item, updates both list visibility states
    ├── gerarDiaDaSemana.js         # Returns formatted date/time string using toLocaleDateString
    ├── verificarListaComprados.js  # Shows/hides the purchased section based on item count
    └── verificarListaVazia.js      # Shows/hides the empty state message
```

### Key Concepts Applied

| Concept | How it shows up |
|---|---|
| **ES Modules** | All 7 files use `import`/`export` — `scripts.js` is the entry point |
| **DOM manipulation** | `criarItemDaLista()` builds the entire item element with `createElement`, `classList`, `appendChild` |
| **Custom checkbox** | CSS-styled div toggled by a real hidden checkbox — preserves accessibility with `label[for]` |
| **Two-list system** | Checking an item moves it to the purchased list; unchecking moves it back |
| **Date/time** | `gerarDiaDaSemana()` uses `toLocaleDateString("pt-BR")` and `toLocaleTimeString` for formatted output |
| **Edit with state** | `editarItem()` preserves the checked/unchecked visual state after renaming |
| **Input validation** | `adicionarItem()` blocks empty submissions with an alert |
| **Confirmation dialog** | `excluirItem()` uses `confirm()` before removing an item |
| **Unique IDs** | Checkboxes get unique IDs via a `contador` variable — enables correct `label[for]` association |

---

## Features

- **Add items** — type and click to add; empty input is blocked
- **Check off** — custom checkbox moves item to the purchased section with strikethrough text
- **Edit** — rename any item via prompt; preserves its checked state and updates the timestamp
- **Delete** — remove with a confirmation dialog
- **Empty state** — message shown when the pending list is empty
- **Purchased section** — hidden when empty, shown automatically when items are checked off

---

## How to Run

```bash
git clone https://github.com/victorhubarb/shopping-list.git
cd shopping-list
```

Open `index.html` in your browser using Live Server or any local server (ES Modules require a server context).

---

## Technologies

- **HTML5 / CSS3 / JavaScript**
- **ES Modules** — native JavaScript module system

---

## Author

**Victor Hugo Barbosa**
[GitHub](https://github.com/victorhubarb) · [LinkedIn](https://www.linkedin.com/in/victorhbarbosa/)
