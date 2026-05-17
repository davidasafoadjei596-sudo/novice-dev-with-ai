# Exercise: HTML Boilerplate

**Module:** 1 | **Type:** Guided | **Time:** 20 minutes

---

## Goal

Type the HTML5 boilerplate from scratch without copying and pasting.
Every line typed by hand. By the end you should be able to do this from memory.

---

## Instructions

### Step 1 — Create your file
In VS Code, inside `student-projects/your-name/`, create a file called `index.html`.

### Step 2 — Type this boilerplate (do NOT copy-paste)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Name — My First Page</title>
    <link rel="stylesheet" href="style.css">
  </head>
  <body>

    <h1>Hello, I'm [Your Name]</h1>
    <p>I am learning web development in this course.</p>
    <p>I am from [your city].</p>

  </body>
</html>
```

Replace `[Your Name]` and `[your city]` with real values.

### Step 3 — Save and preview
Press `Ctrl+S`. Right-click `index.html` → **Open with Live Server**.

Chrome should open and show your heading and two paragraphs.

### Step 4 — Validate
Go to https://validator.w3.org/ → Direct Input → paste your HTML → Validate.

**Required:** Zero errors before submitting.

---

## Checking Your Work

Answer these without looking at the code:

1. What does `<!DOCTYPE html>` tell the browser?
2. Why does `<html>` have `lang="en"`?
3. What happens if you remove `<meta charset="UTF-8">`?
4. What does the `viewport` meta tag do on a phone?
5. What is the difference between `<head>` and `<body>`?

If you can answer all 5, you understand the boilerplate. If not, read `lesson-notes.md` again.

---

## Extension Challenge (If You Finish Early)

Without looking at the lesson notes, add:
- A `<meta name="description">` tag in the `<head>`
- A second heading (`<h2>`) with the text "Why I Want to Learn Web Development"
- A paragraph under it with your reason
- Validate again — still zero errors

---

## Milestone Connection

This exercise directly prepares you for the **Module 1 Milestone**:
typing the boilerplate from memory and explaining each line out loud.
