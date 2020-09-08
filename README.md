# gulp-versioning-assets
Its the same as original repo. but the only diff. is versioning all files even if its cloud import and without checking file paths.
so if you change the base URL in the original project, still can versioning files.

A plugin for gulp.js to add version after file's name by random hash.
### `test.html` -> `test.html?v=7f499bc7`
### `test.css` -> `test.css?v=f83a98d9`

## Installation

```bash
npm install gulp-versioning-assets
```

## Usage

```js
var gulp = require('gulp');
var assetVersion = require('gulp-versioning-assets');

gulp.task('css',function() {
    gulp.src("./test/styles/test.css")
        .pipe(assetVersion())
        .pipe(gulp.dest('./dest/styles'));
});

gulp.task('html',function() {
    gulp.src("./test/test.html")
        .pipe(assetVersion())
        .pipe(gulp.dest('./dest'));
});
```

## Options

### assetPath: direct asset path to when using template engines.
Type: `String` Default: ""

### rootPath: it should be assigned when the asset's path is an absolute path.
Type: `String` Default: ""

## Example

### before: test.css
```css
body{background:url('../images/bg.png')}
```

### after: test.css
```css
body{background:url("../images/bg.png?v=1434f26c"}
```
### before: test.html
```html
<html>
<head>
    <meta charset="utf-8"/>
    <title></title>
    <link rel="stylesheet" href="./styles/test.css" type="text/css" />
</head>
<body>
    <div>
        <img src="./images/test.png" />
    </div>
    <script src="./scripts/test.js" type="text/javascript"></script>
</body>
</html>
```
### after: test.html

```html
<html>
<head>
    <meta charset="utf-8"/>
    <title></title>
    <link rel="stylesheet" href="./styles/test.css?v=55440a04" type="text/css" />
</head>
<body>
    <div>
        <img src="./images/test.png?v=72ceqefw" />
    </div>
    <script src="./scripts/test.js?v=4f97eec9" type="text/javascript"></script>
</body>
</html>
```
