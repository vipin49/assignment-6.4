

## 1. Aim

To create a webpage demonstrating CSS positioning properties: `static`, `relative`, `absolute`, `fixed`, and `sticky`. The webpage will contain multiple sections, a sticky navigation bar, a floating help button, and a positioned badge inside a card. The `z-index` property will control overlapping elements.

## 2. Project Structure

Create a folder named `Assignment-6.4` with the following files:

```text
Assignment-6.4/
├── index.html
└── style.css
```

## 3. HTML Code — `index.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Assignment 6.4 - Positioning Practice</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Page Header -->
    <header class="hero" id="home">
        <h1>CSS Positioning Practice</h1>
        <p>
            Learn how sticky, fixed, absolute, and relative positioning
            work in a real webpage.
        </p>
        <a href="#about" class="hero-button">Explore More</a>
    </header>

    <!-- Sticky Navigation Bar -->
    <nav class="navbar">
        <a href="#home" class="logo">WebLearn</a>

        <div class="nav-links">
            <a href="#home">Home</a>
            <a href="#about">About</a>
            <a href="#courses">Courses</a>
            <a href="#contact">Contact</a>
        </div>
    </nav>

    <main class="container">

        <!-- About Section -->
        <section class="content-section" id="about">
            <h2>About CSS Positioning</h2>
            <p>
                CSS positioning controls where elements appear on a webpage.
                It helps developers create navigation bars, floating buttons,
                badges, overlays, and many other interface components.
            </p>
            <p>
                Scroll down the page to observe the sticky navigation bar
                and the floating Help button. The navigation remains near
                the top while scrolling, and the Help button stays in a
                fixed position relative to the viewport.
            </p>
        </section>

        <!-- Card with Absolute Badge -->
        <section class="content-section" id="courses">
            <h2>Featured Course</h2>
            <p>
                This card demonstrates how relative and absolute positioning
                work together.
            </p>

            <article class="course-card">
                <span class="badge">NEW</span>

                <div class="course-icon">💻</div>
                <h3>Web Development</h3>
                <p>
                    Learn HTML, CSS, and JavaScript to build responsive
                    and interactive websites.
                </p>
                <a href="#contact" class="card-button">Learn More</a>
            </article>

            <p class="note">
                The card uses position: relative, allowing the NEW badge
                to be positioned at the top-right corner using
                position: absolute.
            </p>
        </section>

        <!-- Positioning Examples -->
        <section class="content-section">
            <h2>Positioning Examples</h2>

            <div class="example-grid">
                <article class="example-card">
                    <h3>Relative</h3>
                    <p>
                        Relative positioning moves an element from its
                        normal position while preserving its original space.
                    </p>
                    <div class="relative-demo">
                        <div class="relative-box">Moved Element</div>
                    </div>
                </article>

                <article class="example-card">
                    <h3>Absolute</h3>
                    <p>
                        Absolute positioning places an element relative
                        to its nearest positioned ancestor.
                    </p>
                    <div class="absolute-demo">
                        <span class="absolute-label">Absolute Element</span>
                    </div>
                </article>

                <article class="example-card">
                    <h3>Static</h3>
                    <p>
                        Static is the default position value. The element
                        follows the normal document flow.
                    </p>
                    <div class="static-demo">Static Element</div>
                </article>
            </div>
        </section>

        <!-- Scroll Section -->
        <section class="content-section" id="practice">
            <h2>Why Positioning Matters</h2>
            <p>
                Positioning is useful for building modern web interfaces.
                A sticky navbar helps users navigate long pages without
                scrolling back to the top.
            </p>
            <p>
                Fixed elements are useful for persistent actions such as
                help, contact, or back-to-top buttons. Absolute positioning
                is useful for labels and badges that belong to a card.
            </p>
            <p>
                The z-index property controls the stacking order of
                positioned elements when they overlap. A higher z-index
                generally places an element above another element within
                the same stacking context.
            </p>
        </section>

        <!-- Contact Section -->
        <section class="content-section contact-section" id="contact">
            <h2>Contact Us</h2>
            <p>
                Have a question about web development? Use the floating
                Help button in the bottom-right corner of this page.
            </p>
            <p>
                This is a demonstration webpage created for Assignment 6.4.
            </p>
            <a href="#home" class="hero-button">Back to Top</a>
        </section>

    </main>

    <!-- Fixed Floating Help Button -->
    <a href="#contact" class="floating-help" aria-label="Go to contact section">
        <span class="help-icon">?</span>
        <span>Help</span>
    </a>

    <!-- Footer -->
    <footer class="footer">
        <p>Assignment 6.4 | Web Development Practice</p>
    </footer>

</body>
</html>
```

## 4. CSS Code — `style.css`

```css
/* Reset and General Styles */
* {
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
    scroll-padding-top: 90px;
}

