# Bug Report & Fixes — Landing Page

## 2. Text Not Aligning Below the Box

**File:** `index.html` + `style.css`

**Error:** The `<p>` tag inside `.img1` had an inline style `float: inline-start` applied. This pulled the text sideways instead of placing it below the image box, breaking the card layout entirely.

**Fix:** Removed the inline style completely. Added a proper `.info-img-text` CSS class with `margin-top: 12px`, `text-align: center`, and `line-height: 1.5` to place and style the text correctly under each box.

---

## 3. `.img1` Had No Flex Direction Set

**File:** `style.css`

**Error:** `.img1` had no CSS rules at all. Without `flex-direction: column` and `align-items: center`, the image box and text sat side by side horizontally instead of stacking vertically.

**Fix:** Added `.img1` to the CSS with:
```css
.img1 {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 180px;
}
```

---

## 4. `.image-info` Missing `align-items: flex-start`

**File:** `style.css`

**Error:** `.image-info` had `align-items: center`, which vertically centered each card relative to the tallest card. Cards with more text appeared misaligned compared to cards with less text.

**Fix:** Changed to `align-items: flex-start` so all cards align from the top, keeping the image boxes at the same level regardless of text length below them. Also added `gap: 24px` to replace any manual margin spacing.

---

## 5. `.imgs` Width Was Set to 20% of the Viewport

**File:** `style.css`

**Error:** `.imgs` had `width: 20%`, which referred to 20% of the parent container (`.image-info`), not the card itself. This caused inconsistent sizing depending on screen width.

**Fix:** Changed to `width: 100%` so the image box fills its parent `.img1` card, which has a fixed `width: 180px`. This makes sizing predictable and consistent across all cards.

---

## 6. `.info` Section Had a Fixed Height That Clipped Content

**File:** `style.css`

**Error:** `.info` had `height: 400px` hardcoded. With 4 cards plus the section heading, content overflowed or got clipped on smaller screens.

**Fix:** Removed the fixed height and replaced it with `padding-bottom: 40px` so the section expands naturally to fit all content.

---