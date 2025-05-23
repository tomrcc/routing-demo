# Routing Demo

Add the routing.json file to a collection in CloudCannon to enable management of routes in app.


Places to look:
  - cloudcannon.config.yaml (routing collection)
  
  - .cloudcannon/routing.json


[CloudCannon routing documentation](https://cloudcannon.com/documentation/articles/configure-custom-routing/)

## Getting Started

To start using this template, go to the [GitHub repository](https://github.com/CloudCannon/astro-starter/), and click `Use this template` to make your own copy.

### Commands

All commands are run from the root of the project, from a terminal:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies                            |
| `npm run dev`             | Starts local dev server at `localhost:4321`      |
| `npm run build`           | Build your production site to `./dist/`          |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI                     |

### Local Development

1. Clone the repository
2. Run `npm install`
3. Run `npm start`

## Features

### Bookshop

[Bookshop](https://cloudcannon.com/documentation/guides/bookshop-astro-guide/) is a component development workflow for static websites.

Build custom components that non-technical editors can use in a page building experience in CloudCannon.

Bookshop is already set up on this project, so that you can start building components straight away.

To add a new component run `npm run new-component <your-new-component>` in the root of your repository.

### Blog & Documentation Pages

Blog section with tags and pagination included.

Documentation, blog and other text heavy sections should replicate how the blog section is implemented in this template.

The blog pages in this template use MDX to allow for snippets. Snippets allow you to use HTML components throughout your markdown text.

A common layout, with changing markdown content is favored for these kinds of text heavy pages, rather than using Bookshop components - which are defined and managed in your markdown pages frontmatter.

These text heavy pages will be edited in CloudCannon's content editor, rather than the visual editor used for building pages with Bookshop components.

### Image Optimization

An [Astro Image](https://docs.astro.build/en/guides/images/#image--astroassets) is used in the two placeholder components in this template.
An Astro Image will process an image in your src/assets/images folder, and output an optimized image, like below:

```html
<img
  src="/_astro/my_image.hash.webp"
  srcset="
    /_astro/my_image.hash.webp  240w,
    /_astro/my_image.hash.webp  540w,
    /_astro/my_image.hash.webp  720w,
    /_astro/my_image.hash.webp 1600w
  "
  sizes="
    (max-width: 360px) 240px,
    (max-width: 720px) 540px,
    (max-width: 1600px) 720px,
    1600px
  "
  alt="A description of my image."
  width="1600"
  height="900"
  loading="lazy"
  decoding="async" />
```

This template also demonstrates [how to set](https://cloudcannon.com/documentation/articles/adjusting-the-uploads-path/) `uploads` paths on a per-input level, to allow for both processed and unprocessed images on one site.

On this template, by default, image inputs are opened at `public/images`, meaning they are unprocessed images.

Components that use the Astro Image component are configured so the image source input opens at `src/assets/images`, which are images to be processed and optimized on build.

### SEO Controls

SEO inputs come set up and configured to allow editors to control SEO on a page-by-page, and sitewide basis.

### Tailwind CSS

Use Tailwind to add utility classes to your HTML, allowing you to style your components without leaving your HTML.
This can be used in combination with normal CSS and SCSS styling, leaving you to add styles to your site however you want.

To remove Tailwind CSS:

1. Remove the following packages from your `package.json`:

```json
"dependencies": {
  "tailwindcss": "^3.3.3",
  "@astrojs/tailwind": "^5.0.0"
}
```

2. Remove mentions of Tailwind from your `astro.config.mjs`

```mjs
import { defineConfig } from 'astro/config';
import tailwind from '@astrojs/tailwind';

export default defineConfig({
  // ...
  integrations: [tailwind()],
});
```

3. Delete your `tailwind.config.mjs` file.

### Font Awesome Icons

A Font Awesome Icon free icon pack is included, removing the need to set up your own kit in Font Awesome.

To add more icons:

1. Go to the [Font Awesome icon list](https://fontawesome.com/search?o=r&m=free)
2. Pick a free icon
3. Go to `src/components/utility/icon.jsx`
4. Import the component from `'@fortawesome/free-solid-svg-icons'`, `'@fortawesome/free-regular-svg-icons'`, or `'@fortawesome/free-brands-svg-icons'`, depending on which kind of icon it is. Tip: After entering 'fa' into one of the destructured objects, you should see an autocomplete dropdown list to help you with the correct syntax.
5. Add another case to the switch statement following the format the other icons use.
6. Add the name you just used in the conditional of the switch statement to `data/icons.json`, which populates the icon dropdown list used for icons in the placeholder components.

To remove Font Awesome Icons:

1. Remove the following packages from your `package.json`:

```json
  "dependencies": {
  "@fortawesome/fontawesome-svg-core": "^6.5.2",
  "@fortawesome/free-brands-svg-icons": "^6.5.2",
  "@fortawesome/free-regular-svg-icons": "^6.5.2",
  "@fortawesome/free-solid-svg-icons": "^6.5.2",
  "@fortawesome/react-fontawesome": "^0.2.0"
  }
```

2. Remove `src/components/utility/icon.jsx`
3. Remove any imports of the icon

```Astro
import Icon from '../utility/icon';
```

4. Remove `icons.json`
5. Remove any select inputs that were using the icon

```yaml
icon:
  type: select
  options:
    values: data.icons
```

6. Remove icons from your defined data in `cloudcannon.config.yml`

```yaml
data_config:
  icons:
    path: data/icons.json
```

### Data files

Demonstrates using data files to:

- Populate select inputs in CloudCannon. This is powerful for allowing editors to make styling changes to the page, within a set design system populated by an editable data file.
- Set sitewide values such as the overall site SEO settings.
- Control header and footer data to allow editors to control navigation.

### Schemas

Shows how to set up schemas in CloudCannon to allow for non-technical editors to create new pages, with preset frontmatter and content. Schemas can be defined on a collection level, allowing your new blog pages to be different to your new landing pages. This allows for your text heavy blog/docs pages to be built and edited in the content editor, while your other pages can be built with Bookshop in the visual editor.

### CloudCannon Config

A `cloudcannon.config.yml` file has been provided with some configuration that starts to show what can be done to configure the CMS.

The placeholder Bookshop components show how to configure your components to control inputs and previews in CloudCannon.

### Markdown Styles

The markdown toolbar has most of the options supported in the rich text editor, along with the necessary styling.
See the CloudCannon [Docs](https://cloudcannon.com/documentation/articles/configure-your-rich-text-editors/) for more information.

### CSS Variables

Shows how to set global CSS variables in Astro, to set commonly used values like `pagePadding`, and `pageContainer`.

Extra work could be done to write a `node fs` script to write said values from a data file to the appropriate places in the code, which would then allow editors to control sitewide styles like page max-width and padding.
