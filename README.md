# [WIP] Jinja Compat Tests

**This project tests compatibility of Jinja2 template language with Nunjucks and Twig.**

[![Build Status](https://travis-ci.org/jbmoelker/jinja-compat-tests.svg)](https://travis-ci.org/jbmoelker/jinja-compat-tests)

[Jinja2](http://jinja.pocoo.org/) (Python) introduced an expressive template language. It has since been adapted by other template engines (languages): [Nunjucks](https://mozilla.github.io/nunjucks/) (JavaScript), [Twig](http://twig.sensiolabs.org/) (PHP) and others. While the template syntax between these implementations is very similar, they do have their differences. This project uses a single set of [tests](tests/), generates the output with all template engines separately, and then compares the output.


## Test results

You can [**browse the test results online**](https://jbmoelker.github.io/jinja-compat-tests/). In addition all raw data is available as JSON:

* [Test templates](https://jbmoelker.github.io/jinja-compat-tests/api/tests.json) grouped by feature.
* [Test data](https://jbmoelker.github.io/jinja-compat-tests/api/data.json) passed to templates.
* [Results](https://jbmoelker.github.io/jinja-compat-tests/api/results.json) of tests per template engine.
* [Error logs](https://jbmoelker.github.io/jinja-compat-tests/api/errors.json) of tests per template engine.
* [Versions](https://jbmoelker.github.io/jinja-compat-tests/api/versions.json) of languages and engines used.
* [Documentation references](https://jbmoelker.github.io/jinja-compat-tests/api/docs.json) of all template features for all engines.


## Test setup

This project aims to cover all features of the templating language(s). The test setup consists of:

* [1 shared set of test files](tests) for all template features
* a render script for each template engine (see below)

All scripts render the tests to `output/` in a directory per template engine. The output file has the same name as the test file, but with the rendered result. If a render error occurs an error log file is written to the tests output destination instead.


## Test engines

* [Jinja2](#jinja2) (Python)
* [Nunjucks](#nunjucks) (JavaScript)
* [Twig](#twig) (PHP)
* [Swig](#swig) (JavaScript)
* [Django](#django) (Python)

### Jinja2

#### Install

The Jinja2 setup requires [Python](https://www.python.org/) (>= 3.3) and `pip3` (comes with Python3) to be installed. Then install dependencies:

```bash
pip3 install -r requirements.txt
```

#### Run tests

Render all [tests](tests/) to `output/jinja2/`:

```bash
python3 test-jinja2.py
```


### Nunjucks

#### Install

The Nunjucks setup requires [NodeJS](https://nodejs.org/en/) (>= 6.0) and [npm](https://www.npmjs.com/) (comes with Node) to be installed. Then install dependencies:

```bash
npm install
```

#### Run tests

Render all [tests](tests/) to `output/nunjucks/`:

```bash
node test-nunjucks.js
```


### Twig

#### Install

The Twig setup requires [PHP](https://secure.php.net/) (>= 5.5.9) and [Composer](https://getcomposer.org/) to be installed. Then install dependencies:

```bash
composer install
```

#### Run tests

Render all [tests](tests/) to `output/twig/`:

```bash
php test-twig.php
```


### Swig

#### Install

The [Swig](https://github.com/voorhoede/swig#readme) setup requires [NodeJS](https://nodejs.org/en/) (>= 6.0) and [npm](https://www.npmjs.com/) (comes with Node) to be installed. Then install dependencies:

```bash
npm install
```

#### Run tests

Render all [tests](tests/) to `output/swig/`:

```bash
node test-swig.js
```

### Django

#### Install

The Django setup requires [Python](https://www.python.org/) (>= 3.3) and `pip3` (comes with Python3) to be installed. Then install dependencies:

```bash
pip3 install -r requirements.txt
```

#### Run tests

Render all [tests](tests/) to `output/django/`:

```bash
python3 test-django.py
```


## Roadmap

* Tests for all templating features and all their use cases
* UI to compare output of templating engines
* Add more templating engines (Jinjava (Java), Pongo (Go Lang), ...)