# Patterns Angular

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 11.1.1. It is a companion to the [generic installation guide for **NYCO Patterns Library**](https://nycopatterns.cityofnewyork.us/installation).

# Angular + NYCO Patterns integration

**$1** When [initializing a new Angular Project](https://angular.io/guide/setup-local), select Sass (not the indented syntax).

```shell
? Which stylesheet format would you like to use? SCSS [ https://sass-lang.com/documentation/syntax#scss ]
```

**$2** Install the [**NYCO Patterns library**](https://nycopatterns.cityofnewyork.us) after [initializing an Angular Project](https://create-react-app.dev/docs/getting-started).

```shell
$ npm install @nycopportunity/patterns
```

**3** Add the style preprocessor options with include paths to the **angular.json** configuration file. There are two blocks to nest it under; one in `projects.{{ your project name }}.architect.build.options` and the other in `projects.{{ your project name }}.architect.test.options`. It can be added after the `styles` block for convenience.

```json
  //...
  "styles": [
    "src/styles.scss"
  ],
  "stylePreprocessorOptions": {
    "includePaths": [
      "node_modules/@nycopportunity",
      "node_modules/@nycopportunity/patterns/src",
      "node_modules/animate.scss"
    ]
  },
  //...
```

**$4** Import patterns into the main stylesheet. The following line will import everything. [*View this repository's styles.scss file to browse the import configuration options*](src/styles.scss).

```scss
@import '~@nycopportunity/patterns/src/scss/imports';
```

**$5** Copy distributed assets from the library into the src directory of the project:

```shell
./node_modules/@nycopportunity/patterns/dist/fonts > ./src/fonts
./node_modules/@nycopportunity/patterns/dist/svg > ./src/svg
```

**$6** Run `ng serve --open` to begin development.

---

**Notes**:

* The configuration above is largely dependent on what patterns in the library you will be using in your project. The above steps are based on the usage of *all* NYCO Patterns stylesheets.

* Below is a breakdown of the include paths. Not all of them are required if only a few of the patterns are being used.

```
src
node_modules/@nycopportunity
node_modules/@nycopportunity/patterns/src
node_modules/animate.scss
```

* The font and svg assets only need to migrated into the project if using the NYCO Pattern's [fonts](https://github.com/IBM/plex) and/or [icons](https://nycopatterns.cityofnewyork.us/icons). You may also include fonts via [Google Fonts Embed](https://fonts.google.com/specimen/IBM+Plex+Sans) or SVGs and fonts the [CDN method of integration](https://nycopatterns.cityofnewyork.us/installation#heading-cdn).

* Icons require the provided [Patterns Icon Script](https://github.com/CityOfNewYork/patterns-scripts/tree/main/src/icons) ([or a similar method](https://css-tricks.com/ajaxing-svg-sprite/)) to inline the SVG sprite in the DOM. See the [Icon Usage documentation](https://nycopatterns.cityofnewyork.us/icons#heading-icon-usage) for more details. The CDN path to the distributed icons can be passed to the method as opposed to hosting them with the project (if desired).

* The NYCO Patterns rely on the Feather icon set which can be integrated with the entire svg sprite installed with the library under the directory **./node_modules/@nycopportunity/patterns/dist/svg/feather.svg** using the [Patterns Icon Script](https://github.com/CityOfNewYork/patterns-scripts/tree/main/src/icons) mentioned above or separately with the [Angular Feather](https://github.com/michaelbazos/angular-feather) package. See the [Feather Icon documentation](https://nycopatterns.cityofnewyork.us/icons#heading-icons-ui) for more details.

**Happy Coding!**

---

![The Mayor's Office for Economic Opportunity](NYCMOEO_SecondaryBlue256px.png)

[The Mayor's Office for Economic Opportunity](http://nyc.gov/opportunity) (NYC Opportunity) is committed to sharing open source software that we use in our products. Feel free to ask questions and share feedback. **Interested in contributing?** See our open positions on [buildwithnyc.github.io](http://buildwithnyc.github.io/). Follow our team on [Github](https://github.com/orgs/CityOfNewYork/teams/nycopportunity) (if you are part of the [@cityofnewyork](https://github.com/CityOfNewYork/) organization) or [browse our work on Github](https://github.com/search?q=nycopportunity).