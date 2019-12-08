<img src="http://52.48.57.141/php-actions.png" align="right" alt="PHP Actions for Github" />

Run your PHPUnit tests in your Github Actions.
==============================================

PHPUnit is a programmer-oriented testing framework for PHP.
It is an instance of the xUnit architecture for unit testing frameworks.

Usage
-----

Create your Github Workflow configuration in `.github/workflows/ci.yml` or similar.

```yaml
name: CI

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v1
    - uses: phpactions/composer@master # or alternative dependency management
    - uses: phpactions/phpunit@master
    # ... then your own project steps ...
```

Inputs
------

The following configuration options are available:

+ `config` Path to the `phpunit.xml` file (default: `test/phpunit/phpunit.xml`)
+ `junit` Path to junut output file (default: `test/phpunit/_junit/junit.xml`)
+ `memory` The memory limit to run your tests with (default: `512M`)

If you require other configurations of phpunit, please request them in the [Github issue tracker](https://github.com/php-actions/phpunit/issues)
