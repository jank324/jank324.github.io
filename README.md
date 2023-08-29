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

### Buttons open in same or new tab

When creating a button, you can set `target="_blank"` to open the link in a new tab or `target="_self"` to open it in the same tab.

## Changes I made to the theme

- Add custom icons

- Add `"custom"` homepage layout as modified copy of `"background"` layout

## Make your own personal website based on this one

1. Fork this repository. Make sure to untick to only fork the main branch. You need at the very least the `main` and `gh-pages` branch.

2. Change the repository name to `your-username.github.io`. Make sure that in _Settings_ -> _Pages_ the repository is set to deploy from the `gh-pages` branch.

3. Fill in your own content

- Set `baseURL` in `config/_default/config.toml` to `https://your-username.github.io`.
- In `config/_default/languages.toml` change `title` and `author.name`.
- In the same file change `author.image` to point a profile picture of yourself. Place the image file in `assets/img/` and make sure it is square. If you don't want to use a profile picture, comment out the line.
- In the same file fill in your general job title and affiliation in `author.headline`. It makes sense to keep the format I've chose, with the job title first, then a line break, followed by the affiliation in a hyperlink to its homepage.
- In the same file, add your social media links under `author.links`. Simply comment in/out the ones you want and add their correct URLs. If you need one that is not listed, add a custom icon as described above and simply add it to the list by the icon name.
- For the rest of the content, edit `content/_index.md`. You can of course change the sections used to your liking. If you stick with the ones I used, write a brief text about yourself and your research interests. Add your own CV by changing the `href` property of the button to `"/resume_your_name.pdf"` and add the CV PDF file at `static/resume_your_name.pdf`. Then fill in publications in the same format I used for mine, starting with the newest at the top. The same goes for talks you would like to feature. Projects and personal projects are added using the Hugo Shortcode `article`. You need to create a folder in the `content` directory (e.g. `content/my-project`). In that folder, you need an image file `featured.*` for the thumbnail image and a `index.md` file which you best copy from one of my project files. In that `index.md` edit `title`, `externalUrl`, `summary` and `tags`. Then make sure that in the original `_index.md` the `article` Shortcode's `link` property points to the correct location in `content` (e.g. `link="/my-project/"`). Also make sure that every `article` Shortcode is followed by a `<br>` tag. If you chose to change the sections or their order, make sure to also change `config/_default/menus.en.toml` accordingly.

4. To get your own look, so your page does not look like a copy of mine.

- Change (or remove) the background image. In `config/_default/params.toml`, change `homepage.homepageImage` to point to an image file placed in `assets/img/` or comment out the line to remove the background image and use a plain background colour according to your colour scheme.
- Change the colour scheme in `config/_default/params.toml` using the `colorScheme` property. Available colour schemes are shown at https://blowfish.page/docs/getting-started/#colour-schemes.
- Choose a look for the header menu bar in `config/_default/params.toml` using the `header.layout` property. Available options are `"basic"`, `"fixed"`, `"fixed-fill"` and `"fixed-fill-blur"`.
- Choose a homepage layout by changing `homepage.layout` in `config/_default/params.toml`. Blowfish offers a bunch of them, but if you are planning to stick to the single page CV-type homepage layout, you should choose one of `"page"`, `"custom-background"` and `"custom-hero"`.

5. Hope that I didn't forget anything. 😄

6. There is of course an endless amount of further customisation options, both within Blowfish and by building your own HTML templates and so on, but for now you should have a presentable personal website. 🎉
