# ROS-less workspace #
This is a catkin workspace for you to clone when you want to develop without
ROS (but with catkin).

# How to set up #
The first step ensures, this workspace will not extend any other, e.g. ROS one.

1. **[IMPORTANT]** `CMAKE_PREFIX_PATH=""`
2. `git clone --recursive git@gitlab.ipb.uni-bonn.de:global/rosless-workspace.git`
3. `cd rosless-workspace`
4. `catkin build -v`

The workspace contains `catkin` package, which is needed for building non-ROS
workspaces with `catkin_tools`.

# How to use #
Once you have set up this workspace, copy any project of yours into the `src/`
folder and build it with `catkin build` command. For this you need
[catkin_tools](https://catkin-tools.readthedocs.io/en/latest/installing.html) 
and the EmPy library for Python (`pip install empy`).

If your project depends on other projects that can be checked out with git, you
can use a `fetch` verb of `catkin`.

- Install `fetch` following instructions on the
  [catkin_tools_fetch][fetch-github] GitHub page.
- Use it in this workspace like this:
```
catkin dependencies fetch --default_url git@gitlab.ipb.uni-bonn.de:ipb-tools
```

[fetch-github]: https://github.com/niosus/catkin_tools_fetch