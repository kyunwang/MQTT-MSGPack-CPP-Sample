# MSGPack + MQTT CPP Example

A very basic example (test) to get MSGPack and MQTT working in CPP.
Wanted to have as little dependencies and build steps as possible to reduce complexity to get started.

A previous working attempt made use of Boost, but as a non-CPP native all of these extra dependencies, build and install steps were just too time consuming.

> Currently confirmed working on OSX only

- [Quick start](#quick-start)
	- [Prerequisites](#prerequisites)
- [Approach](#approach)


## Quick start
Assuming you are using VSCode, if you do not, see the scripts used in `.vscode/tasks.json` for reference.
1. `git submodule update --init --recursive`
2. Run task **"Build & Install Prerequisite Dependencies"** once
3. Run **"Build Libraries"** once
4. Run **"Build and Run Script"** to run the script and on every update thereafter


The scripts will handle the dependencies:
- https://github.com/nlohmann/json
- https://github.com/eclipse/paho.mqtt.cpp 

### Prerequisites
- CMake
- C++ version of 17+
  - Older versions haven't been tested

## Approach
This example does NOT make use of any of the cpp msgpack libraries like msgpack-c. I've tried almost all of them but couldn't get a quick test running to catch non predefined data structures.

I've opted to use nlohmann's json library instead which has a `to/from` msgpack <-> json utilities which suit my needs well including it practically bypassing predefined static typing and avoiding any visitor/parse mechanisms or including the Boost library.
