# grunt-lodash v0.5.1

A Grunt wrapper around the [lodash](https://lodash.com/) command-line interface, [lodash-cli](https://npmjs.org/package/lodash-cli).

## Discontinued

This plugin has been discontinued. No further development is expected.

## Getting Started

This plugin requires Grunt `^0.4.1`.
If you haven’t used [Grunt](http://gruntjs.com/) before, be sure to check out the [“Getting Started”](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you’re familiar with that process, you may install this plugin with this command:

```bash
$ npm i --save-dev grunt-lodash
```

Once grunt-lodash has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-lodash');
```

### Overview

In your project’s Gruntfile, add `lodash` to the data object passed to `grunt.initConfig`:

```js
grunt.initConfig({
  'lodash': {
    'build': {
      // output location
      'dest': 'build/lodash.build.js',
      'options': {
        // modifiers for prepared builds
        // modern, strict, compat
        'modifier': 'modern'
      }
    }
  }
});
```

This will produce the same output as:

```bash
$ lodash modern -o build/lodash.build.js
```

Finally, include `lodash` in your desired build task:

```js
grunt.registerTask('build', [
  'clean:dist',
  'lodash'
]);
```

## Configuration

For more details see the [lodash-cli documentation](https://lodash.com/custom-builds).

```js
'lodash': {
  'target': {
    // output location
    'dest': 'build/lodash.build.js'
  },
  'options': {
    // modifiers for prepared builds
    // modern, strict, compat
    // also accepts an array to allow combination with 'strict'
    'modifier': 'modern',
    'modularize': true,
    'category': ['collection', 'function'],
    'exports': ['amd', 'commonjs', 'node'],
    'iife': '!function(window,undefined){%output%}(this)',
    'include': ['each', 'filter', 'map'],
    'minus': ['result', 'shuffle'],
    'plus': ['random', 'template'],
    'template': './*.jst',
    'settings': '{interpolate:/\\{\\{([\\s\\S]+?)\\}\\}/g}',
    'moduleId': 'underscore',
    // with or without the `--`
    // these are the only tested options,
    // as the others don’t make sense to use here
    'flags': [
      '--stdout',
      'development',
      '--production',
      'source-map'
    ],
    // with or without the `-`
    // these are the only tested options,
    // as the others don’t make sense to use here
    'shortFlags': [
      'c',
      '-d',
      'p',
      '-m'
    ]
  }
}
```

## Support

Tested in Node.js 0.10, 0.12, 4, & 5.
