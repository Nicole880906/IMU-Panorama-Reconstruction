# ECE276: Robust Orientation Tracking and Panorama Reconstruction

This project estimates camera orientation from IMU data (accelerometer + gyroscope) and uses the estimated rotations to generate high-resolution panoramas. The pipeline integrates gyroscope measurements with a quaternion motion model, then refines orientation via an optimization objective that reduces integration drift and aligns the gravity direction, producing a seamless equirectangular panorama.

---

## Features
- **IMU Calibration**: Bias and scale adjustment for raw sensor data.
- **Motion Model**: Quaternion-based gyroscope integration.
- **Optimization**: Combined motion and observation (gravity) loss to minimize drift.
- **Quaternion Normalization**: Projection to the unit sphere for valid rotations.
- **Panorama Reconstruction**: Generation of seamless equirectangular images.
- **Ground Truth Validation**: Comparison with Vicon motion capture data (trainset).

---

## File Structure

```text
ECE276/
├── main.py                # Primary script for data processing, optimization, and stitching
├── README.md              # Project documentation
└── data/                  # Data directory
    ├── trainset/          # Training data (IMU, Camera images, and Vicon ground truth)
    └── testset/           # Testing data (IMU and Camera images)
```
---

## Requirements
* Python 3.8+
* torch
* numpy
* matplotlib

---

## Getting start
1 Create and activate a virtual environment
From the ECE276/ directory:
```text
python3 -m venv venv
source venv/bin/activate
```

2 Install dependencies
```text
pip install torch numpy matplotlib
```

3 Run the program
```text
python3 main.py
```

output
The script will typically:
* Plot IMU signals (accelerometer and gyroscope)
* Plot estimated Euler angles vs. ground truth (if available)
* Render panoramas for both estimation and ground truth (trainset)

---
*Developed as part of ECE 276A: Sensing and Estimation Robotics at UC San Diego.*