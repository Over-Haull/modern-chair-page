Understood! Here's the design specification for your "Modern Chair Page" project, based on the HTML and CSS you provided.

You can copy this entire section and save it as a `project-specs.md` file on your computer for easy reference.

https://codehelp-modern-chair-page.netlify.app/

---

# Design Specs: Modern Chair Page

## 🎨 Color Palette

| Usage | Color | HEX/CSS Value |
| :------------------------------- | :----------------------------- | :-------------------------- |
| **Global Text** | White | `#fff` |
| **Body Background (Default)** | Red Gradient | `linear-gradient(196deg, #f1a9a9, #e66767)` |
| **Accent Text (Description Label)**| Yellow | `#ffeba7` |
| **Price Strikethrough Opacity** | Semi-transparent White | `opacity: 0.6` (`#fff` base) |
| **Color Picker Border (Active)** | Dark Grey | `#434343` |
| **Button Background (Default)** | Dark Red | `#944852` |
| **Button Background (Hover)** | Dark Grey | `#333` |
| **Button Shadow (Default)** | Dark Blue (15% Opacity) | `rgba(16, 39, 112, 0.15)` |
| **Button Shadow (Hover)** | Dark Blue (25% Opacity) | `rgba(16, 39, 112, 0.25)` |
| **Color Picker Shadow** | Dark Blue (25% Opacity) | `rgba(16, 39, 112, 0.25)` |

### Dynamic Colors (based on chair selection)

| Chair Color | Background Color | Button Background Color |
| :----------------- | :----------------------- | :---------------------- |
| **Chair 1 (Default)** | `#f1a9a9` to `#e66767` gradient | `#944852` |
| **Chair 2** | `#dadada` to `#b0b0b0` gradient (implicit from image) | `#1a1a1a` |
| **Chair 3** | `#c7e0f3` to `#8ec6ec` gradient (implicit from image) | `#40566e` |
| **Chair 4** | `#a1b1d3` to `#627fa2` gradient (implicit from image) | `#5e89b2` |
| **Chair 5** | `#e1d1c8` to `#b2a297` gradient (implicit from image) | `#8c7f76` |
| **Chair 6** | `#c2d0d0` to `#87a2a2` gradient (implicit from image) | `#5d6160` |

---

## ✒️ Typography

* **Global Font Family:** `'Poppins', sans-serif`

| Element | Font Weight | Font Size | Line Height | Other Styles |
| :------------------------------ | :---------- | :-------- | :---------- | :----------- |
| **Paragraph Text (`p`)** | `400` | `16px` | `1.7` | |
| **Title Up (`.titleUp`)** | `700` | `13px` | `1.2` | Uppercase, `1px` letter-spacing |
| **Main Heading (`h2`)** | `800` | `34px` | `1.2` | |
| **Price (`h4`)** | `500` | `26px` | `1.2` | |
| **Old Price (`h4 span`)** | `(inherit)` | `20px` | `(inherit)` | Line-through, `0.6` opacity, `15px` left padding |
| **Color Choice Heading (`h5`)** | `600` | `18px` | `1.2` | |
| **Description/Details Labels** | `600` | `18px` | `1.2` | `25px` right margin, `0.5` opacity (default) |
| **Detail Values (`span` in `.sectionInline p`)** | `(inherit)` | `30px` | `1.1` | |
| **Button Text (`.btn`)** | `500` | `14px` | `2` | `1px` letter-spacing |
| **Button Icon (`.icon`)** | `(inherit)` | `20px` | `(inherit)` | `7px` right padding |

---

## 📏 Layout & Spacing

