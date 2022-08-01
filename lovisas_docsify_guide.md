# A lousy guide to how I failed - and solved, docsify

## Installation

Installing `docsify-cli` helps locally launch the site, good for previewing:
```bash
npm i docsify-cli -g 
```

Then, create a github-pages where you want your website to be. I followed [this](https://docs.github.com/en/pages/quickstart) guide and stopped at step 3 (included). I still don't know how to actually launch an existing page, only locally.

If you do not have `npm` installed, you can do it [here](https://nodejs.org/en/download/). To confirm the installation of both Node and NPM:
```bash
node -v
npm -v
```

## Initialization (taken from [here](https://docsify.js.org/#/quickstart?id=initialize))
To initialize the needed startfiles:
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

   <!-- Themes (light + dark) -->
   <link rel="stylesheet" media="(prefers-color-scheme: dark)" href="https://cdn.jsdelivr.net/npm/docsify-themeable@0/dist/css/theme-simple-dark.css">
   <link rel="stylesheet" media="(prefers-color-scheme: light)" href="https://cdn.jsdelivr.net/npm/docsify-themeable@0/dist/css/theme-simple.css">

   <!-- Custom Styles -->
   <style>
     :root {
      --base-font-size: 14px;
      --theme-color   : #FF2C6D;
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
      subMaxLevel: 2,
      name: 'Flasheye',
      // repo: ... loads a little triangle on the top of the page to the github linked
      repo: 'https://github.com/flasheye-lovisa/flasheye-lovisa.github.io',
    
      //Loads a search-bar, only available in english atm  
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
And this one can handle the most basic things. It has a sidebar, with links to the Github, autoscrolls to the top when clicking a topic/chapter, etc.

The configuration-guide for docsify is much longer than this but I did not understand a half of it so I omitted it and it has worked out great.

Then, in the docs-folder, add a `_coverpage.md` and `_sidebar.md` file.

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

<!-- This is the color-theme of the coverpage, the background -->
![color](#0A1226)
```

Note the `Get Started`-line. In the parenthesis there are a crossreference to the introduction in the site. The local path for the homepage (where the `Get Started` button is located), is http://localhost:3000/#/ and for the introduction it is http://localhost:3000/#/introduction, therefore the path should just be 'introduction'.

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






