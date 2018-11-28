# ROS-less workspace #

[![Travis](https://img.shields.io/travis/PRBonn/rosless-workspace.svg?style=flat-square)](https://travis-ci.org/PRBonn/rosless-workspace)

This is a catkin workspace for you to clone when you want to develop without
ROS (but with catkin). We use `pipenv` to have a control over the dependencies.
You should have a python virtual environment for your worspace.

# How to set up your workspace #
The first step ensures, this workspace will not extend any other, e.g. ROS one.
We make use of python virtual environtments by using
[pipenv](https://github.com/pypa/pipenv) that makes using virual environments
easy.

```bash
# Install pipenv if needed.
pip install --user pipenv 
# Omit this line you WANT to extend a ROS workspace.
CMAKE_PREFIX_PATH=""
# Get the workspace and move into it.  
git clone --recursive https://github.com/PRBonn/rosless-workspace.git
cd rosless-workspace
# We use a pipenv that ensures you have correct dependencies.
# Here we install the dependencies and run the virtual environment.
pipenv install
pipenv shell
# Build the empty workspace.
catkin build 
```

The workspace contains the `catkin` package, which is needed for building
non-ROS workspaces with `catkin_tools`.

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
