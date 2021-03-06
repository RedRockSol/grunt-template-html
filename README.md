# grunt-template-html

> Precomplie templates to HTML.

## Getting Started
This plugin requires Grunt `~0.4.1`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-template-html --save-dev
```

One the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-template-html');
```

## The "template" task

### Overview
In your project's Gruntfile, add a section named `template` to the data object passed into `grunt.initConfig()`.


### Options

#### engine

Template engine is supported by [Consolidate](https://github.com/visionmedia/consolidate.js)
```js
engine: 'handlebars'
```
#### cwd

Path to template folder
```js
cwd: 'test/fixtures/'
```
#### partials

Path to partials folders
```js
partials: ['test/fixtures/modules/*.hbs']
```
#### data

- Path to data file
```js
data: 'test/fixtures/data/data.json'
```

- Function, which MUST return an Object, which will serve as template data
```
data: function() {
	return {
	  some: "object"
	};
}
```

- Object, which will be the data object itself
```
data: { some: "object"}
```

### Usage Examples

```js
grunt.initConfig({
  template: {
    dev: {
      engine: 'handlebars',
      cwd: 'test/fixtures/',
      partials: ['test/fixtures/modules/*.hbs'],
      data: 'test/fixtures/data/data.json',
      options: {
      },
      files: [
        {
          expand: true,     // Enable dynamic expansion.
          cwd: 'test/fixtures',      // Src matches are relative to this path.
          src: '*.hbs', // Actual pattern(s) to match.
          dest: 'tmp/',   // Destination path prefix.
          ext: '.html'  // Dest filepaths will have this extension.
        }
      ]
    }
  },
})
```