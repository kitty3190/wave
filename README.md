<div align="center">
<img width="175" src="assets/telesync.png"/>
</div>

Telesync: Q's Realtime App SDK

- Realtime cache module
- Development server
- UI components
- Python driver

Issues: https://github.com/h2oai/q/issues

## Development

### Setup and Run

```sh
git clone https://github.com/h2oai/telesync.git
cd telesync
make
make run
```

### Daily Development

- `make run`
- `make run-ui`
- Open root directory in Visual Studio Code.
- Open `py/` in PyCharm.

### Developing apps using bleeding edge

Clone this repo and install into your app's `venv` using pip's `--editable` option `pip install -e`.

For example `./venv/bin/pip install -e path/to/git/telesync/py/`.

### Make tasks

```
all                            Setup and build everything
build                          Build everything
build-db                       Build database
build-py                       Build Python driver
build-server                   Build server
build-ui                       Build UI
clean                          Clean
help                           List all make tasks
run-db                         Run database
run                            Run server
run-ui                         Run UI in development mode (hot reloading)
setup                          Set up development dependencies
```


## Migration Guide

### Breaking changes

**1. `ui.buttons()`, `ui.expander()` and `ui.tabs()` accept a `list` of items instead of var args `*args`**

Before:
```py
ui.buttons(ui.button(...), ui.button(...), ui.button(...))
```

After:
```py
ui.buttons([ui.button(...), ui.button(...), ui.button(...)]) # Note enclosing [ ]
```
