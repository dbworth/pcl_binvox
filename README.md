#pcl_binvox

Command-line tools to convert between .binvox and .pcd file formats.

binvox is a binary format for a 3D voxel grid, developed by [Patrick Min](http://www.patrickmin.com/binvox/).  
pcd is Point Cloud Data from PCL ([PointCloud Library](http://www.pointclouds.org)).

David Butterworth, 2016.

.

### Usage

This was tested on Ubuntu 14.04 with PCL 1.8  

Install this package in a catkin workspace.  
Set your path:  
```
$ export PATH=$PATH:~/path/to/your/catkin/workspace/devel/lib/pcl_binvox/  
$ roscd pcl_binvox
```

**Convert from .binvox to .pcd**  
The output file name is specified first. Then you can list multiple binvox files as input.
```
$ binvox2pcd -o output.pcd data/chair.binvox
```

**Convert from .pcd to .binvox**  
Specify the voxel grid resolution, between 32 and 1024.
```
$ pcd2binvox -d 32 data/teapot.pcd output.binvox
```

.

### Screenshots:

A room was scanned to create a PointCloud and then voxelized:  
<img src="https://raw.githubusercontent.com/dbworth/pcl_binvox/master/screenshots/room_scan_from_pointcloud.png" width=900>

Original binvox file:  
<img src="https://raw.githubusercontent.com/dbworth/pcl_binvox/master/screenshots/chair_orig_binvox.png" width=500>

Converted to PointCloud:  
<img src="https://raw.githubusercontent.com/dbworth/pcl_binvox/master/screenshots/chair_converted_to_pcd.png" width=500>



