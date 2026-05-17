# Exercise: Flexbox Navigation and Cards

**Module:** 4 | **Type:** Semi-guided | **Time:** 30 minutes

---

## Goal

Build a responsive navigation bar and a 3-card row using Flexbox only.
No CSS Grid, no `float`, no `position: absolute` for layout.

---

## Part A — Navigation Bar (15 min)

### Requirements
- Brand name on the LEFT
- 3 navigation links on the RIGHT
- All items vertically CENTERED
- Dark background (`#1e293b`)
- Links turn white on hover
- Works on all screen sizes (links wrap if needed)

### HTML to use

```html
<nav class="site-nav">
  <a href="#" class="nav-brand">Morning Brew</a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#menu">Menu</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>
```

### Hints (use only if stuck after 5 minutes)

<details>
<summary>Hint A1 — Which element gets display: flex?</summary>
The `.site-nav` — it is the container (parent). The children are the brand and the ul.
</details>

<details>
<summary>Hint A2 — How do I push the links to the right?</summary>
`justify-content: space-between` on `.site-nav` pushes the first and last children apart.
</details>

<details>
<summary>Hint A3 — How do I put the links in a row?</summary>
The `<ul>` is also a flex container: `display: flex` on `.nav-links`.
</details>

---

## Part B — Card Row (15 min)

### Requirements
- 3 equal-width cards side by side
- Gap between cards
- Cards wrap to a new row when the screen is narrow
- Each card has a title, short description, and a link

### HTML to use

```html
<section class="card-section">
  <h2>Our Drinks</h2>
  <div class="card-row">
    <article class="card">
      <h3>Espresso</h3>
      <p>Rich, concentrated coffee with a smooth finish.</p>
      <a href="#">Order now</a>
    </article>
    <article class="card">
      <h3>Latte</h3>
      <p>Espresso with steamed milk and a touch of foam.</p>
      <a href="#">Order now</a>
    </article>
    <article class="card">
      <h3>Cold Brew</h3>
      <p>Slow-steeped for 12 hours. Smooth and refreshing.</p>
      <a href="#">Order now</a>
    </article>
  </div>
</section>
```

### Hints

<details>
<summary>Hint B1 — Making all cards equal width</summary>
`flex: 1` on `.card` makes each card grow equally.
</details>

<details>
<summary>Hint B2 — Preventing cards from getting too narrow</summary>
`min-width: 220px` on `.card` sets the minimum before wrapping.
</details>

---

## Success Criteria

**Navigation:**
- [ ] Brand on left, links on right (space-between)
- [ ] All items vertically centered (align-items: center)
- [ ] Hover state changes link color

**Cards:**
- [ ] 3 cards side by side with gap
- [ ] Cards wrap to 1 column on narrow window (test by resizing)
- [ ] All cards same height (try `align-items: stretch` on container)

**Code:**
- [ ] No `float`, `position: absolute`, or CSS Grid used
- [ ] CSS validator: zero errors