body {
    margin: 0;
    font-family: Arial, sans-serif;
    line-height: 1.7;
    color: #1e293b;
    background-color: #f1f5f9;
}

/* Hero Header */
.hero {
    min-height: 300px;
    padding: 55px 20px;
    text-align: center;
    color: white;
    background: linear-gradient(135deg, #1e3a8a, #2563eb);
}

.hero h1 {
    margin: 0 0 12px;
    font-size: 38px;
}

.hero p {
    max-width: 650px;
    margin: 0 auto 25px;
}

.hero-button {
    display: inline-block;
    padding: 10px 20px;
    color: white;
    text-decoration: none;
    background-color: #0f766e;
    border-radius: 8px;
    font-weight: bold;
}

.hero-button:hover {
    background-color: #115e59;
}

/* Sticky Navigation Bar */
.navbar {
    position: sticky;
    top: 0;
    z-index: 1000;

    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;

    padding: 15px 6%;
    background-color: #0f172a;
    color: white;
    box-shadow: 0 3px 10px rgba(0, 0, 0, 0.15);
}

.logo {
    color: white;
    font-size: 22px;
    font-weight: bold;
    text-decoration: none;
}

.nav-links {
    display: flex;
    flex-wrap: wrap;
    gap: 22px;
}

.nav-links a {
    color: white;
    text-decoration: none;
    font-weight: bold;
}

.nav-links a:hover {
    color: #93c5fd;
}

/* Main Content */
.container {
    width: 92%;
    max-width: 1100px;
    margin: 30px auto;
}

.content-section {
    margin-bottom: 30px;
    padding: 30px;
    background-color: white;
    border: 1px solid #e2e8f0;
    border-radius: 12px;
    box-shadow: 0 4px 12px rgba(15, 23, 42, 0.05);
    scroll-margin-top: 90px;
}

.content-section h2 {
    margin-top: 0;
    color: #1d4ed8;
}

/* Course Card: Relative Parent */
.course-card {
    position: relative;
    z-index: 1;

    width: 100%;
    max-width: 380px;
    margin: 30px auto 20px;
    padding: 30px 25px;

    text-align: center;
    background-color: #eff6ff;
    border: 2px solid #93c5fd;
    border-radius: 14px;
    box-shadow: 0 6px 16px rgba(37, 99, 235, 0.1);
}

.course-icon {
    font-size: 48px;
}

.course-card h3 {
    margin-bottom: 8px;
    color: #1e40af;
}

/* Absolute Badge inside the Relative Card */
.badge {
    position: absolute;
    top: 12px;
    right: 12px;
    z-index: 2;

    padding: 5px 12px;
    color: white;
    background-color: #dc2626;
    border-radius: 20px;
    font-size: 12px;
    font-weight: bold;
}

.card-button {
    display: inline-block;
    padding: 9px 16px;
    color: white;
    background-color: #2563eb;
    text-decoration: none;
    border-radius: 7px;
}

.card-button:hover {
    background-color: #1d4ed8;
}

.note {
    padding: 12px;
    background-color: #fef3c7;
    border-left: 4px solid #d97706;
    border-radius: 5px;
}

/* Positioning Examples Layout */
.example-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 20px;
}

.example-card {
    padding: 20px;
    background-color: #f8fafc;
    border: 1px solid #cbd5e1;
    border-radius: 10px;
}

.example-card h3 {
    margin-top: 0;
    color: #0f766e;
}

/* Relative Positioning Demonstration */
.relative-demo {
    min-height: 110px;
    padding: 10px;
    background-color: #dbeafe;
    border: 1px dashed #2563eb;
}

.relative-box {
    position: relative;
    top: 10px;
    left: 10px;

    width: 150px;
    max-width: 100%;
    padding: 10px;
    background-color: #2563eb;
    color: white;
    border-radius: 5px;
}

/* Absolute Positioning Demonstration */
.absolute-demo {
    position: relative;
    min-height: 110px;
    padding: 10px;
    background-color: #dcfce7;
    border: 1px dashed #16a34a;
}

.absolute-label {
    position: absolute;
    top: 10px;
    right: 10px;
    padding: 8px;
    color: white;
    background-color: #15803d;
    border-radius: 5px;
    font-size: 12px;
}

/* Static Positioning Demonstration */
.static-demo {
    position: static;
    padding: 12px;
    background-color: #f3e8ff;
    border: 2px solid #9333ea;
    border-radius: 5px;
}

/* Contact Section */
.contact-section {
    min-height: 250px;
    background-color: #f8fafc;
}

/* Fixed Floating Help Button */
.floating-help {
    position: fixed;
    right: 24px;
    bottom: 24px;
    z-index: 2000;

    display: flex;
    align-items: center;
    gap: 8px;

    padding: 13px 18px;
    color: white;
    background-color: #ea580c;
    text-decoration: none;
    font-weight: bold;
    border-radius: 50px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.25);
}

