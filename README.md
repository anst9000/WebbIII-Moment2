# WebbIII-Moment2

## Redovisning
...
### Why automate your workflow?
> There are many repetitive task in web development, for example minifying code, optimizing images, saving files to directory for publishing and preprocessing CSS. Gulp or Grunt can be used to assist and speed up these tasks.
### Node modules used
> I have used Gulp version 4.0.2 and installed a few node modules that can assist for building a smooth gulpfile.js. The base module is gulp. It is required to be able to run a gulpfile. Next module is browser-sync which is helpful because it reloads the web browser every time a change is made in any .scss-, .js- or .html-file. The module gulp-clean-css is used to minify css files. Module gulp-concat is used to concatenate for example .js-files or .css-files. To be able to decrease the size of images the module gulp-imagemin was used. Because the setup was made for writing .scss-files it was necessary to use the module gulp-sass. And finally the module gulp-terser was used to minify the .js-files. The module gulp-uglify was used before but for some reason it has difficulties to minify ES6 .js-files, so I decided to test gulp-terser instead.
### Commands to run
> The function all is run with the command <gulp all> and that includes many functions running at once. In most cases you start your workflow by this command. If you only are interrested in browser-sync and updating the changes in .js, .css and .html files you can run <gulp watchFiles>. It is also possible to run the functions one by one like <gulp message> or <gulp style>. A full explanation of all the commands is followed in the table below.

## Homepage
[WebbIII-Moment2](https://github.com/anst9000/WebbIII-Moment2)


## Developer Dependencies
| Dependency     | Version | Motivering                                                |
| -------------- | :-----: | --------------------------------------------------------- |
| browser-sync   | 2.26.7  | Uppdaterar webbläsaren vid ändringar i html, css eller js |
| gulp           |  4.0.2  | Grundmodulen för att kunna använda en gulpfile.js         |
| gulp-concat    |  2.6.1  | Modul som pusslar ihop filer, i det här fallet js-filer   |
| gulp-imagemin  |  6.1.0  | Modul som krymper images så att de tar mindre plats       |
| gulp-sass      |  4.0.2  | Modul som konverterar sass/scss-filer till css-filer      |
| gulp-terser    |  1.2.0  | Modul som rensar bort alla ws (= white spaces) från filer |
| gulp-clean-css |  4.2.0  | Modul som fungerar som gulp-terser, men med css-filer     |


## Help from these sites
<ul>
  <li>https://www.youtube.com/watch?v=QgMQeLymAdU</li>
  <li>https://www.youtube.com/watch?v=1rw9MfIleEg</li>
  <li>https://www.youtube.com/watch?v=rmXVmfx3rNo</li>
  <li>https://gulpjs.com/</li>
  <li>https://github.com/gulpjs/gulp/blob/v3.9.1/docs/API.md</li>
  <li>https://developers.google.com/web/ilt/pwa/introduction-to-gulp</li>
</ul>
