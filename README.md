# sponzy-watermark
i need a watermark for a script called sponzy


1.	How do I upgrade or get the Laravel ffmpeg to work with version 7 of ffmpeg?
2.	I need the watermark function changes so that creators can add their own watermarks for use the site.  The watermark would be like OnlyFans Fansly etc., the creator can add a text that they want instead of using the sites default watermark.  Right now, we can get it to work with the photos but are having issues getting it to work with the videos.  We are facing issues with adding text over a video as a watermark using pbmedia/laravel-ffmpeg.  Please help me out, what I am doing wrong?
$format = new X264();
$format->setAudioCodec('aac');
$format->setVideoCodec('libx264');
$format->setKiloBitrate(0);

$localPath = '/' . $this->video->id . '.mp4';

$ffmpeg = FFMpeg::fromDisk("public")
          ->open($localPath)
          ->addFilter(function ($filters) {
            $filters->custom("drawtext=fontfile=S:/Freelancer/version58trials/version58trials/public/webfonts/arial.TTF:text='Stack Overflow':fontcolor=white:fontsize=24");
          })
          ->export()
          ->toDisk('public')
          ->inFormat($format)
          ->save("watermark_video_added.mp4");



[2024-08-25 08:53:25] local.INFO: ffprobe running command C:\ffmpeg\bin\ffprobe.exe -help -loglevel quiet  
[2024-08-25 08:53:25] local.INFO: ffprobe executed command successfully  
[2024-08-25 08:53:25] local.INFO: ffprobe running command C:\ffmpeg\bin\ffprobe.exe "S:/Freelancer/version58trials/version58trials/storage/app/public/143.mp4" -show_streams -print_format json  
[2024-08-25 08:53:25] local.INFO: ffprobe executed command successfully  
[2024-08-25 08:53:25] local.INFO: ffmpeg running command C:\ffmpeg\bin\ffmpeg.exe -y -ss 00:00:01.00 -i "S:/Freelancer/version58trials/version58trials/storage/app/public/143.mp4" -vframes 1 -f image2 "S:/Freelancer/version58trials/version58trials/storage/app/public/RzBnC8ZESC40iRSfOuED66cb37513ccd11724594001-poster.jpg"  
[2024-08-25 08:53:26] local.INFO: ffmpeg executed command successfully  
[2024-08-25 08:53:26] local.INFO: ffmpeg running command C:\ffmpeg\bin\ffmpeg.exe -y -i "S:/Freelancer/version58trials/version58trials/storage/app/public/143.mp4" -threads 12 -vcodec libx264 -acodec aac -refs 6 -coder 1 -sc_threshold 40 -flags +loop -me_range 16 -subq 7 -i_qfactor 0.71 -qcomp 0.6 -qdiff 4 -trellis 1 -b:a 128k -vf "[in]drawtext=fontfile=S:/Freelancer/version58trials/version58trials/public/webfonts/arial.TTF:text='Stack Overflow':fontcolor=white:fontsize=24[out]" "S:/Freelancer/version58trials/version58trials/storage/app/public/watermark_video_added.mp4"  
[2024-08-25 08:53:26] local.INFO: ffprobe running command C:\ffmpeg\bin\ffprobe.exe "S:/Freelancer/version58trials/version58trials/storage/app/public/143.mp4" -show_format -print_format json  
[2024-08-25 08:53:26] local.INFO: ffprobe executed command successfully  
[2024-08-25 08:53:26] local.ERROR: ffmpeg failed to execute command C:\ffmpeg\bin\ffmpeg.exe -y -i "S:/Freelancer/version58trials/version58trials/storage/app/public/143.mp4" -threads 12 -vcodec libx264 -acodec aac -refs 6 -coder 1 -sc_threshold 40 -flags +loop -me_range 16 -subq 7 -i_qfactor 0.71 -qcomp 0.6 -qdiff 4 -trellis 1 -b:a 128k -vf "[in]drawtext=fontfile=S:/Freelancer/version58trials/version58trials/public/webfonts/arial.TTF:text='Stack Overflow':fontcolor=white:fontsize=24[out]" "S:/Freelancer/version58trials/version58trials/storage/app/public/watermark_video_added.mp4": ffmpeg version 2024-08-21-git-9d15fe77e3-full_build-www.gyan.dev Copyright (c) 2000-2024 the FFmpeg developers
  built with gcc 13.2.0 (Rev5, Built by MSYS2 project)
  configuration: --enable-gpl --enable-version3 --enable-static --disable-w32threads --disable-autodetect --enable-fontconfig --enable-iconv --enable-gnutls --enable-libxml2 --enable-gmp --enable-bzlib --enable-lzma --enable-libsnappy --enable-zlib --enable-librist --enable-libsrt --enable-libssh --enable-libzmq --enable-avisynth --enable-libbluray --enable-libcaca --enable-sdl2 --enable-libaribb24 --enable-libaribcaption --enable-libdav1d --enable-libdavs2 --enable-libopenjpeg --enable-libquirc --enable-libuavs3d --enable-libxevd --enable-libzvbi --enable-libqrencode --enable-librav1e --enable-libsvtav1 --enable-libvvenc --enable-libwebp --enable-libx264 --enable-libx265 --enable-libxavs2 --enable-libxeve --enable-libxvid --enable-libaom --enable-libjxl --enable-libvpx --enable-mediafoundation --enable-libass --enable-frei0r --enable-libfreetype --enable-libfribidi --enable-libharfbuzz --enable-liblensfun --enable-libvidstab --enable-libvmaf --enable-libzimg --enable-amf --enable-cuda-llvm --enable-cuvid --enable-dxva2 --enable-d3d11va --enable-d3d12va --enable-ffnvcodec --enable-libvpl --enable-nvdec --enable-nvenc --enable-vaapi --enable-libshaderc --enable-vulkan --enable-libplacebo --enable-opencl --enable-libcdio --enable-libgme --enable-libmodplug --enable-libopenmpt --enable-libopencore-amrwb --enable-libmp3lame --enable-libshine --enable-libtheora --enable-libtwolame --enable-libvo-amrwbenc --enable-libcodec2 --enable-libilbc --enable-libgsm --enable-libopencore-amrnb --enable-libopus --enable-libspeex --enable-libvorbis --enable-ladspa --enable-libbs2b --enable-libflite --enable-libmysofa --enable-librubberband --enable-libsoxr --enable-chromaprint
  libavutil      59. 34.100 / 59. 34.100
  libavcodec     61. 11.100 / 61. 11.100
  libavformat    61.  5.101 / 61.  5.101
  libavdevice    61.  2.100 / 61.  2.100
  libavfilter    10.  2.102 / 10.  2.102
  libswscale      8.  2.100 /  8.  2.100
  libswresample   5.  2.100 /  5.  2.100
  libpostproc    58.  2.100 / 58.  2.100
