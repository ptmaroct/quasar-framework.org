title: Quasar App Structure
---
## Overview
This is what a new Quasar Framework App folder structure looks like. Some folders are creating after building the App.
``` bash
.
├── build
│   ├── assets
│   │   └── favicon.ico
│   ├── css
│   │   ├── app.css
│   │   └── app-dependencies.css
│   ├── html
│   │   └── app.html
│   ├── js
│   │   ├── app-dependencies.js
│   │   └── app.js
│   ├── pages
│   │   └── index
│   │       ├── assets
│   │       ├── css
│   │       │   └── style.index.css
│   │       ├── html
│   │       │   └── view.index.html
│   │       └── js
│   │           └── script.index.js
│   ├── app.json
│   └── index.html
├── coverage
│   ├── lcov-report
│   │   ├── base.css
│   │   ├── index.html
│   │   ├── prettify.css
│   │   ├── prettify.js
│   │   ├── sort-arrow-sprite.png
│   │   └── sorter.js
│   └── lcov.info
├── dist
│   ├── assets
│   │   └── favicon.ico
│   ├── css
│   │   ├── app.css
│   │   └── app-dependencies.css
│   ├── html
│   │   └── app.html
│   ├── js
│   │   ├── app-dependencies.js
│   │   └── app.js
│   ├── pages
│   │   └── index
│   │       ├── assets
│   │       ├── css
│   │       │   └── style.index.css
│   │       ├── html
│   │       │   └── view.index.html
│   │       └── js
│   │           └── script.index.js
│   ├── app.json
│   └── index.html
├── src
│   ├── assets
│   │   └── favicon.ico
│   ├── css
│   │   └── app.styl
│   ├── html
│   │   └── app.html
│   ├── js
│   │   └── app.js
│   ├── pages
│   │   └── index
│   │       ├── assets
│   │       ├── css
│   │       │   └── style.index.styl
│   │       ├── html
│   │       │   └── view.index.html
│   │       ├── js
│   │       │   └── script.index.js
│   │       └── config.index.yml
│   └── index.html
├── test
│   ├── .eslintrc
│   ├── setup.js
│   └── test.spec.js
├── CHANGELOG.md
├── .eslintrc
├── .gitignore
├── package.json
├── quasar.build.yml
├── README.md
└── .stylintrc

36 directories, 48 files
```

What each is used for:

| Asset | Description |
| --- | --- |
| /build | Development build folder |
| /dist | Production build folder |
| {/build,/dist}/app.json | Pages Manifests put together. Details [here](/guide/quasar-app-configuration.html#app-json) |
| /coverage | Code coverage after [running tests with CLI](/guide/cli-commands.html#Running_Test_Suites) |
| /src | App source files; see [Source Folder](#Source_Folder) |
| /test | Test source files used for [running tests with CLI](/guide/cli-commands.html#Running_Test_Suites) |
| /CHANGELOG.md | Change log [generated by Quasar CLI](/guide/cli-commands.html#Making_a_Release) |
| /.eslintrc | Default ESLINT config for linting Javascript files |
| /.gitignore | Tells GIT what files to ignore |
| /package.json | App's NPM management file |
| /quasar.build.yml | YAML file used to [configure App build](/guide/quasar-app-configuration.html#quasar-build-yml) |
| /.stylintrc | Default Stylus lint config for linting Stylus files |

## Source Folder

| Asset | Description |
| --- | --- |
| /src/css | Folder to store global/common CSS files |
| /src/html | Folder to store global/common HTML files |
| /src/js | Folder to store global/common JS files |
| /src/pages | Folder to store assets for each page |
| /src/index.html | App starting point |

## Pages
An App's central working point is the Pages it is composed of. Each page has the following structure:

| Asset | Description |
| --- | --- |
| /src/pages/**&lt;page-name&gt;** | Page folder |
| /src/pages/**&lt;page-name&gt;**/assets | Folder to place images, fonts, ... specific to the page only |
| /src/pages/**&lt;page-name&gt;**/css | Folder to place CSS files specific to the page only |
| /src/pages/**&lt;page-name&gt;**/html | Folder to place HTML files specific to the page only |
| /src/pages/**&lt;page-name&gt;**/js | Folder to place JS files specific to the page only |
| /src/pages/**&lt;page-name&gt;**/config.**&lt;page-name&gt;**.yml | Folder to place CSS files specific to the page only |

Each page has a starting point for each type of asset:

| Asset | Description |
| --- | --- |
| style.**&lt;page-name&gt;**.styl | If it exists, it will automatically be included when page is loaded.<br>When user navigates away, it is removed. |
| view.**&lt;page-name&gt;**.html | If it exists, it will automatically be included when page is loaded. |
| script.**&lt;page-name&gt;**.js | **[Required]** Starting point of the page logic |
| config.**&lt;page-name&gt;**.yml | **[Required]** YAML file with page configuration (called *Manifest*). |

> Read about page manifests (`config.*page-name*.yml`) in [Writing a Page](/guide/writing-quasar-page.html#Page_Manifest) section.