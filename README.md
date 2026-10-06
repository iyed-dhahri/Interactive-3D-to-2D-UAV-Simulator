# UAV Disaster Simulator

**An Interactive 3D-to-2D UAV Simulator for Controlled Disaster Data Generation and Analysis**

A browser-based simulator that flies a virtual drone over photogrammetric 3D tiles
of a real city, triggers a disaster (earthquake or flood) with controllable
intensity and extent, and captures georeferenced before/after nadir images with
exact per-building ground truth. The generated imagery is used to evaluate
building-damage and flood segmentation (SegFormer) and to study the
simulation-to-reality gap under controlled conditions.

## Overview

The pipeline connects, in a single framework:

1. **Real-world 3D scene** – Google Photorealistic 3D Tiles or extruded
   OpenStreetMap (OSM) buildings over a terrain model, rendered with CesiumJS.
2. **Disaster simulation** – an earthquake (rigid-block collapse) or a flood
   (rising water surface) is placed at the drone, with a controllable radius and
   per-building damage level.
3. **Drone acquisition** – nadir, north-up photos are captured before and after
   the event, aligned pixel-for-pixel and georeferenced (WGS84).
4. **Segmentation** – a SegFormer (MiT-B2) network, trained on real UAV imagery
   (RescueNet), labels intact buildings, damaged buildings and water.
5. **Post-processing** – superpixel smoothing and a robust flood-colour model
   refine the masks.
6. **Georeferenced maps** – predictions are projected back onto the source
   imagery.

## Features

- Interactive 3D city with drone piloting and a nadir camera.
- Controllable earthquake and flood scenarios (type, location, radius, severity).
- Automatic, exact per-building ground truth for every capture.
- Scalable, reproducible, controllable generation of UAV disaster data.
- Evaluation scripts for building-damage and flood segmentation.

## Repository structure

> To be populated.

```
.
├── README.md
├── simulator/      # browser-based 3D-to-2D disaster simulator (planned)
├── segmentation/   # SegFormer training / inference and post-processing (planned)
├── data/           # generated frames and ground truth (planned)
└── figures/        # paper figures (planned)
```

## Getting started

> Setup and run instructions will be added here.


## License

> Choose and add a license (e.g. MIT) in a `LICENSE` file.
