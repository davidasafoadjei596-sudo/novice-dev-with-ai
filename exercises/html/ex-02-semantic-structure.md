# Exercise: Semantic Page Structure

**Module:** 2 | **Type:** Semi-guided | **Time:** 25 minutes

---

## Goal

Build a complete, valid 4-region HTML page using only semantic elements.
Zero `<div>` elements allowed.

---

## What You Will Build

A page for a fictional coffee shop called **"Morning Brew Café"**.

It must include:
- A `<header>` with the café name as `<h1>` and a `<nav>` with 3 links
- A `<main>` containing:
  - A `<section id="about">` with an `<h2>` and two `<p>` elements
  - A `<section id="menu">` with an `<h2>` and an unordered list of 5 menu items
  - An `<article>` with a customer testimonial using `<blockquote>`
- An `<aside>` with opening hours
- A `<footer>` with copyright text and a link to an email address

---

## Hints (read only if stuck after 5 minutes of trying)

<details>
<summary>Hint 1 — Page skeleton</summary>

```html
<body>
  <header>...</header>
  <nav>...</nav>
  <main>
    <section id="about">...</section>
    <section id="menu">...</section>
    <article>...</article>
    <aside>...</aside>
  </main>
  <footer>...</footer>
</body>
```
</details>

<details>
<summary>Hint 2 — Blockquote format</summary>

```html
<blockquote>
  <p>"Best coffee in town, hands down!"</p>
  <cite>— A Happy Customer</cite>
</blockquote>
```
</details>

<details>
<summary>Hint 3 — Email link format</summary>

```html
<a href="mailto:hello@morningbrew.com">Contact us</a>
```
</details>

---

## Success Criteria

- [ ] `<header>`, `<nav>`, `<main>`, `<footer>` all present
- [ ] Zero `<div>` elements in the file
- [ ] One `<h1>` only
- [ ] Headings in order (h1 → h2, no skipping)
- [ ] All images have `alt` text (if you add any)
- [ ] All links have descriptive text (no "click here")
- [ ] HTML validator: zero errors — https://validator.w3.org/

---

## Submitting

Commit and push, then open a PR following `CONTRIBUTING.md`.
Title: `[Your Name] — Module 2 — Semantic Page Structure`