.floating-help:hover {
    background-color: #c2410c;
}

.help-icon {
    display: inline-flex;
    align-items: center;
    justify-content: center;

    width: 24px;
    height: 24px;
    color: #ea580c;
    background-color: white;
    border-radius: 50%;
}

/* Footer */
.footer {
    padding: 20px;
    color: white;
    background-color: #0f172a;
    text-align: center;
}

.footer p {
    margin: 0;
}

/* Responsive Layout */
@media (max-width: 750px) {
    .navbar {
        flex-direction: column;
        gap: 10px;
        padding: 12px;
    }

    .nav-links {
        justify-content: center;
        gap: 14px;
    }

    .example-grid {
        grid-template-columns: 1fr;
    }

    .hero h1 {
        font-size: 29px;
    }

    .content-section {
        padding: 20px;
    }

    .floating-help {
        right: 14px;
        bottom: 14px;
    }
}
```

## 5. Explanation of CSS Positioning Properties

### A. `position: sticky`

The navigation bar uses:

```css
.navbar {
    position: sticky;
    top: 0;
    z-index: 1000;
}
```

It behaves like a normal element until it reaches the top of the viewport, where it sticks while scrolling within its scrolling container.

### B. `position: fixed`

The floating Help button uses:

```css
.floating-help {
    position: fixed;
    right: 24px;
    bottom: 24px;
    z-index: 2000;
}
```

It remains at the bottom-right of the viewport while the page scrolls.

### C. `position: relative`

The course card uses:

```css
.course-card {
    position: relative;
}
```

This makes the card the positioning reference for its absolutely positioned badge.

### D. `position: absolute`

The badge uses:

```css
.badge {
    position: absolute;
    top: 12px;
    right: 12px;
}
```

It is placed 12 pixels from the top and right edges of the nearest positioned ancestor, which is the course card.

### E. `position: static`

Static positioning is the default. The element remains in the normal document flow, and `top`, `right`, `bottom`, and `left` do not reposition it.

### F. `z-index`

The example uses different stacking values:

| Element | `z-index` | Purpose |
|---|---:|---|
| Sticky navbar | 1000 | Keeps navigation above normal page content |
| Course card | 1 | Establishes a stacking level for the card |
| Badge | 2 | Positions the badge above the card's content |
| Floating Help button | 2000 | Keeps the button above most page elements |

`z-index` works within stacking-context rules; a larger number does not automatically place an element above every element in every stacking context.

## 6. Steps to Run the Project

1. Open Visual Studio Code.
2. Create a folder named `Assignment-6.4`.
3. Create `index.html` and `style.css` inside the folder.
4. Paste the HTML code into `index.html`.
5. Paste the CSS code into `style.css`.
6. Save both files.
7. Open `index.html` with the Live Server extension.
8. Scroll down to check that the navigation bar sticks to the top.
9. Confirm that the Help button remains in the bottom-right corner.
10. Locate the Featured Course card and observe the NEW badge at its top-right corner.
11. Resize the browser window to test the responsive layout.

## 7. Screenshot Instructions

Take a screenshot of the actual running webpage in Chrome.

**Screenshot 1 — Main Positioning Demo**

1. Open the page using Live Server.
2. Keep the navigation bar visible at the top.
3. Scroll to the Featured Course section so the NEW badge is visible.
4. Make sure the floating Help button is visible in the bottom-right corner.
5. Take a screenshot using `Win + Shift + S`.

Save the image as:

`positioning-practice.png`

The screenshot should show all three required features:

- Sticky navigation bar at the top.
- Floating fixed Help button.
- NEW badge positioned inside the course card.

If all three features do not fit in one screenshot, take two screenshots: one showing the sticky navbar and Help button, and another showing the course card and its badge.

## 8. Expected Output

- A webpage with multiple scrollable sections.
- A sticky navigation bar that stays near the top during scrolling.
- A fixed floating Help button in the bottom-right corner.
- A course card with an absolute NEW badge.
- A relative parent element for the badge.
- Demonstrations of static, relative, and absolute positioning.
- Appropriate `z-index` values for overlapping elements.
- A responsive layout for smaller screens.

## 9. Result

A working webpage was created using CSS positioning properties. The sticky navbar, fixed floating Help button, and absolute badge inside a relative card demonstrate how positioning and stacking order can be used to create practical webpage layouts.

## 10. Conclusion

CSS positioning provides control over the placement of webpage elements. Sticky positioning is useful for navigation, fixed positioning for persistent controls, relative positioning for establishing a reference point, and absolute positioning for badges and overlays. The `z-index` property helps manage overlapping elements.

## 11. Submission Checklist

- [ ] `index.html`
- [ ] `style.css`
- [ ] `positioning-practice.png`
- [ ] Working sticky navbar
- [ ] Fixed floating Help button
- [ ] Absolute badge inside a relative card
- [ ] Result and conclusion
