frontsize
=========

Current version [3.9.50-beta][release]

The project was [originally developed in LESS][less], but soon only the SASS version will be matained.

Non beta version will be available after we've fully added tests and documentation.

[![TravisCI](https://travis-ci.org/ideatosrl/frontsize-sass.svg?branch=master)](https://travis-ci.org/ideatosrl/frontsize-sass/builds)
[![Built with SASS](http://img.shields.io/:language-SASS-ff6799.svg)](http://badges.github.io/badgerbadgerbadger/)
[![MIT licence](http://img.shields.io/:license-MIT-00AFFF.svg)](https://github.com/ideatosrl/frontsize-sass/blob/master/LICENSE.md)
[![Join the chat at https://gitter.im/ideatosrl/frontsize-sass](http://img.shields.io/:gitter-join chat-00AFFF.svg)](https://gitter.im/ideatosrl/frontsize-sass?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

It's a CSS generator written to make websites easy to read on every device and faster to be coded. It gives to the developer a solid base which can be used to build responsive layouts for websites or web apps.

###Why Frontsize?

- It supports various types of [grid rules][grids]
- It's [BEM][bem] ready, also with [expressive BEM][bem_expressive]
- It has all the automation support you need, with it's [config][automation_config], [grunt][automation_grunt] and [gulp][automation_gulp]
- It passes [CSSlint][csslint] tests (see the tests [configuration][csslintc])
- It can be useful for [migrations][migration] by it's high customizable features
- It's totally [customizable][app]

If you'd like to see more features, visit [frontsize.com][site] website.

---

###Bower install

This will download Frontsize on `bower_components` folder, you should do that from the project's root folder.

```
bower install frontsize-sass
```

---

###The next steps will be automated soon

Once you have downloaded it, copy your theme to the project front-end develop folder:

```
cp bower_components/frontsize-sass/themes/default frontsize-sass/themes/theme-name
```

Then change core references to let it point on bower folder:

So in `frontsize-sass/themes/theme-name/compile-test.scss` file:

```
@import "themes/default/config";
@import "core/core";
@import "themes/default/import";
```

Change the code to:

```
@import "themes/theme-name/config";
@import "bower_components/frontsize-sass/core/core";
@import "themes/theme-name/import";
```

The do the same in `frontsize-sass/themes/theme-name/compile.scss` file:

```
@import "core/vendor/normalize.css.scss";
@import "compile-test";
```

Change the code to:

```
@import "bower_components/frontsize-sass/core/vendor/normalize.css.scss";
@import "compile-test";
```

Now the core is easily to be upgraded with `bower update` when a new release is available.

---

File package.json
---

To add all node dependencies for grunt and gulp run this from your project `package.json` location:

```
npm install --save-dev colors csslint execSync fs-extra grunt grunt-contrib-clean grunt-contrib-copy grunt-contrib-csslint grunt-contrib-cssmin grunt-contrib-sass grunt-contrib-watch grunt-stylestats grunt-uncss gulp gulp-bower gulp-clean gulp-concat gulp-copy gulp-csslint gulp-load-plugins gulp-prompt gulp-run gulp-sass gulp-shell gulp-sourcemaps gulp-stylestats gulp-symlink gulp-uglify gulp-uglifycss js-yaml matchdep mkpath run-sequence sass sassdoc sassdoc-theme-vulcan stylestats
```

---

Documentation
---

The docs are generated by [SASSdoc][sassdoc].
We've started writing documentation and we'll release it as soon as possible.

```
sassdoc ./core ./themes
```

---

Release details
---

**Features**
- **added** a missing dependency on theme imports
- **changed** YAML config to make gulp and grunt automation more consistent and flexible
- **changed** gulp automation, now it's more consistent and flexible
- **changed** grunt automation, now it's more consistent and flexible
- **removed** `normalize.css` from core, now will be added from bower vendors like other dependencies
- **removed** default padding on `asTable` mixin, with `false`, the prop will be skipped

Next release details
---

**Features**
- **added** gulp automation support on theme creation to simplify the project management

---

To test HTML examples:

```
npm install && ./node_modules/.bin/bower install && php -S localhost:8000 -t ./
open http://localhost:8000/test/html/index.html
```

created by [Vittorio Vittori][vitto] and [Alessandro Minoccheri][minompi], sponsored by [ideato srl][ideato]

[app]:               https://github.com/ideatosrl/frontsize-sass/blob/master/themes/default/app.scss
[csslint]:           https://github.com/CSSLint/csslint
[csslintc]:          https://github.com/ideatosrl/frontsize-sass/blob/master/.csslintrc
[bem]:               https://github.com/ideatosrl/frontsize-sass/blob/master/core/components/bem.scss
[bem_expressive]:    https://github.com/ideatosrl/frontsize-sass/blob/master/core/components/bem-expressive.scss
[docs]:              https://github.com/ideatosrl/frontsize-less/wiki
[automation_config]: https://github.com/ideatosrl/frontsize-sass/blob/master/frontsize.yml.dist
[automation_gulp]:   https://github.com/ideatosrl/frontsize-sass/blob/master/gulpfile.js
[automation_grunt]:  https://github.com/ideatosrl/frontsize-sass/blob/master/Gruntfile.js
[grids]:             https://github.com/ideatosrl/frontsize-sass/tree/master/core/grids
[ideato]:            http://www.ideato.it
[migration]:         https://gist.github.com/vitto/9b7dfc40ef710470fed1
[minompi]:           https://twitter.com/minompi
[sass]:              https://github.com/ideatosrl/frontsize-sass
[less]:              https://github.com/ideatosrl/frontsize-less
[site]:              http://frontsize.com
[vitto]:             https://twitter.com/vttrx
[sassdoc]:           http://sassdoc.com/
[release]:           https://github.com/ideatosrl/frontsize-sass/releases/tag/3.9.50
