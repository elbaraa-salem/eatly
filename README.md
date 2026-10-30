# Eatly — React Frontend Training Project

**A food-delivery interface implemented during company training, with reusable React components, responsive styling, and client-side page navigation.**

## Overview

Eatly is a frontend implementation of a food-delivery website concept. It presents featured restaurants and dishes, promotional content, purchase-summary illustrations, customer testimonials, and sign-in and sign-up screens.

I completed this project during my training at a company. It complements the training certificate included in my scholarship application by providing a concrete example of the practical work undertaken during that training. The project demonstrates the implementation of a supplied interface design as an organised React application.

The focus of this project is frontend development: structuring pages, creating reusable components, styling layouts, and adapting the presentation to different screen widths. It is an interface prototype, not a complete food-ordering service.

## Training Context and Objectives

The original assignment supplied an Eatly design reference and identified practical learning objectives in web development, including semantic markup, responsive layout, browser compatibility, decorative styling, and animation.

The submitted implementation provides evidence of work in component-based development, page composition, CSS styling, responsive presentation, and routing. Assignment objectives describe the intended training scope; they do not establish that every objective has been independently tested or fully completed.

The portfolio contribution is the frontend implementation of the supplied design. This README does not claim original authorship of the visual design, brand, illustrations, or sample marketing content.

## Implemented Interface

| Area | What is included |
| --- | --- |
| Landing page | Header, introductory section, promotional statistics, app promotion, restaurant and dish sections, purchase-summary illustration, testimonials, subscription form, and footer. |
| Restaurant cards | Repeated cards showing a restaurant name, category, preparation-time label, and rating. |
| Dish cards | Reusable cards displaying images, categories, names, time labels, ratings, and prices. |
| Purchase-summary illustration | Example order statuses and expenditure cards using static sample values. |
| Sign-in screen | Email and password fields, a sign-in button, and navigation to the sign-up screen. |
| Sign-up screen | Registration-style fields and visual account-provider options. |
| Responsive presentation | CSS media queries and viewport-based changes to the header and footer. |
| Page routing | React Router routes for the main page, sign-in page, and sign-up page. |

Restaurant information, reviews, order statuses, financial figures, and promotional statistics are demonstration content. They are not evidence of real customers, sales, payments, or service performance.

## User Journey

A visitor opens the landing page and explores the food-delivery concept through restaurant and dish cards. The page combines product information with supporting promotional sections and an example purchase summary.

On the desktop header, the visitor can navigate to the sign-in or sign-up screen. These screens demonstrate the layout of account-access interfaces; they do not create accounts or authenticate users.

The layout includes adaptations for narrower screens. The header changes its presentation below the desktop breakpoint, and multiple sections adjust their styling through media queries. The compact header includes a menu icon, but opening a functional mobile navigation menu is not implemented in this version.

## Technology Stack

| Technology | Role in the project |
| --- | --- |
| JavaScript and JSX | Define interface components, page composition, and rendering logic. |
| React 18 | Provides the component model and hooks used for viewport state. |
| React Router 6 | Maps URL paths to the landing, sign-in, and sign-up pages. |
| CSS | Controls typography, spacing, component appearance, and responsive layouts. |
| SVG and image assets | Provide icons, food imagery, and decorative interface elements. |
| Create React App / react-scripts | Supplies development, build, and test commands. |
| gh-pages | Provides a configured publishing command for the generated build. |

## Project Organisation

| Location | Responsibility |
| --- | --- |
| `src/App/` | Application component and route definitions. |
| `src/Pages/` | Main page and account-access screens. |
| `src/Pages/MainPage/UI/` | Header and footer components. |
| `src/Widgets/` | Larger page sections, including featured dishes, restaurants, testimonials, and purchase summaries. |
| `src/Shared/UI/` | Reusable dish, restaurant, dashboard, statistics, and purchase-card components. |
| `src/Shared/Hooks/` | Viewport-dimension hook. |
| `src/Shared/Icons/` | Shared icon component. |
| `src/Shared/imgs/` | Image assets used by the interface. |

This separation allows a page to be assembled from larger sections while repeated visual elements remain in shared components.

## Engineering Highlights

### Reusable components with explicit inputs

Dish and restaurant components receive values through props, including titles, category labels, ratings, and preparation times. The parent sections define sample items in arrays and render them using `map`. This demonstrates how repeated content can share one component implementation while displaying different data.

### Separation between pages, sections, and shared elements

The main page composes independent sections instead of placing its entire interface in one component. Shared cards can be reused by those sections, keeping repeated markup in identifiable locations and making individual interface elements easier to revise.

### Responsive styling and viewport state

The project combines CSS media queries with a custom `useWindowDimensions` hook. The hook uses React state and an effect to track browser resize events, and removes its event listener during cleanup. The main page passes the current width to the header and footer for conditional rendering.

Several landing-page sections use a 991-pixel breakpoint, while the account-access screens include a 700-pixel breakpoint. These are implemented layout rules; comprehensive device and browser testing has not been established by this review.

### Client-side navigation

The application uses `BrowserRouter`, `Routes`, and `Route` to organise separate screens. Navigation components connect the main page to the account-access interfaces without requiring separate HTML documents for each screen.

## Running the Project Locally

Install Node.js and npm, then run the following commands from the project directory:

```bash
npm ci
npm start
```

The application defines its routes under `/eatly`. With the default development-server port, open:

```text
http://localhost:3000/eatly/
```

The account-access routes are:

```text
/eatly/signin
/eatly/signup
```

Create a production build with:

```bash
npm run build
```

The package also includes `npm run deploy`, which builds the project and publishes the build directory through `gh-pages`. Before using it, update the `homepage` setting and confirm the intended repository and deployment configuration. Hosting must also account for direct requests to client-side routes.

## Current Scope and Verification

This version contains frontend screens and static demonstration data. It does not implement a backend, database, real authentication, social sign-in, shopping cart, checkout, payment processing, order tracking, or newsletter subscription service. Several promotional links and controls are placeholders.

The supplied test file is the default “learn React” starter test and does not describe the current interface. It should be replaced with project-specific checks before the test suite is used as evidence of correctness.

This README was prepared through inspection of the source and original assignment. No successful build, automated test run, live deployment check, or cross-browser verification is claimed here.

## Further Development

The next improvements would be to complete mobile navigation, correct the sign-up screen's sign-in link, and connect forms to deliberate validation and submission behaviour. Accessibility work should include meaningful form labels, keyboard interaction, and appropriate image descriptions.

Further engineering work could add stable keys to mapped component lists, remove unused imports, consolidate repeated styles, and introduce tests for routes, cards, and responsive navigation. Backend integration and persistent ordering workflows would be separate extensions beyond the original frontend scope.

## Academic Portfolio Relevance

Eatly provides a practical example of frontend work completed during company training. It connects the training certificate to an inspectable software artifact and demonstrates experience with React components, props, list rendering, routing, browser events, and responsive CSS.

Within a software engineering portfolio, its value is evidence of interface implementation and code organisation. Alongside projects involving databases and backend services, it shows experience with another part of application development: turning a supplied visual specification into structured frontend code.

## Design Reference

The original training assignment identifies the following supplied design:

[Eatly design reference in Figma](https://www.figma.com/file/3aWfY7szo0Ja4M5BKWdia6/Eatly-(1-week)?type=design&node-id=0%3A1&mode=design&t=t6f2ecEr5XWqqvcX-1)

Design and asset attribution should be retained when presenting the implementation.
