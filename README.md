
```markdown
# PDF Viewer Application

## Goal of the Project

The goal of this project is to create a simple, interactive PDF viewer that allows users to view PDF files directly in the browser, with options to navigate between pages. This project leverages the `pdf.js` library to render PDF files on a canvas element and provides features such as page navigation and error handling.

## Purpose of the Project

The purpose of this project is to:
- **Render PDF Files**: Provide users with a way to display PDF files in the browser without the need for external plugins or downloads.
- **Navigate Pages**: Enable users to easily navigate through the pages of a multi-page PDF document using previous and next buttons.
- **Enhance User Experience**: Ensure smooth rendering of PDF pages by implementing queue management, allowing for efficient page loading even while the current page is rendering.

---

## Overview

This project creates a basic PDF viewer in the browser using the `pdf.js` library. The PDF viewer renders the content of a PDF file onto a HTML5 canvas and provides user controls for navigating between pages of the PDF. It also handles error scenarios, such as missing files or rendering issues, by displaying appropriate error messages to the user.

### Key Features:
- **PDF Rendering**: Loads and renders a PDF document onto a canvas element.
- **Page Navigation**: Allows users to navigate between pages using 'Previous' and 'Next' buttons.
- **Error Handling**: Displays error messages in case the PDF cannot be loaded or other issues arise.
- **Dynamic Canvas Resizing**: Adjusts the canvas dimensions dynamically based on the current page's viewport to maintain proper scaling.

## Technology Stack

- **JavaScript**: Core programming language used for handling PDF rendering and user interactions.
- **pdf.js**: A powerful library to display PDF files within a web page.
- **HTML5 Canvas**: For rendering the PDF content directly onto the web page.

---

## Installation and Setup

To run this project locally, follow the steps below:

### Prerequisites:
- A modern browser that supports JavaScript and HTML5 Canvas.
- The `pdf.js` library (included via CDN or local installation).

### Steps to Run:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/pdf-viewer-app.git
   cd pdf-viewer-app
   ```

2. **Download the Required Files**:
   Ensure you have `pdf.js` included in your project. You can either:
   - Download the library from the [PDF.js GitHub repository](https://github.com/mozilla/pdf.js).
   - Use a CDN version of PDF.js:
     ```html
     <script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/2.10.377/pdf.min.js"></script>
     ```

3. **Set up your PDF file**:
   Place your PDF file (e.g., `con1.pdf`) inside the `docs` folder.

4. **Run the Application**:
   Open the `index.html` file in your browser, and the PDF viewer will load the document and display it.

## Code Explanation

### Core Functions

- **`renderPage(num)`**: 
  - Renders the given page number (`num`) from the PDF document onto the canvas. It resizes the canvas based on the page dimensions using the viewport's width and height. It also tracks the rendering state to prevent duplicate rendering.

- **`queueRenderPage(num)`**: 
  - Ensures that only one page is being rendered at a time. If a rendering operation is already in progress, it queues the next page until the current one finishes.

- **`showPrevPage()` and `showNextPage()`**: 
  - These functions handle the navigation between pages. They decrement or increment the page number, and trigger the rendering of the new page.

- **Error Handling**: 
  - If an error occurs while fetching or rendering the PDF (such as a missing file), an error message is displayed to the user, and the navigation bar is hidden.

### Event Listeners

- **Button Events**:
  - The `#prev-page` and `#next-page` buttons allow users to navigate between pages by triggering the `showPrevPage` and `showNextPage` functions, respectively.

### Example Structure

```bash
.
├── docs
│   └── con1.pdf               # Example PDF document
├── index.html                  # Main HTML file for the viewer
├── app.js                      # JavaScript logic for rendering and navigation
└── styles.css                  # Basic styles for the application
```

---

## Usage

1. **Load PDF**: Upon loading the page, the PDF document is displayed in the canvas element. The first page of the PDF is shown by default.
2. **Navigate Pages**: Use the "Previous" and "Next" buttons to navigate through the pages of the PDF.
3. **Error Handling**: If the PDF file cannot be loaded, an error message is displayed at the top of the page.

## Future Enhancements

- **Zoom In/Out Functionality**: Add buttons to zoom in and out of the PDF pages for a better viewing experience.
- **Search Feature**: Allow users to search for specific keywords or phrases within the PDF.
- **Thumbnails**: Display thumbnails of all pages for easier navigation.
- **Download PDF**: Include a button to allow users to download the PDF.

---

## License

This project is licensed under the MIT License. Feel free to modify and use the code for your own purposes.
```
