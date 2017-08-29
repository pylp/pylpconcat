## Information

[![PyPI](https://img.shields.io/pypi/v/pylpconcat.svg)](https://pypi.org/project/pylpconcat)
[![PyPI](https://img.shields.io/pypi/format/pylpconcat.svg)]()
[![PyPI](https://img.shields.io/pypi/pyversions/pylpconcat.svg)]()

**pylpconcat** is a plugin for [Pylp](https://github.com/pylp/pylp) that can concatenate
file contents.


## Installation

Install **pylpconcat** with `pip`:

    pip install pylpconcat

If you don't have Python `Scripts` folder in your PATH, you can run also:

    python -m pip install pylpconcat


## Usage

The usual use of **pylpconcat** is as follows:

```python
import pylp
from pylpconcat import concat

pylp.task('scripts', lambda:
    pylp.src('lib/*.js')
      .pipe(concat('all.js'))
      .pipe(pylp.dest('dist'))
)
```

Moreover, you can specify the separator to add between files (`\n` by default):

```python
import pylp
from pylpconcat import concat

pylp.task('scripts', lambda:
    pylp.src('lib/*.js')
      .pipe(concat('all.js', sep=';'))
      .pipe(pylp.dest('dist'))
)
```
