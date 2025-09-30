# xf86-video-pvrdri

A fork of the X.org server's modeset driver (along with the glamor
acceleration module), aimed to be used with PowerVR LinuxWS DDK driver.

## Main changes

- Backported GLES-related fixes to Glamor.
- Picked Glamor-less DRI3 implementation, in case it's needed (e.g. the 3D
  acceleration is too weak to do 2D).
- Backported some modesetting driver fixes.
- Some optimizations (mostliy for GLES).
- Purged the DRI2 codepath (always unusable in PowerVR DDK drivers and
  now also abandoned by mainline Mesa).

## How to build

Just install the dependencies for building usual DDXes (along with
libgbm + libepoxy, which Glamor uses), then:

```
mkdir -p build && cd build
meson setup ..
ninja
ninja install
```
