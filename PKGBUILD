#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <archiv8@artisteducator.com>
# Contributor: Ross Clark <archiv8@artisteducator.com>


_cvsorg="drush-ops"
_pkgname="drush"
_pkgsuffix="launcher"


pkgname="${_pkgname}-${_pkgsuffix}"
pkgver=0.10.1
pkgrel=1
pkgdesc="A small wrapper around Drush for your global $PATH"
arch=('any')
url="http://drupalconsole.com/"
license=('GPL')
depends=('php')
makedepends=("composer")
source=("${_pkgname}.phar"::"https://github.com/${_cvsorg}/${_pkgname}-${_pkgsuffix}/releases/latest/download/${_pkgname}.phar")
sha512sums=('73456d685c028fd23c87b53e864906958c91c50b14059cb79bc88eccf098e495eba3ecfe27c962786a8639124f7a2359af8d6f4ecf180b457a3856d046802018')

# build() {
#   cd "${srcdir}/${_pkgname}-${pkgver//_/-}"
#  php /usr/bin/composer install --no-dev
#  ulimit -Sn 2048
#   php -d phar.readonly=Off /usr/bin/php-box build
# }

package() {
  cd "${srcdir}"
  install -D -m755 "drush.phar" "${pkgdir}/usr/bin/drush"
}
