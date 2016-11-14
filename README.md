# ROS-less workspace #
This is a catkin workspace for you to clone when you want to develop without
ROS (but with catkin).

# How to set up #
The first step needs to be done only once. It ensures, this workspace will not
extend any other, e.g. ROS one.

1. **[IMPORTANT]** `CMAKE_PREFIX_PATH=""`
2. `git clone --recursive git@gitlab.ipb.uni-bonn.de:igor/rosless-workspace.git`
3. `cd rosless-workspace`
4. `catkin build -v`

The workspace contains `catkin` package, which is needed for building non-ROS
workspaces with `catkin_tools`.

Copy any project of yours into the `src/` folder and it should be built with
`catkin build` command.

If your project depends on other projects that can be checked out with git, you
can use a `fetch` verb of `catkin`. Install this verb following instructions on
the [catkin_tools_fetch][fetch-github] GitHub page. It allows to run `catkin
fetch` from your catkin workspace and manages the dependency downloads for you.

[fetch-github]: https://github.com/niosus/catkin_tools_fetch