# mmwave device configuration data represention dataset (MM-DCDR Dataset)

MM-DCDR dataset is an open-source mmWave human activity dataset collected from various domains (i.e. radar kinds, environments and users), and it can be used to investigate the influence of device configurations and data
representation on mmWave radar. Following we introduce the composition and implementation details of this dataset.

# Dataset Introduction

![Action of Liedownup](/figure/liedown_camera.jpg)

- **11 volunteers**: 11 users with different sex, ages, heights and weights.
- **2 distances**: 1m, 2m
- **8 kinds of activities**: standing, sitting, sitting down, turning a chair, bowing, waving hands, squatting, and lying down
- **352k frames**: approximately 586 minutes action data


# Dataset Implementation

## Hardware Configuration

- This dataset is collected by TI AWR1843 mmWave radar, IMAGEVK-74 radar and Zed 2i camera.

![Devices](/figure/devices.jpg)

- The parameters of the radar are set as follows:

| Parameter | AWR 1843 | IMAGEVK-74 |
|----------|----------|----------|
| Modulation | FMCW |SFCW |
| Framerate | 10 Hz | 15 Hz |
| Start Frequency | 77.00 GHz | 63.00 GHz |
| Stop Frequency | 81.00 GHz | 67.00 GHz |
| Number of TX Antenna | 3 | 20 |
| Number of RX Antenna | 4 | 20 |
| Velocity Resolution | 1.27 m/s | - |
| Range Resolution | 3.75 cm | 3.75cm |
| Azimuth Angle Resolution | 15° | 6.7° |
| Elevation Angle Resolution | 57.3° | 6.7° |
| Sampling Points | 128 | 128 |
| Number of Chirps Per Frame | 128 | 1 |
| Duration of Each Chirp | 19.9 μs | - |

## Data preprocessing

### Heatmap

Taking the action of lying down as an example, the raw signals are processed through range-FFT and doppler-FFT to generate a range-Doppler heatmap (first row), and through Range-FFT and Angle-FFT to produce a Range-Angle heatmap (second row).

![rdfft_heatmap](/figure/rdfft_heatmap.jpg)
![rafft_heatmap](/figure/rafft_heatmap.jpg)

### Pointcloud
The raw signals are converted into a 3D point cloud using a two-dimensional Fourier Transform process that includes Range-FFT and Doppler-FFT, combined with CFAR detection and DOA estimation techniques. The point cloud produced by the AWR1843 radar encompasses five-dimensional features, which consist of the xyz spatial coordinates, Doppler velocity, and the intensity of the reflected signal. In contrast, the point cloud formed by the IMAGEVK-74 radar is characterized by four-dimensional attributes, which capture the xyz spatial coordinates along with the signal's reflectivity intensity.

![pcd sequence](/figure/lie_visualization_pcd.svg)

## How to access the dataset

To obtain the dataset, please sign the [agreement](/agreement.pdf), scan and send it to yatinggao557@gmail.com. You will receive a notification email which includes the download links of the dataset within two days.


## Citation

Please cite the following paper if this dataset is helpful to your research

```bibtex
@inproceedings{gao2024mm,
  title={MM-DCDR: A Benchmark of Device Configuration and Data Representation for mmWave-Based Human Sensing},
  author={Gao, Yating and Geng, Ruixu and Zhang, Dongheng and Hu, Yang and Lin, Hui and Chen, Yan},
  booktitle={2024 16th International Conference on Wireless Communications and Signal Processing (WCSP)},
  pages={801--806},
  year={2024},
  organization={IEEE}
}
```


