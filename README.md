# Astro SQLite HTMX PoC

**Proof-of-concept for a dynamic web application using [Astro.build](https://astro.build/), powered by a [SQLite database](https://sqlite.org/about.html) and progressively enhanced with [HTMX](https://htmx.org/).**


## 🚀 Project Structure

This web app consists of an index page with a filterable list and a detail page for each item. The items are loaded from a SQLite database file stored within the project.

```
├── public/
│   └── northwind.sqlite        <-- database file
├── src/
│   ├── components/
│   │   └── ProductList.astro   <-- used in index page & partial
│   ├── layouts/
│   │   └── Layout.astro        <-- shared between pages
│   └── pages/
|       ├── index.astro         <-- filterable list page
│       └── products.astro      <-- item detail page
└── package.json
```


## 🧞 Progressive enhancement

This web app works without client-side scripts. The list on the index page can be filtered server-side using the `form` on the page. The index and detail pages are linked with regular `a`nchor tags.

The app is enhanced with HTMX. When enhancement kicks in, the `form` is submitted asynchronously and the list is updated asynchronously. On navigation, the next page is also fetched asynchronously and the HTML is updated without a full page reload.


## 🫙 Database

The database (borrowed from [`jpwhite3/northwind-SQLite3`](https://github.com/jpwhite3/northwind-SQLite3)) structure:

![](https://raw.githubusercontent.com/jpwhite3/northwind-SQLite3/master/images/Northwind_ERD.png)


## 🧰 Commands

All commands are run from the root of the project, from a terminal:

| Command                | Action                                             |
| :--------------------- | :------------------------------------------------- |
| `npm install`          | Installs dependencies                              |
| `npm run dev`          | Starts local dev server at `localhost:3000`        |
| `npm run build`        | Build your production site to `./dist/`            |
| `npm run preview`      | Preview your build locally, before deploying       |
| `npm run astro ...`    | Run CLI commands like `astro add`, `astro preview` |
| `npm run astro --help` | Get help using the Astro CLI                       |
