# Script generated with Bloom
pkgdesc="ROS - Interactive control for generic Twist-based robots using interactive markers"


pkgname='ros-lunar-interactive-marker-twist-server'
pkgver='1.2.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-catkin'
'ros-lunar-interactive-markers'
'ros-lunar-roscpp'
'ros-lunar-roslaunch'
'ros-lunar-roslint'
'ros-lunar-visualization-msgs'
)

depends=('ros-lunar-interactive-markers'
'ros-lunar-roscpp'
'ros-lunar-visualization-msgs'
)

conflicts=()
replaces=()

_dir=interactive_marker_twist_server
source=()
md5sums=()

prepare() {
    cp -R $startdir/interactive_marker_twist_server $srcdir/interactive_marker_twist_server
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

