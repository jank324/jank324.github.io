# Personal Homepage

This is the repository for my personal homepage. This repository is based on (forked from) our [RL4AA collaboration website](https://github.com/RL4AA/RL4AA.github.io) with some changes made to the theme, file structure and of course the content. It uses [Hugo](https://gohugo.io/) to build the site and the [Blowfish theme](https://blowfish.page).

## Pointers

Below I'm collecting pointers on how to do certain things for later reference.

### Building the website

Just clone the repository, change what you need to change and push back onto `main`. The website will be built automatically by GitHub my GitHub and is served from the `gh-pages` branch.

### Adding a custom icon

Add custom icons as `.svg` files to `assets/icons/`. They can then be used as `{{< icon name="icon-name" >}}`. They may also be used for the author links by editing `config/_default/languages.toml`, where under `[author] -> links` you can add `icon-name = "link"`. To get the icon to automatically use the website's colours instead of its own and highlight correctly, find all `fill` properties in the `.svg` file and replace their values with `currentColor`.

### Linking to static files

Static files such as a resume PDF can be placed in the `static` directory. They can then be linked with `/` as the root of the static directory. For example, you have the following file: `static/resume.pdf`. You can link it as `/resume.pdf`.

### Link menu item to lower down location of same page

To make the page simply scroll down to another section on the same page instead of linking to another page, use the `url` field of the menu item. You can link to a markdown header `Section` by setting `url = "#section"`. Spaces are replaced with `-` and all characters are converted to lowercase.

## Changes I made to the theme

- Add custom icons
