_commit=f155ed9aca886d631cb3ad706b86ece99555e606
pkgname=audacious-plugins
pkgver=3.7.2
pkgrel=1
pkgdesc="Plugins for Audacious (qt5 interface)"
arch=('x86_64')
url="http://audacious-media-player.org/"
license=('BSD' 'GPL')

makedepends=("audacious" 'qt5-multimedia'
             'glib2' 'python2' # for gdbus-codegen
             'alsa-lib' 'pulseaudio' 'jack2' 'lame' 'libvorbis' 'flac'
             'mpg123' 'faad2' 'ffmpeg' 'libmodplug' 'fluidsynth' 'libcdio-paranoia' 'wavpack'
             'dbus-glib' 'libnotify' 'curl' 'libmtp'
             'neon' 'libmms' 'libcue')

optdepends=('alsa-lib: Advanced Linux Sound Arch. output'
            'pulseaudio: PulseAudio output'
            'jack2: Jack Audio Connection Kit output'
            'lame: FileWriter MP3 output'
            'libvorbis: Vorbis input, FileWriter Vorbis output'
            'flac: FLAC input, FileWriter FLAC output'

            'mpg123: MP3 input'
            'faad2: AAC input'
            'ffmpeg: ffaudio input'
            'libmodplug: modplug input'
            'fluidsynth: MIDI FluidSynth backend input'
            'libcdio-paranoia: CD Digital Audio input'
            'wavpack: WavPack input'

            'dbus-glib: Gnome Shortcuts Plugin'
            'libnotify: libnotify OSD'
            'curl: AudioScrobbler Client'
            'libmtp: Upload to MTP device'

            'neon: neon-based http transport'
            'libmms: libmms-based mms transport'
            'libcue: CUE playlist format'

            'qt5-multimedia: qtaudio support')

source=(https://github.com/audacious-media-player/audacious-plugins/archive/${_commit}.zip)
sha256sums=('424baa8940e1cc983636cedd44dca6620c590fd5712595cf1a3131314dcb9048')

build() {
  cd "$srcdir/$pkgname-$_commit"

  ./configure \
    --prefix=/usr \
    --enable-amidiplug \
    --enable-qt \
    --disable-gtk 
  make
}

package() {
  cd "$srcdir/$pkgname-$_commit"
  make DESTDIR="$pkgdir" install
  install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
