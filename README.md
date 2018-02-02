# Kern Lodge Blog
[![Build Status](https://travis-ci.org/shgysk8zer0/kernlodge.svg?branch=master)](https://travis-ci.org/shgysk8zer0/kernlodge)
[![GitHub issues](https://img.shields.io/github/issues/shgysk8zer0/kernlodge.svg)](https://github.com/shgysk8zer0/kernlodge/issues)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/shgysk8zer0/kernlodge.svg)](https://github.com/shgysk8zer0/kernlodge/pulls)
- - -
A blogging site for The Kern Lodge

![screenshot](https://i.imgur.com/vl1QVLel.png)

## Index
- [Markdown basics](https://guides.github.com/features/mastering-markdown/)
- [Liquid / Jekyll syntax](https://github.com/shopify/liquid/wiki/Liquid-for-Designers)
- [Directory structure](#directory-structure)
- [Creating content](#creating-content)
- [Working with images](#working-with-images)
- [Adding videos](#adding-videos)
- [Author profile](#cauthor-profile)
- [Publishing](#publishing)
- [Recommended software and services](#recommended-software-and-services)
- [Developer guidelines](docs/CONTRIBUTING.md)

## Directory structure
**This is a partial list of folders and a brief description of their contents**
- `css/`
  - `styles/` Theme layout, styles, etc.
- `_data/` Data files used by Jekyll
- `_drafts/` Can be created to store unpublished posts
- `docs/` This is used on GitHub for pull-request templates, etc.
- `_fonts/` A submodule containing a collection of fonts
- `img/` Contains all icons and images.
- `_includes/` Folder for Jekyll templates/components
- `js/` Scripts directory.
- `_layouts/` Jekyll directory for page layouts ("default", "page", "post", etc.)
- `_posts/` Directory for published posts. See [Creating content](#creating-content)

**Version control and site generation resources (DO NOT TOUCH)**
- `.git/` This is a folder used by Git to store repository info, such as version history
- `node_modules/` This is a massive directory for NPM packages, used for development
- `_site/` This is where the generated site content is stored. Changes **WILL NOT** be saved

For authors, the only folders of any interest or use to you will be `_posts/` and
`_drafts/`. Everything else will be of little to no use to you unless you're trying
to learn to be a developer.

## Creating content
Most posts will probably be written using Markdown, it would be a good idea to
familiarize yourself with the [basic syntax](https://guides.github.com/features/mastering-markdown/).

All posts **MUST** be creating in the `_posts/` directory. The name of the file
**MUST** be in the format `YYYY-MM-DD-name-of-post.(md|html)`.

You can change the layout and meta data in the post's "front matter".
```
---
title: My Awesome Post
author: Chuck Norris
data: '2018-02-01 23:57'
description: 'This is a description, and it should be surrounded in single quotes'
imgur: 'https://imgur.com/GxWyD8e'
keywords:
- Blog
- Post
- Kittens
- Bacon
---
```

As a general rule, anything in front matter that contains special characters
**MUST** be surrounded by double or single quotes.

## Working with images
You can either use typical Markdown syntax, or use use an Imgur Responsive Image
```
{% include imgur.html
  ulr='https://imgur.com/GxWyD8e'
%}
```

Using Imgur will automatically select the correct image for the device's screen
(assuming the image should fill up 100% of the width of the screen) and you can
optionally specify different dimensions by adding a [`sizes` attribute.](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-sizes)

## Adding videos
You may either copy the embed code provided by YouTube *(Share -> Embed) or use
the provided YouTube component:
`{% include youtube.html url='https://www.youtube.com/watch?v=sy5NY-Dqdys' %}`

You will have better results with the YouTube component, as it provides code
similar to the embed code, but with changes to improve appearance on the site,
as well as the privacy of users.

## Author profile
By default, posts will display the name of the author, as listed in `author:` in
the post's front matter. You can, however, create a file in `_data/authors/`
containing extended info, such as Gravatar profile image and social links.

When creating an author file, remember that it **MUST** be all lowercase with
any spaces replaced with "-". This file **MUST** be in either YAML or JSON format
(extension of `.yml` and `.json`, respectively).

## Publishing
### Publishing to Netlify
If you publish using Netlify and everything is setup correctly,
publishing should only require committing and pushing to GitHub. Netlify will
re-generate the site's contents, icons, scripts, and stylesheets.

### Publishing to GitHub Pages
GitHub Pages will generate your site, but it will not generate the necessary scripts,
stylesheets, and package the icons. Should you chose this option, you **MUST**
remove these resouces from `.gitignore` and re-generate and commit them.

### Publishing elsewhere
Since Jekyll sites are only static assets, you can publish anywhere you have filesystem
access. This might require FTP, rsync, it it will require for you to be able to
build the site locally before uploading the **entire** contents of `_site/`.

## Recommended software and services
You will, at the very least, be required to open and edit Markdown files and push
changes to GitHub. Syntax highlighting will be very helpful, so you might want to
look into something like Atom or Sublime Text.

You will also need a [Git client](https://git-scm.com/downloads/guis) to commit and
push changes. GitHub Desktop is the simplest option here, though GitKraken is also
fairly popular.

**Software**
- [Atom text editor](https://atom.io)
- [GitHub Desktop](https://desktop.github.com/)

**Services**
- [Netlify](https://www.netlify.com/)
- [GitHub](https://github.com)
- [Gravatar](https://en.gravatar.com/)
- [Imgur](https://imgur.com/)
- [Google Analytics](https://analytics.google.com/analytics/web/)
- [Disqus](https://disqus.com/)

**Required for developers**
- [Jekyll](https://jekyllrb.com/)
- [NPM](https://nodejs.org/)

After cloning and `cd`ing into the project directory, run
`npm install && bundle install`.
