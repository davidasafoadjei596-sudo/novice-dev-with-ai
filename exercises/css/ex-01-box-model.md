# Exercise: CSS Box Model Inspector

**Module:** 3 | **Type:** Guided | **Time:** 20 minutes

---

## Goal

Apply the CSS box model to a card and inspect it in Chrome DevTools.
Understand visually what content, padding, border, and margin each do.

---

## What You Will Build

A styled profile card with visible padding, border, and margin.

---

## Instructions

### Step 1 — HTML

Add this to your `index.html` inside `<main>`:

```html
<article class="profile-card">
  <img src="https://picsum.photos/80/80" alt="Profile placeholder" class="profile-card__avatar">
  <h2 class="profile-card__name">Your Name</h2>
  <p class="profile-card__role">Web Development Student</p>
  <p class="profile-card__bio">
    I am learning HTML, CSS, and JavaScript through the novice-dev-with-ai course.
  </p>
  <a href="#" class="profile-card__link">View my GitHub</a>
</article>
```

### Step 2 — CSS (type each property and observe the change)

Add to `style.css`:

```css
/* Start with the reset */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: system-ui, sans-serif;
  background: #f8fafc;
  padding: 2rem;
}

/* --- Add these ONE AT A TIME and observe in Live Server --- */

.profile-card {
  width: 300px;
}
/* After typing this: how wide is the card? */

.profile-card {
  width: 300px;
  padding: 1.5rem;    /* Add this next */
}
/* Padding pushed content inward — total width is still 300px (box-sizing: border-box) */

.profile-card {
  width: 300px;
  padding: 1.5rem;
  border: 2px solid #e2e8f0;  /* Add this */
}
/* Border is now visible — still 300px total */

.profile-card {
  width: 300px;
  padding: 1.5rem;
  border: 2px solid #e2e8f0;
  border-radius: 12px;        /* Rounded corners */
  background: white;
  margin: 2rem auto;          /* Center the card + space around it */
}
```

### Step 3 — Inspect in DevTools

1. Press `F12`
2. Click the Inspector/Elements tab
3. Click on your `.profile-card` in the HTML tree
4. Look at the bottom right — find the **Box Model diagram**
5. Hover over each section (margin, border, padding, content) — it highlights in the browser
6. Screenshot it

### Step 4 — Style the rest of the card

```css
.profile-card__avatar {
  width: 80px;
  height: 80px;
  border-radius: 50%;          /* perfect circle */
  display: block;
  margin-bottom: 1rem;
}

.profile-card__name {
  font-size: 1.25rem;
  margin-bottom: 0.25rem;
}

.profile-card__role {
  color: #64748b;
  font-size: 0.875rem;
  margin-bottom: 1rem;
}

.profile-card__bio {
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.profile-card__link {
  display: inline-block;
  color: #2563eb;
  font-weight: 600;
  text-decoration: none;
}

.profile-card__link:hover {
  text-decoration: underline;
}
```

---

## Questions (Answer in a CSS comment)

Add this comment block at the top of your CSS file and fill it in:

```css
/*
  BOX MODEL REFLECTION
  =====================
  1. What is the TOTAL rendered width of my .profile-card?
  2. What happens if I remove box-sizing: border-box and add 100px of padding?
  3. What is the difference between margin and padding?
  4. How did I center the card horizontally?
*/
```

---

## Success Criteria

- [ ] Card renders correctly in Chrome
- [ ] DevTools Box Model screenshot taken
- [ ] All 4 reflection questions answered in a CSS comment
- [ ] CSS validator: zero errors
