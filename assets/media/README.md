# Encoding instructions

Copy an MP4 file to this directory and run the following command at the terminal:

`ffmpeg -i YOUR_MEDIA_FILENAME_HERE.mp4 -profile:v baseline -level 3.0 -s 640x360 -start_number 0 -hls_time 10 -hls_list_size 0 -f hls 1/hls/index.m3u8`