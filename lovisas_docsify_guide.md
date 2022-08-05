# A guide to launch your own docsify-page

<!-- Author: Lovisa Sjöberg. This document contains line-references, keep that in mind when editing -->
<!-- Version: 1.0 (2022-08-05) -->

## Installation

Install `docsify-cli` through your desired terminal, this helps locally launch the site, good for previewing:
```bash
npm i docsify-cli -g 
```

Then, create a github-pages where you want your website to be. I followed [this](https://docs.github.com/en/pages/quickstart) guide and stopped at step 3 (included). I still don not know how to actually launch an existing page, only locally.

If you do not have `npm` installed, you can do it [here](https://nodejs.org/en/download/). To confirm the installation of both Node and NPM:
```bash
node -v
npm -v
```

## Initialization (taken from [here](https://docsify.js.org/#/quickstart?id=initialize))
To initialize the needed startfiles for docsify to work:
```bash
docsify init ./docs
```
Then you'll have three files:
 - `index.html`, entry file
 - `README.md`, home page
 - `.nojekyll`, prevents GitHub-pages to from ignoring files that begin with an underscore.

The `index.html`-file that I have, looks like this:
```html
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="utf-8">
   <meta http-equiv="X-UA-Compatible" content="IE=edge">
   <meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1.0, shrink-to-fit=no, viewport-fit=cover">
   <meta name="This is a description..." content="">
   <Flasheye></title>

   <!-- Theme dark -->
   <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/docsify-themeable@0/dist/css/theme-simple-dark.css">

   <!-- Uncomment these 2 lines of code to adjust the theme (dark/light) to the settings of the user's media-theme -->
   <!-- <link rel="stylesheet" media="(prefers-color-scheme: dark)" href="https://cdn.jsdelivr.net/npm/docsify-themeable@0/dist/css/theme-simple-dark.css">-->
   <!-- <link rel="stylesheet" media="(prefers-color-scheme: light)" href="https://cdn.jsdelivr.net/npm/docsify-themeable@0/dist/css/theme-simple.css">-->

   <!-- Custom Styles -->
   <style>
     :root {
      --base-font-size: 14px;
      --theme-color   : #FF2C6D;

      /* Background behind brödtext: #283339, sidebar: 242E33 */
      /* Searchbar-color: 1F282D, Text is #fafafa, search-wordtext: 556F81

      /* Cover #0A1226
============================================================================= */
    --cover-color                                      : ;
    --cover-margin                                     : 0 auto;
    --cover-max-width                                  : 40em;
    --cover-text-align                                 : center;

    /* Background */
    --cover-background-blend-mode                      : ;
    --cover-background-color                           : ;
    --cover-background-image                           : url(_media/coverpage.png);
    --cover-background-mask-color                      : var(--base-background-color);
    --cover-background-mask-opacity                    : 0.4;
    --cover-background-mask-visibility                 : ;
    --cover-background-position                        : center center;
    --cover-background-repeat                          : no-repeat;
    --cover-background-size                            : cover;

    /* Blockquote (Subtitle) */
    --cover-blockquote-color                           : ;
    --cover-blockquote-font-size                       : var(--font-size-l);

    /* Buttons */
    --cover-button-background                          : ;
    --cover-button-background--hover                   : ;
    --cover-button-border                              : 1px solid var(--theme-color);
    --cover-button-border--hover                       : 1px solid #fafafa;
    --cover-button-border-radius                       : var(--border-radius-m);
    --cover-button-box-shadow                          : ;
    --cover-button-box-shadow--hover                   : ;
    --cover-button-color                               : var(--theme-color);
    --cover-button-color--hover                        : #fafafa;
    --cover-button-padding                             : 0.5em 2rem;
    --cover-button-text-decoration                     : none;
    --cover-button-text-decoration--hover              : ;
    --cover-button-text-decoration-color               : ;
    --cover-button-text-decoration-color--hover        : ;
    --cover-button-transition                          : all var(2s) ease-in-out;

    /* Buttons - Primary */
    --cover-button-primary-background                  : var(--theme-color);
    --cover-button-primary-background--hover           : #fff;
    --cover-button-primary-border                      : 1px solid var(--theme-color);
    --cover-button-primary-border--hover               : 1px solid var(--theme-color);
    --cover-button-primary-box-shadow                  : ;
    --cover-button-primary-box-shadow--hover           : ;
    --cover-button-primary-color                       : #fff;
    --cover-button-primary-color--hover                : var(--theme-color);
    --cover-button-primary-text-decoration             : ;
    --cover-button-primary-text-decoration--hover      : ;
    --cover-button-primary-text-decoration-color       : ;
    --cover-button-primary-text-decoration-color--hover: ;

    /* Heading */
    --cover-heading-color                              : var(--theme-color);
    --cover-heading-font-size                          : var(--font-size-xxl);
    --cover-heading-font-size-min                      : ;
    --cover-heading-font-size-max                      : ;
    --cover-heading-font-weight                        : normal;

    /* Links */
    --cover-link-border-bottom                         : ;
    --cover-link-border-bottom--hover                  : ;
    --cover-link-color                                 : ;
    --cover-link-color--hover                          : ;
    --cover-link-text-decoration                       : underline;
    --cover-link-text-decoration--hover                : ;
    --cover-link-text-decoration-color                 : ;
    --cover-link-text-decoration-color--hover          : ;


    --sidebar-transition-duration                 : var(--duration-medium);
    }
   </style>
</head>
<body>
   <div id="app"></div>

   <script>
     // Docsify Configuration
     window.$docsify = {
      logo: '_media/flasheye_logo.png',
      auto2top: true,
      coverpage: true,
      executeScript: true,
      loadSidebar: true,
      loadNavbar: true,
      mergeNavbar: true,
      maxLevel: 4,
      subMaxLevel: 3,
      name: 'Flasheye',
      // repo: 'https://github.com/flasheye-lovisa/flasheye-lovisa.github.io',

      search: {
        noData: {
          //'/es/': '¡No hay resultados!', If there is no results
          //'/de-de/': 'Keine Ergebnisse!',
          //'/ru-ru/': 'Никаких результатов!',
          //'/zh-cn/': '没有结果!',
          '/': 'No results!',
        },
        paths: 'auto',
        placeholder: {
          //'/es/': 'Buscar', This is for multiple languages
          //'/de-de/': 'Suche',
          //'/ru-ru/': 'Поиск',
          //'/zh-cn/': '搜索',
          '/': 'Search',
        },
      }
    }
   </script>

   <!-- Required -->
   <script src="https://cdn.jsdelivr.net/npm/docsify@4/lib/docsify.min.js"></script>
   <script src="https://cdn.jsdelivr.net/npm/docsify-themeable@0/dist/js/docsify-themeable.min.js"></script>

   <!-- Recommended -->
   <script src="https://cdn.jsdelivr.net/npm/docsify@4/lib/plugins/search.js"></script>
   <script src="https://cdn.jsdelivr.net/npm/docsify@4/lib/plugins/zoom-image.min.js"></script>
</body>
</html>
``` 
The many lines of code with a preceeded: /* Cover, is just for customization of the colors, the buttons behavior and appearance. 

This index-file has configuration of the most basic things. It has a sidebar, has a good layout of how the content is presented and autoscrolls to the top when clicking a topic/chapter, etc. It is possible to add a GitHub-link at the top of the page's corner, see line 149 (commented).

The configuration-guide for docsify is much longer than this but I did not understand half of it so I omitted it and it has worked out great.

Then, in the current folder (docs), add a `_coverpage.md` and `_sidebar.md` file.

### `_coverpage.md`
> You can name it something else, but then you have to change the `index`-file. Instead of `coverpage = true` it should be `coverpage = 'coverpagefile.md'`

```markdown
<!-- _coverpage.md -->
<!-- A logo. Pretty self-explanatory -->
![logo](_media/flasheye_logo.png)

<!-- This is the "site-name", in large font -->
# BIG TITLE <small>version</small>

<!-- Second level text, something more describing -->
> Second level text

<!-- For a third level of text -->
- Third level text

<!-- Displays as buttons on the coverpage -->
[Website](https://www.flasheye.se/)
[GitHub](https://github.com/flasheye-lovisa/flasheye-lovisa.github.io)
[Get Started](introduction)

<!-- This is the color-theme of the coverpage, the background. Like an accent color.-->
<!-- Can be written in both HEX and rgb :) -->
![color](#0A1226)
```

Note the `Get Started`-line. In the parenthesis there are a crossreference to the introduction in the site. The local path for the homepage (where the `Get Started` button is located) is in the docs folder, which is http://localhost:3000/#/ and for the introduction it is http://localhost:3000/#/introduction, therefore the path should just be 'introduction'.

That means, that if the introduction is in another folder, relative to the docs-folder, the path would change to http://localhost:3000/#/folder/introduction. 

### `_sidebar.md`
> As said above, it could be changed to something else but then in `index`, the line `loadSidebar = true` has to be changed to `loadSidebar = 'sidebarfile.md'`

```markdown
<!-- docs/_sidebar.md -->

* [Chapter 1](path/to/file1.md "Text about file1")
* [Chapter 2](path/to/file2.md "Text about file2")
* [Chapter 3](path/to/file3.md "Text about file3")
* [Chapter 4](path/to/file4.md "Text about file4")
```
Every time you add a new chapter, it has to be added in this file or else it won't show on the docsify-site.

## Additional pages
To create a new page/chapter/section in the sidebar, create a new Markdown-file somehere within the `docs`-folder and add its path to the `_sidebar.md` file. Then, editing the markdown-file is exactly the same. If you are not familiar with markdown-syntax, [here you go](https://www.markdownguide.org/basic-syntax/). 

When adding any header in the markdown-file, it will always be included in the sidebar if not specified. To specify level-depth, edit the `subMaxLevel`, see line 147.

To see fuller and better explanation of the configuration-settings, see the official documentation [here](https://docsify.js.org/#/configuration).

Docsify will handle the Markdown files smoothly, meaning, writing a good markdown file will essentially result in a nice page on docsify.

Using images in the Markdown files is just the same, although on the docsify page the images would look better centered. To help with this, use HTML. I centered almost all of the pictures with this:

```html
<p align="center">
  <img src="source/path/to/image.png" />
</p>
```

## Deploying the page
This repo is deployed via [netlify.com](https://www.netlify.com/). A good how to deploy via netlify, or some other platform is [here](https://docsify.js.org/#/deploy).

The big guide on how to use docsify is on their official [site](https://docsify.js.org/#/), and is __encouraged__ to use. This acts mostly like a compliment to the guide where I, myself, got stuck. 

Hope this guide finds you helpful!