Input #0, mov,mp4,m4a,3gp,3g2,mj2, from 'S:/Freelancer/version58trials/version58trials/storage/app/public/143.mp4':
  Metadata:
    major_brand     : mp42
    minor_version   : 0
    compatible_brands: mp41isom
    creation_time   : 2024-08-25T10:28:56.000000Z
  Duration: 00:00:05.65, start: 0.000000, bitrate: 6491 kb/s
  Stream #0:0[0x1](und): Video: h264 (Main) (avc1 / 0x31637661), yuv420p(progressive), 1906x960 [SAR 1:1 DAR 953:480], 6317 kb/s, 30 fps, 30 tbr, 30k tbn (default)
      Metadata:
        creation_time   : 2024-08-25T10:28:56.000000Z
        handler_name    : VideoHandler
        vendor_id       : [0][0][0][0]
        encoder         : AVC Coding
  Stream #0:1[0x2](und): Audio: aac (LC) (mp4a / 0x6134706D), 48000 Hz, stereo, fltp, 192 kb/s (default)
      Metadata:
        creation_time   : 2024-08-25T10:28:56.000000Z
        handler_name    : SoundHandler
        vendor_id       : [0][0][0][0]
[AVFilterGraph @ 0000020e99b5f0c0] No option name near '/Freelancer/version58trials/version58trials/public/webfonts/arial.TTF:text=Stack Overflow:fontcolor=white:fontsize=24'
[AVFilterGraph @ 0000020e99b5f0c0] Error parsing a filter description around: [out]
[AVFilterGraph @ 0000020e99b5f0c0] Error parsing filterchain '[in]drawtext=fontfile=S:/Freelancer/version58trials/version58trials/public/webfonts/arial.TTF:text='Stack Overflow':fontcolor=white:fontsize=24[out]' around: [out]
Error opening output file S:/Freelancer/version58trials/version58trials/storage/app/public/watermark_video_added.mp4.
Error opening output files: Invalid argument

Thank you for any help you can provide.
Lenard Blanks
