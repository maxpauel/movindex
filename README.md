# movindex 
# Installation
# Usage
# Output
usage: movindex [-h] -i INPUT [-x X] [-y Y] [-wd WIDTH] [-ht HEIGHT]
                [-w WINDOW_SIZE] [-s STEP] [-p CORES] [-o OUTPUT_DIR]

Calculate movement indices from video frames with optional cropping

options:
  -h, --help            show this help message and exit
  -i INPUT, --input INPUT
                        Input video file path (default: None)
  -x X                  X coordinate of crop region top-left corner (default:
                        0)
  -y Y                  Y coordinate of crop region top-left corner (default:
                        0)
  -wd WIDTH, --width WIDTH
                        Width of crop region (default: full width) (default:
                        None)
  -ht HEIGHT, --height HEIGHT
                        Height of crop region (default: full height) (default:
                        None)
  -w WINDOW_SIZE, --window_size WINDOW_SIZE
                        Sliding window size for SD calculation (default: 7)
  -s STEP, --step STEP  Step size between windows (default: 7)
  -p CORES, --cores CORES
                        Number of CPU cores to use (default: all available)
                        (default: None)
  -o OUTPUT_DIR, --output_dir OUTPUT_DIR
                        Output directory (default: same as input video)
                        (default: None)

