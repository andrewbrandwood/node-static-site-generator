### 3rd party plugin notes.

#### [gulp-sass-generate-contents](https://github.com/andrewbrandwood/gulp-sass-generate-contents)
To enable the compiling of a list of contents in the main scss file and to import all the correct files.  It is required to have a comment at the top of each sass file.

anything on the first line other than a double slash // will result in the file being ignored from the contents and the imports. (see options to change this)

#### [run-sequence](https://www.npmjs.com/package/run-sequence)
Gulp is an asynchronous task runner.  We need the gulp-sass-generate-contents to run and complete before we can compile the sass.  The run-sequence plugin allows us to run the contents file before compiling our SASS.