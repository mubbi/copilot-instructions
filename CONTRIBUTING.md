
# 🤝 Contributing Guide

Thank you for considering contributing to **copilot-instructions**! We’re building a community-driven source of `.github/copilot-instructions.md` templates for different projects, frameworks, and languages. This guide explains how to contribute effectively and manage version-specific instructions.

---

## 📁 Project Structure

```
/
├── <framework-or-language>/
│   ├── copilot-instructions.md
│   ├── copilot-instructions-vX.md         # optional version-specific
│   └── ...
└── README.md
```

Each top-level folder represents a technology (e.g., `react`, `python`, `nodejs`). Inside each:

- `copilot-instructions.md`: General instructions covering all current versions.
- Optionally, `copilot-instructions-vX.md`: Instructions tailored for major versions (e.g., `-v2`, `-v3`).

---

## 🧩 Adding a New Framework or Language

1. Create a folder named after the technology (lowercase, hyphens allowed).
2. Add a `copilot-instructions.md` file at the root of that folder.
3. Include clear, useful instructions specific to that tech.
4. (Optional) Add versioned files like `copilot-instructions-vX.md` for major version differences.

---

## 🕰 Handling Versions

When a major version introduces significant changes:

- **Update general file**: Reflect best practices across all active versions.
- **Add versioned file**: Name it with a `-vX` suffix (e.g., `copilot-instructions-v16.md` for React v16).
- In the README of that folder, explain how users should pick either the general or versioned files.
- Keep old version files for historical reference and backward compatibility.

---

## 📝 Writing Good Instruction Files

- **Brief & actionable**: Use short, self-contained sentences.
- **Markdown format**: Use headings, bulleted lists, and code blocks as needed.
- Avoid referencing external resources.
- Specify clearly what Copilot should follow, e.g.:
  > Use React Hooks and functional components; avoid class components.
- For version-specific files, note:
  > Applies to React 17+ only.

---

## 🛠 Pull Request Workflow

1. **Fork** the repo and create a feature branch.
2. **Add or update** `copilot-instructions.md` or versioned files.
3. **Validate** markdown layout, spelling, and clarity.
4. **Submit a PR** with:
   - Issue number (if one exists).
   - Explanation of what’s new or changed.
   - Justification: why these instructions are needed.
5. Respond to reviews and iterate.

---

## 📚 Examples

### Example folder `react/`

```
react/
├── copilot-instructions.md              # Covers React best practices generally
├── copilot-instructions-v18.md          # For React 18+ specifics (Concurrent Mode, Strict Effects)
└── README.md                            # Explains available versions and usage
```

Inside versioned `README.md`:

```
# React Instructions

- Use `copilot-instructions.md` if you rely on React 16–17.
- Use `copilot-instructions-v18.md` for React 18+ features (e.g. `useId`, `startTransition`).
```

---

## 🚀 How to Use from Your Project

1. Pick instruction file(s) from this repo:
   - General (`copilot-instructions.md`) or
   - Versioned (`-vX.md`).
2. Copy into your project at `.github/copilot-instructions.md`.
3. Enable it by adding to your VS Code `settings.json`:

```
{
  "github.copilot.chat.codeGeneration.useInstructionFiles": true
}
```

4. Reload VS Code or restart Copilot Chat.

---

## 💬 Support

If you have ideas or improvements:

- Open a **discussion** for brainstorming or high-level proposals.
- Submit a **PR** for ready-to-use instructions or updates.
- For issues, use the issue template and explain what you're trying to achieve.

---

## 🏅 Thank You!

Your efforts will help developers get more precise code suggestions across languages and frameworks. Let’s build this for everyone! 💙
