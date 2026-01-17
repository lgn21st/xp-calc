# Project Context: XP Reward Center (XP 兑换中心)

## Project Overview
This project is a single-file Progressive Web App (PWA) designed to help a parent and child calculate exchange rates between **Duolingo XP**, **Pocket Money (SGD)**, and **Video Game Time**.

It is built as a standalone HTML file containing all necessary CSS and JavaScript, ensuring it can run offline and is easy to deploy (e.g., via GitHub Pages or direct file transfer).

## Tech Stack
*   **HTML5:** Structure and PWA meta tags (mobile-capable, status bar style).
*   **CSS:** Embedded styles mimicking iOS design language (San Francisco font, rounded cards, blur effects, dark mode support).
*   **JavaScript:** Vanilla JS for real-time bidirectional calculation and DOM manipulation.

## Key Files
*   **`index.html`**: The complete application source code.
    *   **Logic**: Contains the conversion rates (`XP_PER_MIN = 15`, `MIN_PER_SGD = 3`) and event listeners for the three input fields.
    *   **UI**: Three cards for XP, Money, and Time, with specific input types for mobile keyboards. Canvas-based dynamic icon generation.

## Conversion Logic
The application uses **Minutes** as the base unit for calculation:
*   **150 XP = 10 Minutes** (Base Rate: 1 Min = 15 XP)
*   **10 Minutes = 3.33 SGD** (Base Rate: 1 SGD = 3 Min)

## Features
*   **Instant Calculation**: Updating any field immediately updates the other two.
*   **Input Protection**: Automatically blocks negative numbers and invalid characters ('e', '-', '+').
*   **Clear Button**: A dedicated button in the header to instantly reset all fields.
*   **Smart Formatting**:
    *   Time is displayed in minutes in the input field.
    *   An additional text display converts minutes to "Hours + Minutes" format (e.g., "1 小时 7 分钟").
*   **Mobile Optimized**:
    *   `inputmode="decimal"` triggers the numeric keypad on iOS.
    *   Auto-selects text on focus for quick editing.
    *   Supports "Add to Home Screen" for a full-screen app experience.
*   **Theming**: Automatic Dark/Light mode based on system preference. Duolingo-inspired green accents.

## Development & Usage
1.  **Modify Rates**: Edit the `XP_PER_MIN` and `MIN_PER_SGD` constants in the `<script>` section of `index.html`.
2.  **Deployment**: Host the `index.html` file on any static server or simply open it locally in a browser.
3.  **Mobile Usage**: Open in Safari on iPhone -> Share -> Add to Home Screen.
