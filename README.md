# IPB workspace #

[![Travis](https://img.shields.io/travis/PRBonn/ipb_workspace.svg?style=for-the-badge)](https://travis-ci.org/PRBonn/ipb_workspace)

This is a catkin workspace for you to clone when you want to develop with or
without ROS (but with catkin). We use `pipenv` to have a control over the
dependencies.

# How to set up your workspace #
Follow these steps to setup a new empty workspace.

## 1. Check prerequisites ##
We make use of python virtual environtments by using
[pipenv](https://github.com/pypa/pipenv) that makes using virual environments
easy. All the other prerequisites will be taken care of by `pipenv`. See the configuration file of the virtual environment here: [`Pipfile`](Pipfile).

```bash
# Install pipenv if needed.
pip install --user pipenv  
```

## 2. Decide if you want to use ROS ##

### Yep, give me ROS! ###
```bash
# If you want to use ROS make sure to source its setup script:
source /opt/ros/melodic/setup.sh
```

### Nope, I don't want ROS! ###
```bash
# Run this to make sure we don't extend a ROS workspace.
CMAKE_PREFIX_PATH=""
```

## 3. Get the workspace and build it ##
```bash
# Make sure you use --recursive as we need to check out submodules.
git clone --recursive https://github.com/PRBonn/ipb_workspace.git
cd ipb_workspace
# We use a pipenv that ensures you have correct dependencies.
# Here we install the dependencies and run the virtual environment.
pipenv install
pipenv shell
# Build the empty workspace.
catkin build 
```

The workspace contains the `catkin` package as a submodule, which is needed for
building workspaces with `catkin_tools`. If you did not use `--recursive` flag when pulling this package, make sure to explicitly checkout the submodule by running

```bash
git submodule update --init
```

# How to use the workspace #
Once you have set up this workspace, copy any project of yours into the `src/`
folder and build it with `catkin build` command. 

We rely on
[catkin_tools](https://catkin-tools.readthedocs.io/en/latest/installing.html). It should be installed automatically while you are setting up your virtual environment.

If your project depends on other projects that can be checked out with git, you
can use a `fetch` verb of `catkin` from the package
[catkin_tools_fetch][fetch-github]. It will also be installed automatically
during the virtual environment setup. See its Guthub page for more details.

[fetch-github]: https://github.com/PRBonn/catkin_tools_fetch
