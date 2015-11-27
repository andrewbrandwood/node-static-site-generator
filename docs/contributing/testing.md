# Contributing: Testing

Along with including a skeleton for front-end test, the generator itself has tests stored seperatly along with it's own package file. These tests are to ensure the correct function of the generator itself e.g. certain files / folders exist and that certain files / folders are created after build tasks. The generator tests run on every push.

Whenever new functionality, files or folders are added it is advised to update any and all tests as required as refactoring out a file or renaming a directory will require tests to be modified etc.

## Setting up test environment

* Mocha is the test runner and is required to be installed globally to run all tests. `npm install -g mocha`
* From the project root, `cd` into the `generatorTests` folder.
* Run `npm install`. This will install dependencies for the tests that are seperate from the project dependecnies.
* Still inside the `generatorTests` folder, run the command `mocha` to start running all the tests in the `test` folder. **As these tests may test the gulp output, be prepared for any and all gulp tasks to be run (such as creating folders, files etc)**

To this end, after installation, the whole of the `generatorTests` folder **CAN BE** deleted and **WILL NOT** affect to the rest of the files or output.