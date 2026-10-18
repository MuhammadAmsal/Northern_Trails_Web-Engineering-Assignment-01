# Northern Trails - Multi-Page Travel Website (HTML + CSS only)

A responsive 10-page travel website for a fictional tour agency in northern Pakistan.
Built with HTML5 and CSS3 only. There is no JavaScript anywhere in the project.

## How to run locally

1. Unzip the project (or keep the `northern-trails` folder as it is).
2. Open the folder and double-click `index.html`. It opens in your default browser.
   Alternatively, in Chrome, Edge or Firefox use **File > Open File** and select `index.html`.
3. Use the navigation bar to move between pages. No server, build step or internet connection is needed.

Optional: to test on a phone or tablet, run `python3 -m http.server 8000` inside the folder
and open `http://localhost:8000` (or your computer's local IP address) on the device.

To check responsiveness, resize the browser window or open the browser developer tools
(F12) and switch to the device toolbar.

## Website Architecture Note

### 1. Number of Pages

The site has **10 pages**:

| # | File | Name | Purpose |
|---|------|------|---------|
| 1 | `index.html` | Home | Landing page with hero, key figures, featured destinations, benefits, testimonials and call to action |
| 2 | `destinations.html` | Destinations | Overview of six mountain regions plus Lahore, with a comparison table |
| 3 | `hunza.html` | Hunza Valley | Detailed destination guide: highlights, seasons table, quick facts |
| 4 | `packages.html` | Packages | Three priced tour packages and a feature comparison table |
| 5 | `itinerary.html` | Itinerary | Seven-day day-by-day timeline and packing list |
| 6 | `gallery.html` | Gallery | Image grid with hover captions |
| 7 | `blog.html` | Blog | Three travel articles with a sidebar |
| 8 | `about.html` | About | Story, values and team |
| 9 | `faq.html` | FAQ | Expandable questions using the native `details` element |
| 10 | `contact.html` | Contact | Enquiry form and office information |

### 2. Navigation Structure

- Every page uses the same `header` containing a `nav` element with ten standard `<a>` links,
  so any page can be reached from any other page in one click.
- The current page is marked with `class="active"` and `aria-current="page"`; CSS gives it an orange background.
- The logo links to `index.html`.
- Each page repeats a consistent `footer` with links grouped under Explore and Plan.
- Contextual links tie related content together: buttons on cards, breadcrumbs on inner pages,
  sidebars on the blog and FAQ, and call-to-action bands that lead to the Contact or Packages pages.
- Some links use fragment identifiers (for example `destinations.html#skardu` and `#post-1`)
  to jump to a section inside a page.
- On small screens the menu collapses behind a hamburger icon. It works without JavaScript by
  using a hidden checkbox and the CSS `:checked` sibling selector.

### 3. CSS Implementation

All styling lives in one file, `css/style.css`, organised into numbered sections.

- **Colors:** a palette defined as CSS custom properties in `:root` (teal, orange accent, sand backgrounds, dark ink text), reused everywhere.
- **Typography:** Georgia for headings and the system sans-serif stack for body text. Heading sizes use `clamp()` so they scale smoothly.
- **Layout:** CSS Grid for card grids, the gallery, statistics, footer and two-column sections. Flexbox for the navigation bar, hero buttons and card interiors.
- **Visual style:** rounded corners, soft box shadows, borders and gradient backgrounds on cards, banners and call-to-action bands.
- **Interaction:** hover and focus effects on navigation links, buttons, cards and gallery images, using transitions only.
- **Responsiveness:** a mobile-friendly viewport meta tag, flexible images (`max-width: 100%`) and three breakpoints (1024px, 860px and 640px). Grids reduce from four or three columns to two and then one, and the navigation turns into a hamburger menu. A `prefers-reduced-motion` query and a print rule are also included.
- **Consistency:** shared classes (`.container`, `.section`, `.card`, `.btn`, `.page-banner`, `.cta-band`) are used on every page so the design is uniform.

### 4. File Structure

```
northern-trails/
├── index.html
├── destinations.html
├── hunza.html
├── packages.html
├── itinerary.html
├── gallery.html
├── blog.html
├── about.html
├── faq.html
├── contact.html
├── README.md
├── css/
│   └── style.css          (single shared stylesheet)
└── images/
    ├── logo.svg
    ├── hero.svg
    ├── hunza.svg
    ├── skardu.svg
    ├── swat.svg
    ├── naran.svg
    ├── fairy-meadows.svg
    ├── lahore.svg
    └── chitral.svg
```

HTML files sit at the project root so links between them are simple relative filenames.
The stylesheet is in `css/` and images are in `images/`.

## Image Sources

All images are **original SVG illustrations** hand-written for this project. They are stored in
`images/`, need no download, carry no copyright restrictions and scale sharply on any screen.
The text content, names, prices and contact details are fictional and for demonstration only.

## Requirements Checklist

- HTML5 and CSS3 only, with no JavaScript: yes
- Separate HTML file per page and a separate CSS file: yes
- Semantic elements (`header`, `nav`, `main`, `section`, `article`, `aside`, `footer`): yes
- Consistent navigation, active-page highlight, no broken internal links: yes
- Flexbox and Grid, hover effects and media queries: yes