| Element | Property | Value |
| :----------------------------- | :-------------------------- | :---------------------------------- |
| **Wrapper (`#wrapper`)** | `width` / `height` / `overflow` | `100%` / `100vh` / `auto` (y), `hidden` (x) |
| **Container (`.container`)** | `position` / `max-width` / `width` / `margin` / `padding` | `relative` / `calc(100% - 40px)` / `860px` / `0 auto` / `100px 0` |
| **Info Wrapper (`.infoWrap`)** | `margin-left` / `text-align` | `500px` / `left` |
| **Main Heading (`h2`)** | `margin-bottom` | `10px` |
| **Price (`h4`)** | `margin-bottom` | `30px` |
| **Color Choice Heading (`h5`)**| `margin-bottom` | `20px` |
| **Description/Details Labels** | `margin-right` | `25px` |
| **Description Sections** | `padding-top` / `padding-bottom` | `20px` / `30px` |
| **Inline Detail Sections** | `margin-right` | `20px` |
| **Color Labels** | `height` / `width` / `margin-right` | `40px` / `40px` / `10px` |
| **First Color Label** | `margin-left` | `500px` |
| **Image Wrapper (`.imgWrap`)**| `height` / `width` / `top` / `left` | `410px` / `500px` / `100px` / `0` |
| **Button (`.btn`)** | `height` / `width` / `margin-top` | `48px` / `210px` / `50px` |

---

## ✨ Effects & Components

### Global

* **Box Sizing:** `border-box` applied globally.
* **Radio Buttons:** Hidden by default.

### Color Selection

* **Color Labels:**
    * `cursor: pointer;`
    * `box-shadow: 0 12px 35px 2px rgba(16, 39, 112, 0.25);`
    * **Checked State:** `border-color: #434343; transform: scale(1.1);`
    * **Transition:** `all 200ms linear`

### Image Display (`.imgWrap`)

* **Default State:** `opacity: 0;`
* **Checked State (via radio button):** `opacity: 1;` and triggers a `shake` animation.
* **Background Size:** `100%` (for chair images).
* **Transitions:** `all 550ms linear` with `100ms` delay.
* **Shake Animation (`@keyframes shake`):** A subtle shaking effect for 0.7s, using `cubic-bezier(0.36, 0.07, 0.19, 0.97)`.

### Background Color (`.backColor`)

* **Positioning:** Fixed to cover the entire viewport.
* **Default Background:** `linear-gradient(196deg, #f1a9a9, #e66767)`
* **Dynamic Background:** Changes based on the selected chair, implicitly through the `backColor` classes (e.g., `.backColor.chair2`).
* **Transitions:** `all 250ms linear` with `300ms` delay.

### Description/Details Tabs

* **Labels:**
    * `cursor: pointer;`
    * **Default Opacity:** `0.5`.
    * **Checked State:** `opacity: 1;`
    * **Hover State (unchecked):** `opacity: 0.8;`
    * **Transition:** `all 200ms linear`.
* **Sections (`.descSec`):**
    * **Default State:** `opacity: 0; overflow: hidden; pointer-events: none; transform: translateY(20px);`
    * **Checked State (via radio button):** `opacity: 1; pointer-events: auto; transform: translateY(0);`
    * **Transition:** `all 250ms linear`.

### Button (`.btn`)

* **Base Styles:** `border-radius: 4px;`
* **`::before` Pseudo-element:**
    * Acts as the background, covering the full button size.
    * **Default Background:** `#944852`
    * **Dynamic Background:** Changes based on the selected chair (e.g., `.forColor2:checked ~ .infoWrap .btn:before` sets `background-color: #1a1a1a;`).
    * **Transition:** `background-color 250ms 300ms ease`.
* **Hover State:**
    * `box-shadow: 0 12px 35px 0 rgba(16, 39, 112, 0.25);`
    * `background-color: #333;` (This will be the background for the button itself, *not* the `::before` pseudo-element, creating an interesting layered effect).
* **Transitions:** `all 250ms linear` on the button itself.

---

## 🖼️ Asset List

* `favicon.ico` (located in `./images/`)
* **Color Thumbnails** (located in `./Images/`):
    * `color1.jpg`
    * `color2.jpg`
    * `color3.jpg`
    * `color4.jpg`
    * `color5.jpg`
    * `color6.jpg`
* **Chair Images** (located in `./Images/`):
    * `chair1.png`
    * `chair2.png`
    * `chair3.png`
    * `chair4.png`
    * `chair5.png`
    * `chair6.png`

---

This detailed specification should give you a complete understanding of the design for your "Modern Chair Page."

Would you like to continue with another project, or perhaps explore specific aspects of this one in more detail?