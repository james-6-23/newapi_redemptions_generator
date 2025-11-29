# NewAPI Redemption Code Generator

## Project Overview

This project is a standalone, browser-based utility designed to generate SQL `INSERT` statements for creating bulk redemption codes in the NewAPI system. It is a single-file application (`index.html`) that bundles the user interface, styling, and generation logic.

**Key Features:**
*   **Bulk Generation:** Generate up to 1000 redemption codes at once.
*   **Custom Keys:** Supports custom key prefixes and uses a specific generation logic (Prefix + Random + Timestamp + Counter) to ensure uniqueness.
*   **Flexible Quotas:** Supports both fixed and random quota amounts (automatic conversion: $1 = 500,000 Tokens).
*   **Expiration Management:** Options for codes that never expire, expire after a set number of days, or expire on a specific date.
*   **Export:** Features to copy generated SQL, copy raw keys, or download keys to a text file.

## Building and Running

Since this is a static HTML application with no dependencies or build steps, "deployment" is straightforward.

**To Run:**
1.  Locate the `index.html` file in the project directory.
2.  Open `index.html` in any modern web browser (Chrome, Edge, Firefox, etc.).

**No build commands (npm, make, etc.) are required.**

## Development Conventions

*   **Architecture:** Monolithic single-file HTML. All CSS (styles) and JavaScript (logic) are embedded directly within `index.html`.
*   **Technology Stack:**
    *   **HTML5:** Semantic structure.
    *   **CSS3:** Custom styling with heavy use of gradients, shadows, and animations. No external CSS frameworks are used, though the aesthetic mimics modern glassmorphism.
    *   **JavaScript (ES6+):** Vanilla JavaScript for DOM manipulation and logic. No external libraries are used.
*   **Language:** The user interface and comments are primarily in Chinese (Simplified).
*   **Code Style:**
    *   CSS is located in the `<style>` block in `<head>`.
    *   JavaScript is located in the `<script>` block at the end of `<body>`.
    *   Key generation logic relies on `crypto.getRandomValues` for randomness.

## Key Logic

*   **Token Conversion:** Hardcoded rate of `1 USD = 500,000 Tokens`.
*   **Key Format:** Fixed 32-character length.
    *   `Prefix` (User defined)
    *   `Random Part` (crypto-secure)
    *   `Timestamp` (Base36 encoded)
    *   `Counter` (Base36 encoded)
