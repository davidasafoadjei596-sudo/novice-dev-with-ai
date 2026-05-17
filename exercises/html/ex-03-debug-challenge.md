# Exercise: Debug This HTML

**Module:** 2 | **Type:** Debug Challenge | **Time:** 20 minutes

---

## Goal

Find and fix all the HTML errors in the broken code below.
Do NOT look at the answers — find each one yourself.

---

## Broken Code

Copy this into a new file. Find what's wrong.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>My Blog</title>
  </head>
  <body>

    <div class="header">
      <h1>My Web Development Blog</h1>
      <h1>Learning Every Day</h1>
      <div class="nav">
        <a href="#">Click here</a>
        <a href="#">Read more</a>
        <a href="#">Click here</a>
      </div>
    </div>

    <div class="main">
      <h3>My First Post</h3>
      <p>Today I learned about HTML. It was great.</p>
      <img src="images/code.jpg">
    </div>

    <div class="form-area">
      <input type="text" placeholder="Enter your name">
      <input type="email" placeholder="Enter your email">
      <input type="submit" value="Subscribe">
    </div>

    <div class="footer">
      <p>Copyright 2026</p>
    </div>

  </body>
</html>
```

---

## Your Task

Find at least **8 errors**. Write each one as:

```
Error: [describe what's wrong]
Fix: [describe what it should be]
```

Then fix them all in your file and validate: https://validator.w3.org/

---

## Answer Key (Instructor Only)

Stored in `.claude/contexts/teacher.md` — do not share until after students submit.

```
1. Missing lang="en" on <html>
2. Missing <meta name="viewport">
3. <div class="header"> should be <header>
4. Two <h1> elements — only one allowed
5. <div class="nav"> should be <nav>
6. All three link texts are "Click here" or "Read more" — not descriptive
7. <h3> comes directly after <h1> — skipped <h2> (heading level skip)
8. <img> missing alt attribute
9. Missing <link rel="stylesheet"> (no CSS linked)
10. <div class="main"> should be <main>
11. <div class="form-area"> should be <form>
12. Inputs have no <label> elements
13. <div class="footer"> should be <footer>
```
