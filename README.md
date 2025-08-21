# ORB\_SLAM3\_Windows (Modified)

Windows version of ORB-SLAM3 with some updates and simplified setup.
Original project: [UZ-SLAMLab/ORB\_SLAM3](https://github.com/UZ-SLAMLab/ORB_SLAM3) (GPLv3 license).

Tested on **Windows 10/11 Pro** with **Visual Studio 2022** (2019+ works).

---

## 🔹 Quick Setup (Windows)

1. Install **Visual Studio 2022** (or 2019).
2. Install **Git** if you don’t already have it.
3. Open a terminal (Admin):

   * Windows 11 → `Windows key + X → Terminal (Admin)`
   * Windows 10 → `Windows key + X → PowerShell (Admin)`
4. Clone the repository:

   ```sh
   git clone https://github.com/rexdsp/ORB_SLAM3_Windows
   ```
5. Open the solution file:

   ```
   ORB_SLAM3_Windows/slam.sln
   ```
6. In Visual Studio, switch build mode from **Debug** → **Release**.
7. Build the project (**Ctrl+Shift+B**).
8. Download the vocabulary file [`ORBvoc.txt`](https://github.com/UZ-SLAMLab/ORB_SLAM3/blob/master/Vocabulary/ORBvoc.txt) and place it in:

   ```
   ORB_SLAM3_Windows/Vocabulary/
   ```

✅ That’s it — ORB-SLAM3 for Windows is ready to run.

---

## 🔹 Changes in This Fork

Compared to the original ORB-SLAM3 Windows port, this fork includes:

* Added **`mono_video.cpp`** example to support camera or video input.
* Updated **`main.cpp`** for easier execution.
* Default setup so users just **clone → choose Release → build** (no manual file moves needed).
* Simplified instructions for Windows 10/11 with **Visual Studio 2022**.

---

## 🔹 Mono Video Usage

Run from the `ORB_SLAM3_Windows` directory after building:

### 1. Use a webcam (index 0) with calibration `TUM1.yaml`

```powershell
.\x64\Release\slam.exe mono_video C:\ORB_SLAM3_Windows\Vocabulary\ORBvoc.txt C:\ORB_SLAM3_Windows\Examples\Monocular\TUM1.yaml 0
```

### 2. Use a video file (`video.mp4`) with calibration `TUM1.yaml`

```powershell
.\x64\Release\slam.exe mono_video C:\ORB_SLAM3_Windows\Vocabulary\ORBvoc.txt C:\ORB_SLAM3_Windows\Examples\Monocular\TUM1.yaml "C:\Users\W10\Desktop\video.mp4"
```

---

## 🔹 Program Arguments

General usage:

```
slam.exe testName testArguments
```

Supports **monocular, stereo, RGB-D, and visual-inertial** modes.
(See the [original ORB-SLAM3 documentation](https://github.com/UZ-SLAMLab/ORB_SLAM3) for detailed usage and datasets.)

---

## 🔹 Notes

* Eigen version: **3.3.7**
* OpenCV version: **3.2.0** (DLLs included in `./x64/Debug`)
* Vocabulary can be loaded in **text or binary mode** (`global.h` → `USE_BINARY_VOC`)
* Several cross-platform modifications (`_WINDOWS` defines)

---

## 🔹 License

This repository follows the original [GPLv3 license](https://github.com/UZ-SLAMLab/ORB_SLAM3/blob/master/License.md).

Original authors:
Carlos Campos, Richard Elvira, Juan J. Gómez Rodríguez, José M. M. Montiel, Juan D. Tardós.

If you use ORB-SLAM3 in academic work, please cite:

```bibtex
@article{ORBSLAM3_2020,
  title={{ORB-SLAM3}: An Accurate Open-Source Library for Visual, Visual-Inertial 
           and Multi-Map {SLAM}},
  author={Campos, Carlos AND Elvira, Richard AND Gómez, Juan J. AND Montiel, 
          José M. M. AND Tardós, Juan D.},
  journal={arXiv preprint arXiv:2007.11898},
  year={2020}
}
```


Do you also want me to add a **“Screenshots / Example Output”** section so people can see what it looks like when running `mono_video`?
