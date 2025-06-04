# Routing Demo

Shows how to make the routing.json file editable in CloudCannon.

Places of interest:
  - cloudcannon.config.yaml (`collections_config` > `routing` & `collection_groups`)
  - .cloudcannon/routing.json

- The routing.json file that controls routing on a CloudCannon site must live at `.cloudcannon/routing.json` (although if you need it in a different spot, you can move it to where it needs to be in a `preinstall` or `prebuild`
- Must be a CloudCannon hosted site for the `.cloudcannon/routing.json` to affect routing, although you could similarly make a different hosting provider's routing data file editable in CloudCannon. Simply define it as a collection, and add it to your collection groups (if defined at all) to see it appear in your sidebar, and therefore be accessible to editors.
- Control input config for these files just like anywhere else in CloudCannon to define the editing experience needed for each use case.

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
