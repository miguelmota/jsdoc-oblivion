# JSDoc Oblivion Template

A gray and blue [JSDoc](http://usejsdoc.org/) template theme (based off [docstrap](https://github.com/terryweiss/docstrap)).

# Demo

**[https://lab.miguelmota.com/jsdoc-oblivion](https://lab.miguelmota.com/jsdoc-oblivion)**

# Install

Available via [npm](https://www.npmjs.org/)

```bash
npm install jsdoc-oblivion
```

# Usage

JSDoc config file `jsdoc.json`:

```json
{
  "tags": {
    "allowUnknownTags": true
  },
  "source": {
    "includePattern": ".+\\.js(doc)?$",
    "excludePattern": "(^|\\/|\\\\)_"
  },
  "plugins": [],
  "templates": {
    "cleverLinks": false,
    "monospaceLinks": false,
    "default": {
      "outputSourceFiles": true
    },
    "systemName"      : "Oblivion",
    "footer"          : "",
    "copyright"       : "Copyright © 2014",
    "navType"         : "vertical",
    "theme"           : "oblivion",
    "linenums"        : true,
    "collapseSymbols" : false,
    "inverseNav"      : true
  }
}
```

**Using CLI:**

```
jsdoc src/ -r -c jsdoc.json -d docs/ -t node_modules/jsdoc-oblivion/template
```

**Using [Grunt](http://gruntjs.com/):**

```bash
npm install grunt-jsdoc --save-dev
```

`gruntfile.js`:

```javascript
module.exports = function (grunt) {
  grunt.initConfig({
    pkg: grunt.file.readJSON('package.json'),
    jsdoc : {
      dist : {
        src: [
          './**/*.js',
          'README.md'
        ],
        jsdoc: './node_modules/.bin/jsdoc',
        options: {
          destination: 'docs',
          configure: './jsdocjson',
          template: './node_modules/jsdoc-oblivion/template'
        }
      }
    }
  });
  grunt.registerTask('default', ['grunt-jsdoc']);
  grunt.loadNpmTasks('grunt-jsdoc');
};
```

Generate:

```bash
grunt jsdoc
```

# Source

[https://github.com/miguelmota/jsdoc-oblivion](https://github.com/miguelmota/jsdoc-oblivion)

# License

Released under the MIT License.
