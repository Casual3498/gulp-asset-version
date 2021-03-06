# gulp-asset-version

A plugin for gulp.js to add version after file's name by content hash.
### `test.html` -> `test.html?v=7f499bc7`
### `test.css` -> `test.css?v=f83a98d9`

## Installation

```bash
npm install gulp-asset-version
```

## Usage

```js
var gulp = require('gulp');
var assetVersion = require('gulp-asset-version');

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
