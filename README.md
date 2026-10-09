# Building Mini-React VNode & Mounting Engine

## Overview

This project implements a lightweight Mini-React engine from scratch to demonstrate the fundamental concepts behind Virtual DOM creation and DOM mounting.

The implementation focuses on creating Virtual Nodes (VNodes), converting VNodes into real DOM elements, preserving semantic HTML elements, and safely rendering text content without interpreting it as HTML.

## Learning Objectives

* Understand the structure of a Virtual Node (VNode).
* Implement `createTextElement()` for text nodes.
* Implement `createElement()` to construct VNode trees.
* Implement `renderToDOM()` to mount VNodes into the browser DOM.
* Preserve semantic HTML elements such as `main`, `header`, `section`, and `button`.
* Handle event listeners and element properties.
* Verify rendering behavior using Chrome DevTools.
* Prevent HTML-like text from being interpreted as executable markup.

## Technologies

* HTML5
* CSS3
* JavaScript ES Modules
* Browser DOM API
* Chrome DevTools
* Git and GitHub

## Project Structure

```text
24522046_Building-Mini-React-VNode-And-Mounting-Engine/
├── index.html
├── mini-react.js
├── test-runner.js
└── README.md
```

## Core Implementation

### 1. `createTextElement()`

Creates a VNode representing text content. The text is stored in `props.nodeValue`, and the node contains an empty children array.

### 2. `createElement()`

Creates VNodes from an element type, properties, and children. It normalizes nested child arrays, filters out `null`, `undefined`, and boolean children, and converts primitive values into text VNodes.

### 3. `renderToDOM()`

Recursively converts VNodes into real DOM nodes using browser DOM APIs.

The implementation supports:

* Semantic HTML element creation.
* Text node creation.
* Element attributes and properties.
* Class and style mapping.
* Event listener registration.
* Recursive child mounting.

## Security Considerations

Text content is rendered using `document.createTextNode()` instead of `innerHTML`.

As a result, HTML-like input such as `<img src=x onerror=alert(1)>` is treated as plain text rather than being parsed as an HTML element.

## Testing and Verification

The project includes a lightweight test runner that verifies:

* Text VNode creation.
* VNode construction and child normalization.
* Semantic element preservation.
* DOM mounting for `main`, `section`, and `button`.
* Safe handling of HTML-like text.

Chrome DevTools is used to inspect the resulting DOM tree and Console output.

## How to Run

1. Clone the repository.
2. Open the project folder in Visual Studio Code.
3. Start a local development server, such as the VS Code Live Server extension.
4. Open `index.html` in the browser.
5. Open Chrome DevTools and inspect the Console and Elements panels.

The expected test output is:

```text
All Mini-React tests passed.
```

## Expected Result

The application renders a simple page containing a header, an Exercise 1 section, and a button.

The Console reports successful test results, the button event handler logs `Ping` when clicked, and HTML-like text is displayed without being interpreted as markup.

## Git Commit Requirements

The exercise specifies the following core implementation commits:

1. `feat(core): implement createElement factory`
2. `feat(core): implement renderToDOM`

## Author

**Võ Tấn Vũ**

GitHub: [votanvu2006](https://github.com/votanvu2006)

## License

This project was created for educational purposes as part of a Web Application Development exercise.
