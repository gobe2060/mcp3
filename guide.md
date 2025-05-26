# Installing Python

If Python is already installed on your system, uv will detect and use it without configuration. However, uv can also install and manage Python versions. uv automatically installs missing Python versions as needed — you don't need to install Python to get started.

## Getting started

To install the latest Python version:

```
$ uv python install
```

Note: Python does not publish official distributable binary. As such, uv uses distribution from the Astral python-build-standalone project. See the Python distribution documentation for more details.

Once Python is installed, it will be used by uv commands automatically.

Important: When Python is installed by uv, it will not be available globally (i.e. via the `python` command). Support for this feature is in preview. See Installing Python Executables for details.

You can still use `uv run` or create and activate a virtual environment to use python directly.

## Installing a specific version

To install a specific Python version:

```
$ uv python install 3.12
```

To install multiple Python versions:

```
$ uv python install 3.11 3.12
```

To install an alternative Python implementation, e.g. PyPy:

```
$ uv python install [email protected]
```

See the `python install` documentation for more details.

## Reinstalling Python

To reinstall uv-managed Python versions, use `--reinstall`, e.g.:

```
$ uv python install --reinstall
```

This will reinstall all previously installed Python versions. Improvements are constantly being added to the Python distribution, so reinstalling may resolve bugs even if the Python version does not change.

## Viewing Python installation

To view available and installed Python versions:

```
$ uv python list
```

See the `python list` documentation for more details.

## Automatic Python download

Python does not need to be explicitly installed to use uv. By default, uv will automatically download Python versions when they are required. For example, the following would download Python 3.12 if it was not installed:

```
$ uvx [email protected] -c "print('hello world')"
```

Even if a specific Python version is not requested, uv will download the latest version on demand. For example, if there are no Python versions on your system, the following will install Python before creating a new virtual environment:

```
$ uv venv
```

Tip: Automatic Python download can be easily disabled if you want more control over when Python is downloaded.

## Using existing Python versions

uv will use existing Python installations if present on your system. There is no configuration necessary for this behavior: uv will use the system Python if it satisfies the requirements of the command invocation. See the Python discovery documentation for details.

To force uv to use the system Python, provide the `--no-managed-python` flag. See the Python version preference documentation for more details.

## Next steps

To learn more about uv python, see the Python version concept page and the command reference.

Or, read on to learn how to run scripts and invoke Python with uv.

March 18, 2025

Made with Material for MkDocs Insiders
