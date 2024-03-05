# multi-radar-dataset

Multi-radar dataset is an open-source mmWave human activity dataset collected from various domains (i.e. radar kinds, environments and users), and it can be used to Investigate the influence of device configurations and data
representation on mmWave radar. Following we introduce the composition and implementation details of this dataset.

# Dataset Introduction

![Action of Liedownup](/liedown_camera.jpg)

- **11 volunteers**: 11 users with different sex, ages, heights and weights.
- **2 distances**: 1m, 2m
- **8 kinds of activities**: tanding, sitting, Squatting, sitting down, turning a chair, bowing, waving hands, squatting, and lying down
- **352k frames**: approximately 586 minutes action data


# Dataset Implementation

## Hardware Configuration

- This dataset is collected by TI AWR1843 mmWave radar, IMAGEVK-74 radar and Zed 2i camera.

![Devices](/devices.jpg)

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


