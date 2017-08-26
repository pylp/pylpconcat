## Information

**pylpconcat** is a plugin for [Pylp](https://github.com/pylp/pylp) that can concatenate
file contents.

**Note**: due to Pylp's asynchronous piping system, the order of the files concatenated
is undefined. This will be fix in the next version.


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

Moreover, you can specify the separator to add between files:

```python
import pylp
from pylpconcat import concat

pylp.task('scripts', lambda:
    pylp.src('lib/*.js')
      .pipe(concat('all.js', sep=';'))
      .pipe(pylp.dest('dist'))
)
```
