# Zola TailwindCSS Template

Setting up Zola to work with TailwindCSS can be a pain and requires a lot of
boilerplate. This is a template repository for people looking to work with
[TailwindCSS](https://tailwindcss.com/) and [Zola](https://www.getzola.org/) at
the same time. Containing all the boilerplate file structure, HTML `meta`
tags, basic Markdown styling and a GitHub Action to deploy to GitHub Pages.

## Dependencies

In order to work with this project, both Zola and the standalone TailwindCSS CLI
need to be accessible from your shell.

* To install Zola look [here](https://www.getzola.org/documentation/getting-started/installation/).
* To install the TailwindCSS standalone CLI look [here](https://github.com/tailwindlabs/tailwindcss/releases/latest).

## Usage

Please have a look at the [Zola
Documentation](https://www.getzola.org/documentation/getting-started/overview/)
for an overview of usage and at the [TailwindCSS
Documentation](https://tailwindcss.com/docs) for Tailwind usage.

To build the website, run:

```bash
tailwindcss -i src-styles/base.scss -o static/styles/main.css --minify
zola build
```

To start a local testing server and watch for changes, run:

```bash
tailwindcss -i src-styles/base.scss -o static/styles/main.css --watch &
zola serve
```

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

In order to add automatic deployment to Github Pages, add a Personal Access
Token with `repo` (or `public_repo` for public repositories) access to the a
repository secret called `TOKEN`. Make sure the `base_url` in the *config.yml*
matches the URL you are publishing to.

## License

License under a MIT or Apache license.
