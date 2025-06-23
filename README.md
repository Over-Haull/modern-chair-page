# Modern Chair Product Page

A visually appealing and interactive product page for a modern chair. This project demonstrates how complex UI interactions, such as changing product colors, images, and background gradients, can be achieved using only HTML and CSS.

### [Live Demo]()
[Design file](README-DESIGN.md)
---

## ✨ Features

* **Interactive Color Swatches:** Users can click on different color options to instantly change the displayed chair.
* **Dynamic UI Updates:** Selecting a color updates not only the chair image but also the page's background gradient and the "Add to Cart" button color to match.
* **CSS-Only Interactivity:** All interactions are handled purely by CSS using the "Radio Button Hack," with no JavaScript required.
* **Smooth Animations:** All visual changes are accompanied by smooth transitions and a subtle "shake" animation on the chair image.
* **Accordion Toggle:** A clean, CSS-powered accordion allows users to switch between the product "Description" and "Details".
* **Responsive Layout:** The layout is structured to be adaptable to different screen sizes.

---

## 🛠️ Technologies Used

* **HTML5:** For the structure and content of the page.
* **CSS3:** For all styling, layout, animations, and interactivity.
* **Google Fonts:** For the "Poppins" typeface.
* **Unicons:** For the shopping cart icon.

---

## 💡 Core Concept: The "Radio Button Hack"

The most important technique used in this project is the **"Radio Button Hack"**. This is a powerful, JavaScript-free method for creating stateful interactions in CSS. Here’s how it works:

1.  **Hidden Radio Buttons:** A set of `<input type="radio">` elements is added to the HTML. These are completely hidden from the user (`visibility: hidden`).
2.  **Clickable Labels:** Each radio button is associated with a `<label>`. These labels are styled to look like UI elements (in this case, the color swatches). When a user clicks a label, the browser checks the corresponding radio button.
3.  **`:checked` Pseudo-Selector:** CSS can target the currently selected radio button using the `:checked` pseudo-class.
4.  **General Sibling Combinator (`~`):** This is the magic key. The `~` combinator allows us to select and style elements that are *siblings* of the `:checked` radio button and appear after it in the HTML document.

**Example:**
When the radio button with the ID `#color-2` is checked, the following CSS rule is activated:
```css
.for-color-2:checked ~ .img-wrap.chair-2 {
  opacity: 1;
}
```
This rule finds the `.img-wrap.chair-2` element (which is a sibling to the radio button) and changes its `opacity` from `0` to `1`, making the second chair image visible. The same principle is used to change the background color, button color, and the description/details tabs.

---

## 📂 Project Structure

```
.
├── assets/Images/       # Folder for all images (chairs, color swatches)
├── index.html           # The main HTML file
├── styles.css           # The CSS file for styling
└── README.md            # This README file
```

---

## 🚀 How to Use

To run this project locally:

1.  Clone the repository:
    ```bash
    git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
    ```
2.  Navigate to the project directory:
    ```bash
    cd your-repo-name
    ```
3.  Open the `index.html` file in your web browser.

No special build steps or dependencies are required.

---

This project was created as a fun exercise to explore the advanced capabilities of modern CSS for creating dynamic and engaging user interfaces without relying on JavaScript.
