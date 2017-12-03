# mlvtomp4
Simple Batch Converter for Magic Lantern Raw Video (MLV) to MP4 for UNIX

---

### What is this?

The script mlvtomp4 is a Bash script for UNIX (Mac/Linux) systems that converts Magic Lantern Raw Video (MLV) to MP4 files for use in post-processing or review.

### How does it work?

The script works by unpacking the MLV file to reveal the contained DNGs, converting those DNGs into a PPM format, and sequencing them together at 24 frames per second into an MP4 file.

### Setting up the Environment

Before you can use `mlvtomp4`, there are a few dependencies you will need to install:
  - mlv_dump, from the Magic Lantern forums at https://www.magiclantern.fm/forum/index.php?topic=18975.0
  - dcraw, from brew/apt-get, or at https://www.cybercom.net/~dcoffin/dcraw/
  - ffmpeg, from brew/apt-get, or at https://www.ffmpeg.org/
  
`mlvtomp4` will warn you if any of the required dependencies are not present.

### How do I use it?

(assuming the script is saved to `~`)

*If you get a 'not permitted' error when attempting to run the script, try the following command: `~$ chmod +x mlvtomp4`*

Running the script is as simple as providing it the filenames of as many *.MLV files you would like to convert.

```
# Convert the MLV file M01_0001.MLV to MP4
~$ ./mlvtomp4 M01_0001.MLV

# Convert the MLV files M01_0001.MLV and M01_0002.MLV to MP4
~$ ./mlvtomp4 M01_0001.MLV M01_0002.MLV

# Convert all the MLV files in the current directory
~$ ./mlvtomp4 *.MLV
```

The associated MP4 files will be placed next to the existing MLV file after the conversion process has completed.

### User-defined Variables

`FRAMERATE`: The framerate at which the MP4 should play at. Default is 24.
`FRAMESIZE`: The framesize of the resulting MP4 video. Default is 1824x684. **It is recommended you change this to the appropriate size as recorded by the camera.**

### Advanced Users

If you have any specific mlv_dump, dcraw, or ffmpeg options, simply edit the script and its command invocations to include your options.
