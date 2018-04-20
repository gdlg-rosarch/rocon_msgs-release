# Script generated with Bloom
pkgdesc="ROS - Communication types (msgs/srvs/actions) for robotics in concert (aka multimaster)."
url='http://www.ros.org/wiki/rocon_msgs'

pkgname='ros-kinetic-rocon-msgs'
pkgver='0.9.0_2'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-concert-msgs'
'ros-kinetic-concert-service-msgs'
'ros-kinetic-gateway-msgs'
'ros-kinetic-rocon-app-manager-msgs'
'ros-kinetic-rocon-device-msgs'
'ros-kinetic-rocon-interaction-msgs'
'ros-kinetic-rocon-service-pair-msgs'
'ros-kinetic-rocon-std-msgs'
'ros-kinetic-rocon-tutorial-msgs'
'ros-kinetic-scheduler-msgs'
)

conflicts=()
replaces=()

_dir=rocon_msgs
source=()
md5sums=()

prepare() {
    cp -R $startdir/rocon_msgs $srcdir/rocon_msgs
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
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

