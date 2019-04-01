# Maliput Workspace Setup

## Supported platforms

* For regular workspaces, only Ubuntu Bionic Beaver 18.04 LTS is supported as host OS.

* For dockerized workspaces, only Nvidia powered machines are supported as host machines.

## Prerequisites

* To get all necessary scripts and repos files, clone this repo locally at some path.

* To actually use the scripts, make sure you have `jinja2` installed:

```sh
sudo apt install python3-jinja2
```

* To use dockerized workspaces, make sure [nvidia-docker2](https://github.com/nvidia/nvidia-docker/wiki/Installation-(version-2.0)) is installed.

## Basic setup

To setup a regular workspace, run:

```sh
path/to/dsim-repos-index/setup/setup_workspace path/to/my/workspace
```

To setup a dockerized workspace, run:

```sh
path/to/dsim-repos-index/setup/setup_dockerized_workspace path/to/my/workspace
```

Both operations will setup a `colcon` like workspace that uses binaries for
upstream dependencies whenever possible.

To bring up any of these workspaces, run:

```sh
source path/to/my/workspace/bringup
```

You can always leave the workspace by `exit`ing it.

## Advanced setup

None of the basic setup scripts described so far actually build up a workspace, but rely
on another script that is generated from proper default options. These options, however,
are not the only possible combinations available but just the most commonly used ones.

You can check all available workspace options by running:

```sh
path/to/dsim-repos-index/setup/generate_setup_script -h
```

The output of this script is pure bash code that can be verified, modified and executed. It
is also self contained and thus portable.