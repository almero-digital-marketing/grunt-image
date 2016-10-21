# [grunt-image](https://npmjs.org/package/grunt-mega-image)

Optimize PNG, JPEG, GIF, SVG images with grunt task.

## Install

```sh
$ npm install --save-dev grunt-mega-image
```

## Usage

This is an example of `gruntfile.js`.

```js
module.exports = function (grunt) {
  grunt.initConfig({
    image: {
      static: {
        options: {
          pngquant: true,
          optipng: false,
          zopflipng: true,
          jpegRecompress: false,
          jpegoptim: true,
          mozjpeg: true,
          gifsicle: true,
          svgo: true
        },
        files: {
          'dist/img.png': 'src/img.png',
          'dist/img.jpg': 'src/img.jpg',
          'dist/img.gif': 'src/img.gif',
          'dist/img.svg': 'src/img.svg'
        }
      },
      dynamic: {
        files: [{
          expand: true,
          cwd: 'src/',
          src: ['**/*.{png,jpg,gif,svg}'],
          dest: 'dist/'
        }]
      }
    }
  });

  grunt.loadNpmTasks('grunt-image');
};
```

`options` attributes are optional. If you don't want to set as optimizer, set false. When you omitted, the optimizer will be applied.

## Result

![](https://raw.github.com/1000ch/grunt-image/master/screenshot/terminal.png)