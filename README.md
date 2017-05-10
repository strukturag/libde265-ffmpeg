# libde265-ffmpeg

HEVC/H.265 codec for ffmpeg / libavcodec using libde265

## Building
- Add the `libde265dec.c` to your projects source files.
- Add the folder containing `libde265dec.h` to your include path.
- Change your initialization code (where you call `av_register_all`) to
  also call `libde265dec_register`:

```
  #include <libde265dec.h>

  void initialize(void) {
     ...
     av_register_all();
     libde265dec_register();
     ...
  }
```
- This will replace any existing HEVC/H.265 decoders with libde265.
- Make sure the `libde265` library can be loaded when your application
  runs.

## Dependencies
In addition to a compiler and the public ffmpeg/libavcodec headers,
a couple of other packages must be installed in order to compile the
codec:
- libde265-dev (>= 2.0)

Copyright (c) 2014-2017 struktur AG
