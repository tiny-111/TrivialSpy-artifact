# TrivialSpy

## Build

First, we need to clone the entire repo with all dependant submodules:

```
git clone --recursive https://github.com/tiny-111/TrivialSpy-artifact.git
```

After cloning the repo, use the build script to build TrivialSpy.

```
cd TrivialSpy-artifact
# release build
./build.sh
# build for debugging
./build_debug.sh
```

## Usage

The TrivialSpy tool is built as a client of Dynamorio, which can be invoked as follows.

```
# Assume you are in the root directory of this repo (TrivialSpy-artifact)
export DRRUN=`pwd`/build/bin64/drrun
$DRRUN -t trivialspy -- ${APP} ${ARGS}
```
