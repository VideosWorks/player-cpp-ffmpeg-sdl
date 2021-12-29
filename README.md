# Simple C++ video player using FFmpeg 4 and SDL 2.0 

Supports video with audio.

## Examples

1 - https://ottverse.com/free-hls-m3u8-test-urls/

## Windows setup (Tested on x64 environment)
1 - Install FFMpeg here https://ffmpeg.zeranoe.com/builds/win64/dev/ and add it to your path

2 - Install SDL here https://www.libsdl.org/download-2.0.php and add it to your path

3 - (Optional) Install g++ and make from MinGW https://sourceforge.net/projects/mingw/

4 - Create a env variable to the /include folder of the FFmpeg folder: <FFmpeg_include>, and for the lib folder <FFmpeg_lib>

5 - Create a env variable to the /include folder of the SDL2 folder: <SDL2_include>

6 - Run make
        <br />
        ```
        make -f makefile_windows
        ```

7 - Run<br />
    ```
    ./player <video_address>
    ```

## Linux setup (Tested on Ubuntu)

1 - Install FFmpeg version >= 4
        <br />
        ```
        sudo apt update && sudo apt install ffmpeg x264 x265 libavdevice-dev
        ```

2 - Install SDL >= 2.0<br />
        ```
        sudo apt-get install libsdl2-dev
        ```

3 - Install:<br />
        ```
        make
        ```

4 - Run<br />
    ```
    ./player <video_address>
    ```

## Mac setup (Tested on Big Sur)

1 - Install FFmpeg version >= 4
        <br />
        ```
        brew update && brew install ffmpeg x264 x265 libavdevice-dev
        ```

2 - Install SDL >= 2.0<br />
        ```
        brew install libsdl2-dev
        ```

3 - Install:<br />
        ```
        make
        ```

4 - Run<br />
```
video_address="https://multiplatform-f.akamaihd.net/i/multi/april11/sintel/sintel-hd_,512x288_450_b,640x360_700_b,768x432_1000_b,1024x576_1400_m,.mp4.csmil/master.m3u8"
./player $video_address
```
