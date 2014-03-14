# JSHint checkstyle file reporter

Writes checkstyle output to a file. This can be used to report JSHint results to **Jenkins**.

## Usage

### Standard JSHint cli

```bash
# optional specify a different filename
export JSHINT_CHECKSTYLE_FILE="jshint.xml" # default: checkstyle.xml
# run jshint
jshint --reporter node_modules/jshint-checkstyle-file-reporter *.js
```

### Gulp

```javascript
var gulp = require('gulp');
var jshint = require('gulp-jshint');
var checkstyleFileReporter = require('jshint-checkstyle-file-reporter');

// optional specify a different filename:
process.env.JSHINT_CHECKSTYLE_FILE = 'jshint.xml'; // default: checkstyle.xml

gulp.task('jshint', function() {
	gulp.src('*.js')
		.pipe(jshint())
		.pipe(jshint.reporter(checkstyleFileReporter));
});
```