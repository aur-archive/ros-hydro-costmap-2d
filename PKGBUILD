# Script generated with import_catkin_packages.py
# For more information: https://github.com/bchretien/arch-ros-stacks
pkgdesc="ROS - This package provides an implementation of a 2D costmap."
url='http://wiki.ros.org/costmap_2d'

pkgname='ros-hydro-costmap-2d'
pkgver='1.11.11'
_pkgver_patch=0
arch=('any')
pkgrel=1
license=('BSD')

ros_makedepends=(ros-hydro-voxel-grid
  ros-hydro-message-generation
  ros-hydro-message-filters
  ros-hydro-map-msgs
  ros-hydro-sensor-msgs
  ros-hydro-tf
  ros-hydro-catkin
  ros-hydro-roscpp
  ros-hydro-geometry-msgs
  ros-hydro-laser-geometry
  ros-hydro-std-msgs
  ros-hydro-nav-msgs
  ros-hydro-cmake-modules
  ros-hydro-visualization-msgs
  ros-hydro-dynamic-reconfigure
  ros-hydro-rostest
  ros-hydro-pcl-ros
  ros-hydro-pcl-conversions
  ros-hydro-pluginlib)
makedepends=('cmake' 'git' 'ros-build-tools'
  ${ros_makedepends[@]})

ros_depends=(ros-hydro-voxel-grid
  ros-hydro-message-filters
  ros-hydro-map-msgs
  ros-hydro-message-runtime
  ros-hydro-sensor-msgs
  ros-hydro-rosconsole
  ros-hydro-roscpp
  ros-hydro-geometry-msgs
  ros-hydro-laser-geometry
  ros-hydro-std-msgs
  ros-hydro-nav-msgs
  ros-hydro-tf
  ros-hydro-visualization-msgs
  ros-hydro-dynamic-reconfigure
  ros-hydro-rostest
  ros-hydro-pcl-ros
  ros-hydro-pcl-conversions
  ros-hydro-pluginlib)
depends=(${ros_depends[@]})

_tag=release/hydro/costmap_2d/${pkgver}-${_pkgver_patch}
_dir=costmap_2d
source=("${_dir}"::"git+https://github.com/ros-gbp/navigation-release.git"#tag=${_tag})
md5sums=('SKIP')

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/hydro/setup.bash ] && source /opt/ros/hydro/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/hydro \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}
