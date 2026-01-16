# bat-flight-trajectory-data

This repository contains data for gray bats (*Myotis grisescens*) during collective emergence flights.

## Data File

**bat_tracking_data.csv** - Processed 2D bat trajectories in tidy format (frame | bat_id | x | y)

| Column   | Description                        |
|----------|------------------------------------|
| `frame`  | Frame number (dt = 1/60 s)         |
| `bat_id` | Unique bat identifier (1-34)       |
| `x`      | X coordinate (meters)              |
| `y`      | Y coordinate (meters)              |

## Data Collection

Data were collected in August-September 2022 at Moore Street bridge, Bristol, VA, USA, which shelters a large colony (~10,000 individuals) of gray bats. A synchronized multi-sensor array of four infrared-modified GoPro Hero3+ cameras (60 fps, 1080p) was installed along the bridge railing. Infrared illumination allowed high-contrast imaging without disturbing the bats.

## Data Processing

1. **3D Reconstruction:** Trajectories were reconstructed from synchronized multi-camera recordings using Direct Linear Transformation (DLT), yielding continuous x-y-z positional data for each individual.

2. **Occlusion Handling:** Brief occlusions (when bats left the calibrated volume or were visually obstructed) were identified by visual inspection and filled by linear interpolation over bat-specific frame ranges.

3. **Smoothing:** Position time series were smoothed using a 3-frame moving-average filter to reduce high-frequency digitization noise.

4. **2D Projection:** Positions were projected to 2D (x, y) for the analyses presented here.

