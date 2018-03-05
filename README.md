# ROS-less workspace #
This is a catkin workspace for you to clone when you want to develop without
ROS (but with catkin). We use `pipenv` to have a control over the dependencies.
You should have a python virtual environment for your worspace.

## Prerequisites ##
We use `pipenv` to make sure all dependencies are satisfied.
Make sure you are using `Python 3` and install it with 
```bash
pip install --user pipenv
```

# How to set up your workspace #
The first step ensures, this workspace will not extend any other, e.g. ROS one.
We make use of python virtual environtments by using
[`pipenv`](https://github.com/pypa/pipenv) that makes using virual environments
easy.

```bash
# Omit this line you WANT to extend a ROS workspace.
CMAKE_PREFIX_PATH=""
# Get the workspace and move into it.  
git clone --recursive https://github.com/Photogrammetry-Robotics-Bonn/catkin_tools_fetch.git
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

# How to use #
Once you have set up this workspace, copy any project of yours into the `src/`
folder and build it with `catkin build` command. 

We rely on
[catkin_tools](https://catkin-tools.readthedocs.io/en/latest/installing.html). It should be installed while you are setting up your virtual environment.

If your project depends on other projects that can be checked out with git, you
can use a `fetch` verb of `catkin`.

- Install `fetch` following instructions on the
  [catkin_tools_fetch][fetch-github] GitHub page.
- Use it in this workspace like this:
```
catkin dependencies fetch --default_url git@gitlab.ipb.uni-bonn.de:ipb-tools
```

[fetch-github]: https://github.com/Photogrammetry-Robotics-Bonn/catkin_tools_fetch
