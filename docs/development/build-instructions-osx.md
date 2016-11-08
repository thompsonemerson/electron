# Build Instructions (macOS)

Follow the guidelines below for building Electron on macOS.

## Prerequisites

* macOS >= 10.8
* [Xcode](https://developer.apple.com/technologies/tools/) >= 5.1
* [node.js](http://nodejs.org) (external)

If you are using the Python downloaded by Homebrew, you also need to install
the following Python modules:

* [pyobjc](https://pythonhosted.org/pyobjc/install.html)

## Getting the Code

```bash
$ git clone https://github.com/electron/electron
```

## Bootstrapping

The bootstrap script will download all necessary build dependencies and create
the build project files. Notice that we're using [ninja](https://ninja-build.org/)
to build Electron so there is no Xcode project generated.

```bash
$ cd electron
$ ./script/bootstrap.py -v
```

## Building

Build both `Release` and `Debug` targets:

```bash
$ ./script/build.py
```

You can also only build the `Debug` target:

```bash
$ ./script/build.py -c D
```

After building is done, you can find `Electron.app` under `out/D`.

## 32bit Support

Electron can only be built for a 64bit target on macOS and there is no plan to
support 32bit macOS in the future.

## Cleaning

To clean the build files:

```bash
$ npm run clean
```

## Tests

See [Build System Overview: Tests](build-system-overview.md#tests)
