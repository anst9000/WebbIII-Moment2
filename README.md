# WebbIII-Moment2

## Presentation
![Gulp.js logo](https://github.com/anst9000/WebbIII-Moment2/blob/master/gulp.png "Gulp logo")
### Why automate your workflow?
> There are many repetitive task in web development, for example minifying code, optimizing images, saving files to directory for publishing and preprocessing CSS. Gulp or Grunt can be used to assist and speed up these tasks.
### Node modules used
> I have used Gulp version 4.0.2 and installed a few node modules that can assist for building a smooth gulpfile.js. The base module is gulp. It is required to be able to run a gulpfile. Next module is browser-sync which is helpful because it reloads the web browser every time a change is made in any .scss-, .js- or .html-file. The module gulp-clean-css is used to minify css files. Module gulp-concat is used to concatenate for example .js-files or .css-files. To be able to decrease the size of images the module gulp-imagemin was used. Because the setup was made for writing .scss-files it was necessary to use the module gulp-sass. And finally the module gulp-terser was used to minify the .js-files. The module gulp-uglify was used before but for some reason it has difficulties to minify ES6 .js-files, so I decided to test gulp-terser instead.
### Commands to run
> The function all is run with the command
```javascript
gulp all
```
> and that includes many functions running at once. In most cases you start your workflow by this command. If you only are interrested in browser-sync and updating the changes in .js, .css and .html files you can run 
```javascript
gulp watchFiles
```
> It is also possible to run the functions one by one like 
```javascript
gulp message
```
> or
```javascript
gulp style
```
> A full explanation of all the commands is followed in the table below.

## Functions
| Function  | Function description                                                                                                                                                 |
| --------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| imgMinify | Minifies images of different format and copies them to /pub .                                                                                                        |
| htmlTask  | Moves html files from /src to /pub and also updates browser when a file is changed.                                                                                  |
| jsTask    | Moves js files from /src to /pub and then concatenates them into one single js file. It also uglifies the resulting js file. Updates browser if any file is changed. |
| scssTask  | Moves scss files from /src to /pub, cleans them up and also updates the browser if any file is changed.                                                              |
| watchTask | Starts the browserSync plugin and watches many different directories to check for changes.                                                                           |

### Example code from gulpfile.js
```javascript
// Sets Gulp to automatically update when any changes are made
// Task: Watcher
function watchTask() {
    browserSync.init({
        server: {
            baseDir: 'pub/'
        }
    })

    watch(
        [files.htmlPath, files.jsPath, files.scssPath],
        parallel(htmlTask, jsTask, scssTask)
    ).on('change', browserSync.reload)
    watch(files.imgPath, imgTask).on('change', browserSync.reload)
}

exports.default = series(
    parallel(htmlTask, jsTask, scssTask, imgTask),
    watchTask
)
```

## Homepage
[WebbIII-Moment2](https://github.com/anst9000/WebbIII-Moment2)
```javascript
git clone https://github.com/anst9000/WebbIII-Moment2.git
```


## Developer Dependencies
| Module          | Version | Module description                                       |
| --------------- | :-----: | -------------------------------------------------------- |
| browser-sync    | ^2.26.7 | Reloads web browser after changes in html, css or js     |
| gulp            | ^4.0.2  | Base module necessary to be able to run gulpfile.js      |
| gulp-concat     | ^2.6.1  | Module that concatenates files, both .js- and .css-files |
| gulp-imagemin   | ^6.1.0  | Module that shrinks images to make them smaller          |
| gulp-sass       | ^4.0.2  | Module converting sass/scss-files into css-files         |
| gulp-sourcemaps | ^2.6.5  | Module that creates source map for scss-files            |
| gulp-terser     | ^1.2.0  | Module that removes white spaces in .js-files            |
| gulp-clean-css  | ^4.2.0  | Module that removes white spaces in .css-files           |

## Help from these sites
<ul>
  <li>https://www.youtube.com/watch?v=QgMQeLymAdU</li>
  <li>https://www.youtube.com/watch?v=1rw9MfIleEg</li>
  <li>https://www.youtube.com/watch?v=rmXVmfx3rNo</li>
  <li>https://gulpjs.com/</li>
  <li>https://github.com/gulpjs/gulp/blob/v3.9.1/docs/API.md</li>
  <li>https://developers.google.com/web/ilt/pwa/introduction-to-gulp</li>
</ul>
