# COLMAP-SLAM

COLMAP_SLAM is a Visual-SLAM based on pycolmap and is mainly intended for the development and testing of new SLAM features (deep-learning based tie points and matching, keyframe selection, global optimization, etc). For now, only the code for visual odometry has been released.

Feel free to join the project!

Key fratures:
* completly build on pycolmap, easy to install
* windowed bundle adjustement
* monocular camera supported
* stereo cameras supported
* build to deal with long sequences
* deep learning based features support


## Installation
For installing colmap-slam, we recommend using [uv](https://docs.astral.sh/uv/) for fast and reliable package management:

```bash
# Install uv if you haven't already
curl -LsSf https://astral.sh/uv/install.sh | sh

# Create and activate a virtual environment
uv venv --python 3.10
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

Then, you can install colmap-slam using uv:

```bash
uv pip install -e .
```

This command will install the package in editable mode, allowing you to modify the source code and see changes immediately without needing to reinstall. If you want to use colmap-slam as a non-editable library, you can also install it without the `-e` flag.

Install `pytorch` from https://pytorch.org/ to have GPU support.

## Running the code

```
python ./main.py -c ./config/config_euroc.yaml -a ./calibration/calibration_euroc.yaml -r ./calibration/camera_rig_euroc.yaml -w ./path/to/output/folder
```
In the working directory `raw_data` is expected a folder called `images` containing a folder for each camera, for instance `cam0` and `cam1`.

The full trajectory is stored in the output folder: `trajectory.txt` in world reference system or `images.txt` following COLMAP conventions.

### Reference

Morelli, L., Ioli, F., Beber, R., Menna, F., Remondino, F. and Vitti, A., 2023. COLMAP-SLAM: A FRAMEWORK FOR VISUAL ODOMETRY. The International Archives of the Photogrammetry, Remote Sensing and Spatial Information Sciences, 48, pp.317-324.