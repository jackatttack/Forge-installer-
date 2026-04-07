Got it. Let me write it directly — no bundle needed for this one, it’s a GitHub file not in your Pythonista project.

# Forge2

A clipboard-driven AST patcher for Python, built to run entirely on iPhone in Pythonista.

Write patch bundles in plain text, copy to clipboard, fire a Shortcut — Forge rewrites your code on disk and returns a run packet telling you exactly what happened.

---

## What it does

- Patch Python files surgically — replace functions, inject lines, swap expressions — using structured plain-text bundles
- Create, copy, move, and delete files without touching an editor
- Run scripts and capture output
- Search your project with GREP
- Every op is documented — run `HELP <OP>` from inside a session and Forge tells you exactly how to use it

It's designed to be driven by an LLM. You describe what you want, the LLM writes the bundle, you run it, paste the result back. The run packet is ground truth.

---

## Requirements

- iPhone with [Pythonista 3](https://omz-software.com/pythonista/)
- iOS Shortcuts app
- An LLM you can paste into (Claude, ChatGPT, etc.)

---

## Installation

1. Download `forge_install.py` and copy it to your Pythonista Documents folder
2. Run it once in Pythonista
3. Delete `forge_install.py` when done
4. Set up your Shortcut:
   - Open the Shortcuts app
   - New Shortcut → Add Action → Pythonista → Run Script
   - Set script to `forge2_shortcut.py`
   - Save it as **Forge**
   - Assign to Action Button, Home Screen, or Lock Screen

---

## First session

1. Open `forge2/onboarding.md` in Pythonista
2. Copy the entire contents
3. Paste into your LLM of choice
4. The LLM will orient itself, walk you through the basics, and help you build something

If you already know what you're doing, open `forge2/bootstrap.md` instead — that's the lean reference doc for experienced sessions.

---

## How it works

Forge reads plain-text bundles from the clipboard. Each bundle contains one or more ops:



LIST_FILES .
CREATE_FILE hello.py
print(“hello world”)
RUN_FILE hello.py


Run the Shortcut, Forge executes the ops in order and writes a run packet back to the clipboard. Paste it back to your LLM and continue.

---

## Licence

MIT

