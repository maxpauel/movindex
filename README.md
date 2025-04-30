# movindex
Video Movement Index Calculator
# Description
This program calculates two movement indices (IS1 and IS2) from video frames to quantify activity levels. It processes videos by:

- Optionally cropping to a specified region

- Extracting frames

- Calculating:

    IS1: Mean sliding window standard deviation (more sensitive to temporal variations)

    IS2: Standard deviation across all frames

- Generating visualizations including heatmaps and time series plots
# Dependencies
  Python 3.6+

  Required packages:

  - OpenCV (cv2)

  - NumPy

  - Pillow (PIL)

  - Matplotlib

  - tqdm (for progress bars)
# Installation
Linux
1. Install Python and pip

       sudo apt update   
       sudo apt install python3 python3-pip python3-venv

2. Install dependencies

       pip install opencv-python numpy pillow matplotlib tqdm

3. Download movindex file and make it executable

       chmod +x movindex

4. Install to system path (optional)

       sudo cp movindex /usr/local/bin/

 Windows
 1. Install Python

    Download Python 3.9+ from python.org

    Run installer

    Check "Add Python to PATH" during installation

 2. Open Command Prompt (Admin)
cmd

          python -m pip install --upgrade pip
          python -m venv video_analysis_env
          video_analysis_env\Scripts\activate

 3. Install dependencies
cmd

pip install opencv-python numpy pillow matplotlib tqdm
 
 4. Associate with Python (recommended for development)

    Right-click on movindex → Open With → Choose Python

    Check "Always use this app"

 5. Add to PATH (optional)

    Move movindex (or the .bat/.exe) to a folder like C:\Program Files\movindex\

    Add this folder to your system PATH


# Usage
Basic usage

      movindex -i input_video.mp4
Input video file in common formats (e.g., .avi, .mp4, .mov)

Options:

      -h, --help            show this help message and exit
      -i INPUT, --input INPUT
                        Input video file path
      -x X                  X coordinate of crop region top-left corner (default:0)
      -y Y                  Y coordinate of crop region top-left corner (default:0)
      -wd WIDTH, --width WIDTH
                        Width of crop region (default: full width) (default:None)
      -ht HEIGHT, --height HEIGHT
                        Height of crop region (default: full height) (default:None)
      -w WINDOW_SIZE, --window_size WINDOW_SIZE
                        Sliding window size for SD calculation (default: 7)
      -s STEP, --step STEP
                        Step size between windows (default: 7)
      -p CORES, --cores CORES
                        Number of CPU cores to use (default: all available)
      -o OUTPUT_DIR, --output_dir OUTPUT_DIR
                        Output directory (default: same as input video)

# Output Files

  - Numerical Results:

    results.txt: Appends movment index (IS1) values for all processed videos

    Console output shows both IS1 and IS2 values

- Visualizations:

  *_sd.tiff: SD heatmap (default colors)

  *_sd_alt.tiff: SD heatmap (alternate colors)

  *_sdsw.tiff: Sliding window SD heatmap

  *_max_sd_trace.tiff: Time series of most active pixel

    Intermediate Files:

  Frames directory with extracted TIFF images

  (Optional) Cropped video if cropping parameters were used
