# Football Game Insight Artefact

This project provides a pipeline for downloading and processing the **SoccerNet Tracking** dataset for use in object detection and multi-object tracking tasks. It leverages **YOLO** (via `ultralytics`) and **DeepSORT** for player and ball tracking.

---
## Screenshots
<img alt="image" src="https://github.com/user-attachments/assets/00f8b59c-e348-415b-9d3a-3ad5908f4570" />

## Features

* Automated download of **SoccerNet-Tracking** dataset
* Example setup for video processing
* Ready-to-use environment with dependencies installed
* Extensible for research in player detection, re-identification, and event analysis

---

## Requirements

The project uses Python 3 and requires the following dependencies:

```bash
SoccerNet opencv-python ultralytics scikit-learn deep-sort-realtime numpy
```

---

## Dataset Setup

1. **Download the SoccerNet dataset:**

   ```python
   from SoccerNet.Downloader import SoccerNetDownloader

   mySoccerNetDownloader = SoccerNetDownloader(
       LocalDirectory="/path/to/your/dataset"
   )
   mySoccerNetDownloader.password = "<your_password_here>"
   mySoccerNetDownloader.downloadRAWVideo(dataset="SoccerNet-Tracking")
   ```

   ⚠️ Downloading the dataset may take several hours. File size is approximately **80GB**. 

2. **Extract the archive** once the download completes.

3. Update the `video_path` in your notebook to point to one of the extracted videos:

   * Each video from the dataset represents **one half of a match**.

---

## Usage

1. Open the `cw.ipynb` notebook in Jupyter or Google Colab.
2. Run the installation cell to set up dependencies.
3. Run the dataset download cell (or manually place videos in your dataset folder).
4. Update `video_path` and processing parameters as needed:

   * **`TARGET_FRAME_COUNT`**: number of frames to generate (fps × seconds).
   * **`skip_seconds`**: how many seconds to skip from the start of the video.
5. Run the main video processing cell where `process_video()` is called
---

## Notes

* Ensure you have enough disk space (≥100GB recommended).
* GPU acceleration is highly recommended for video processing.
* The dataset requires authentication to download (fill in the NDA form on the [SoccerNet website](https://silviogiancola.github.io/SoccerNetv2/)).

---

## Author

* Mark Ssenoga

---

