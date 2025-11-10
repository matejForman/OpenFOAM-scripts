# Set of practical scripts to pre or post-process OpenFOAM data

Small practical utility for pre or postprocesing. 
Designed for main OpenFOAM from openfoam.com but all should work 
with other data, maybe even with foam-extend project data. 

## makeMovie.sh 

script is using ffmpeg to generate a mp4 movie from the set of png files called:

***basename.XXXX.png***

Movie is Powerpoint friendly. 

ffmpeg parameters used are: 
- framerate 24 - 24 fps (adjust to your preference: 30, 60, etc.)
- i isoQ.%04d.png - Input pattern (matches isoQ.0001.png, isoQ.0002.png, etc.)
- c:v libx264 - H.264 codec (universally compatible)
- profile:v high -level 4.0 - Compatibility profile for PowerPoint
- pix_fmt yuv420p - Pixel format that PowerPoint requires
- crf 18 - Quality (18 = high quality, range 0-51, lower = better)
- movflags +faststart - Optimizes for streaming/quick playback

Use: makeMovie.sh \<name\>     \<outputName\>.mp4



