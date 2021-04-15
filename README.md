# Zola TailwindCSS Template

Setting up Zola to work with TailwindCSS can be a pain and requires a lot of
boilerplate. This is a template repository for people looking to work with
[TailwindCSS](https://tailwindcss.com/) and [Zola](https://www.getzola.org/) at
the same time. Containing all the boilerplate file structure, HTML `meta`
tags, basic Markdown styling and a GitHub Action to deploy to GitHub Pages.

## Dependencies

In order to work with this project, both Zola and NPM/Yarn need to be accessible
from your shell.

* To install Zola look [here](https://www.getzola.org/documentation/getting-started/installation/).
* To install NPM look [here](https://nodejs.org/en/download/).
* To install Yarn look [here](https://yarnpkg.com/getting-started/install).

## Usage

Please have a look at the [Zola
Documentation](https://www.getzola.org/documentation/getting-started/overview/)
for an overview of usage and at the [TailwindCSS
Documentation](https://tailwindcss.com/docs) for Tailwind usage.

This template provides a few scripts to run from NPM/Yarn. This is done with

**NPM:**

```bash
npm run <script-name>
```

**Yarn:**

```bash
yarn run <script-name>
```

Here `<script-name>` can be one of the following scripts:

* `serve` - Start a dummy webserver. Watch for both changes in stylesheets and
  zola files. When changes happen: recompile the styling and the static files.
* `build` - Create all the optimized files in the `public` folder.
* `tailwind-watch` - Watch for changes in stylesheets. When changes happen:
  recompile the styling files.
* `tailwind-build` - Create all the optimized stylesheet files.

All the preset styling for Markdown is done in the `src-styles/markdown.scss`
file and can be reached by adding the `markdown` class to the container. This
means replacing the following example with the one after.

```html
<div class="container mx-auto">
    {{ page.content | safe }}
</div>
```

Should be replaced with:

```html
<div class="container mx-auto markdown">
    {{ page.content | safe }}
</div>
```

In order to add automatic deployment to Github Pages, add a `TOKEN` with `repo`
(or `public_repo` for public repositories) access to the secrets.

## License

License under a MIT or Apache license.
