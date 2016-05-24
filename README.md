# Preface

This is basically the release workflow defined by Gulp as a plugin to avoid code duplication,

For more info: https://github.com/gulpjs/gulp/blob/master/docs/recipes/automate-release-workflow.md

What it does?

1. Bump version in package.json, it follows [SemVer](http://semver.org) semantic versioning, by default the `patch` version
is bumped, but can be changed to release a _minor_ or _major_ version as well via a CLI param. (see below)
1. Update the CHANGELOG.md file with a link to the commits in between the previous and current version.
1. Commit the changes in current workspace.
1. Push the changes to the master branch.
1. Create and push a tag that correspond to the new version.

# Usage

`npm install --save-dev gulp-release-flows`


Create a `gulpfile.js` in your project with:

```js
// add to gulpfile.js
var gulp = require('gulp');
// pass along gulp reference to have tasks imported
require('../')(gulp);
```

In command line, run:

`gulpfile build:release`


This will bump the `patch` version, minor / major can be bumped by the following command:

`gulpfile build:release --bump minor`

Or

`gulpfile build:release --bump major`
