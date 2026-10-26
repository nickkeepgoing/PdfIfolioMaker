# PdfIfolioMaker

PdfIfolioMaker is a browser-based portfolio maker for turning project photos,
certificates, competition records, and other visual evidence into a polished
A4 PDF. It is designed to work as a lightweight static site with no backend
and no account required.

## Features

- Create and manage multiple portfolio projects.
- Add any number of pages to a project.
- Upload, replace, delete, and reorder images on each page.
- Choose automatic image layout or a one-, two-, or three-column grid.
- Add a project title, subtitle, owner name, page titles, and descriptions.
- Customize the font, accent color, background color, and text color.
- Automatically save projects in the browser using IndexedDB.
- Export the portfolio as an A4 PDF.
- Keep exported PDFs below the 5 MB limit by progressively reducing image
  resolution when necessary.
- Preserve image quality for small text and QR codes as much as possible.
- Use the interface responsively on desktop and smaller screens.

## Requirements

- A modern web browser with IndexedDB support.
- Internet access when opening the page, because the app loads Google Fonts,
  `html2canvas`, and `jsPDF` from CDNs.

## Run locally

Because the app is a static site, it does not require a build step.

### Option 1: Open the file directly

Double-click `index.html` to open it in a browser. A local web server is
recommended for the most consistent browser behavior.

### Option 2: Start a local server

From the project directory, run:

```bash
python -m http.server 8765
```

Then open <http://localhost:8765> in your browser.

## How to use

1. Click **+ โปรเจกต์ใหม่** to create a project.
2. Enter the project name, context, and owner name.
3. Select a font and customize the colors.
4. Add pages and upload images for each page.
5. Select automatic layout or a fixed column layout.
6. Review the preview and click **ดาวน์โหลด PDF** to export.

Projects are saved automatically in the current browser profile. Clearing the
browser's site data will remove saved projects, so export important portfolios
before clearing browser storage.

## Project structure

```text
.
├── index.html          # Complete application: UI, styling, and JavaScript
├── README.md           # Project documentation
└── .claude/
    └── launch.json     # Optional local launch configuration
```

## Technologies

- HTML, CSS, and vanilla JavaScript
- IndexedDB for local project storage
- [html2canvas](https://html2canvas.hertzen.com/) for page rendering
- [jsPDF](https://github.com/parallax/jsPDF) for PDF generation
- Google Fonts for Thai and Latin font choices

## Privacy

Images and project data stay in the browser's local IndexedDB storage. The
application does not upload portfolio data to a server. External CDN requests
are made only for the libraries and fonts referenced by `index.html`.

## License

No license has been selected yet. Add a license file before distributing the
project for reuse.
