# $Id: pkgbuild-mode.el,v 1.23 2007/10/20 16:02:14 juergen Exp $
# Maintainer: Elliott Seyler <emhs@mossberg>
pkgname=sweethome3d-furniture-library
pkgver=1.13
pkgrel=1
pkgdesc="A tool to manage furniture in Sweet Home 3D"
arch=('i686' 'x86_64')
url="http://www.sweethome3d.com/support/forum/viewthread_thread,1550"
license=('GPL')
depends=('java-runtime' 'sweethome3d')
makedepends=('unzip')
source=("http://iweb.dl.sourceforge.net/project/sweethome3d/FurnitureLibraryEditor/FurnitureLibraryEditor-$pkgver.jar"
        'furniturelibraryeditor'
        'furniturelibraryeditor.desktop')
md5sums=('66c5f967f75c76fb88c9359732b248d1'
         'c8980c9deb00e2b167115f795876d7db'
         '152c91ee7b4098c11492f80a587ed64a')

prepare() {
  echo 'cat <<END_OF_TEXT' > temp.sh
  cat furniturelibraryeditor.desktop >> temp.sh
  echo 'END_OF_TEXT' >> temp.sh
  bash temp.sh > furniturelibraryeditor.desktop
  rm temp.sh
}

package() {

  mv com/eteks/furniturelibraryeditor/swing/resources/aboutIcon.png furniturelibraryeditor.png
  mkdir -p $pkgdir/usr/share/java
  mkdir -p $pkgdir/usr/share/pixmaps
  mkdir -p $pkgdir/usr/bin
  mkdir -p $pkgdir/usr/share/applications
  cp FurnitureLibraryEditor-$pkgver.jar $pkgdir/usr/share/java/furniturelibraryeditor.jar
  cp furniturelibraryeditor.png $pkgdir/usr/share/pixmaps
  cp furniturelibraryeditor $pkgdir/usr/bin
  cp furniturelibraryeditor.desktop $pkgdir/usr/share/applications
}

# vim:set ts=2 sw=2 et:
