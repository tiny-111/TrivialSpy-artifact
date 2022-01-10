# TrivialSpy

## Build

First, we need to clone the entire repo with all dependant submodules:

```
git clone --recursive https://github.com/tiny-111/TrivialSpy-artifact.git
```

After cloning the repo, use the build script to build TrivialSpy.

```
cd TrivialSpy-artifact
./build.sh
```

## Usage

The TrivialSpy tool is built as a client of Dynamorio, which can be invoked as follows.

```
# Assume you are in the root directory of this repo (TrivialSpy-artifact)
export DRRUN=`pwd`/build/bin64/drrun
$DRRUN -t trivialspy -- ${APP} ${ARGS}
```

## Build and Run Example

We include the IS program from NPB 3.4.2 as an example to profile with TrivialSpy. After building the TrivialSpy tool with `build.sh` build script, we then build the example programs as follows for further profiling. Note that the makefile in `config/make.def` is already modified to append `-g` options for human readable debug information.

```
export DRRUN=`pwd`/build/bin64/drrun
cd example && make
$DRRUN -t trivialspy -- ./bin/is.C.x
```

The profiling results are stored in a newly generated folder `x86-<hostname>-<pid>-trivialspy`. In the result folder, the overview profiles are listed in `trivialspy.log` and the per-thread detailed profiles as well as the source code attributions are listed in `thread-<n>.log`.

## Tested Platforms

We have tested TrivialSpy on Intel(R) Xeon(R) CPU E5-2680 v4 (Intel Broadwell) platform.
