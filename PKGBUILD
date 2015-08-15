# Maintainer: Thibault Suzanne <thi [DOT] suzanne [AT] gmail [DOT] com>
pkgname=emacs-zlc-git
pkgver=20120926
pkgrel=3
pkgdesc="Provides zsh like completion for minibuffer in emacs"
url="https://github.com/mooz/emacs-zlc"
arch=('any')
license=('GPL')
depends=('emacs')
makedepends=('git')

_gitroot="https://github.com/mooz/emacs-zlc.git"
_gitname="emacs-zlc"

install=emacs-zlc.install

build() {
  cd $srcdir
  
  msg "Connecting to GIT server..."
  
  if [[ -d "$srcdir/$_gitname" ]]; then
    cd $_gitname && git pull origin
    msg "The local files are updated."
  else
    git clone $_gitroot
  fi
  
  msg "GIT checkout done or server timeout"
  
}

package() {
  cd "$srcdir/$_gitname"
  #mkdir $pkgdir/usr{,/share{,/emacs{,/site-lisp}}}}
  install -Dm644 "zlc.el" "$pkgdir/usr/share/emacs/site-lisp/zlc.el"
}
