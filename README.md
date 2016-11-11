# ROS-less workspace #
This is a catkin workspace for you to clone when you want to develop without
ROS (but with catkin).

# How to use #
- `git clone --recursive git@gitlab.ipb.uni-bonn.de:igor/rosless-workspace.git`
- `cd rosless-workspace`
- `catkin build -v`

Copy any project of yours into the `src/` folder and it should be built with
`catkin build` command.

The workspace already contains `catkin` and `ipb-downloader` packages. Follow
the instructions in `ipb-downloader` project on how to make sure your
dependencies are downloaded.