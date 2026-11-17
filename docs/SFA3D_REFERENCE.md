# SFA3D reference and execution notes

This document records what was checked in upstream [maudzung/SFA3D](https://github.com/maudzung/SFA3D) while preparing the project README. It is not a claim that upstream files or dependencies are installed in this repository.

## Upstream architecture

The upstream README describes SFA3D as an anchor-free LiDAR 3D detector without NMS. Its technical notes describe a ResNet-based Keypoint Feature Pyramid Network inspired by RTM3D. The model input is a BEV map with height, intensity, and density channels. Outputs include a center heatmap, center offsets, yaw components, dimensions, and vertical position. The upstream KITTI setup covers cars, pedestrians, and cyclists.

The upstream dependency file pins an older stack: `torch==1.5.0`, `torchvision==0.6.0`, `easydict==1.9`, `opencv-python==4.2.0.34`, `numpy==1.18.3`, `torchsummary==1.5.1`, `tensorboard==2.2.1`, `scikit-learn==0.22.2`, `wget==3.2`, `tqdm==4.54.0`, and `matplotlib==3.3.3`. These are upstream pins, not a validated requirements file for this repository. Compatibility depends on Python, CUDA, and platform; verify in an isolated environment before use.

## Upstream entry points verified

- `sfa/demo_front.py`: loads a configured checkpoint, runs front-view detection, draws BEV predictions, projects detections using KITTI calibration, combines camera/BEV imagery, and writes an MJPG AVI.
- `sfa/demo_2_sides.py`: runs front and back BEV detections, joins those BEV views, projects front detections onto the RGB image, and writes an MJPG AVI.
- `sfa/test.py`: upstream inference entry point documented by the upstream README.
- `sfa/train.py`: upstream training entry point documented by the upstream README.

The commands below are taken from the upstream README and are intended only after cloning that project and following its data/checkpoint setup. Run `--help` and inspect the upstream config for current path expectations.

```bash
# From the root of the upstream SFA3D checkout:
python sfa/demo_2_sides.py --gpu_idx 0 --peak_thresh 0.2
python sfa/demo_front.py --gpu_idx 0 --peak_thresh 0.2
python sfa/test.py --gpu_idx 0 --peak_thresh 0.2
```

The upstream README says the two-side demo data is downloaded by the demo command, while the script asserts that the configured pretrained checkpoint exists. For KITTI training/evaluation data, use the official KITTI source and upstream directory conventions; do not upload dataset archives here.

## Attribution and license

SFA3D is by Nguyen Mau Dung. The upstream repository declares MIT License (copyright 2020). If this project later includes copied or modified upstream code, preserve the upstream license/copyright notice and identify modifications. The MIT status of upstream code does not cover KITTI content, checkpoints from other sources, or this repository's original files. Review each component's terms separately.

## References

- [SFA3D repository](https://github.com/maudzung/SFA3D)
- [SFA3D technical notes](https://github.com/maudzung/SFA3D/blob/master/Technical_details.md)
- [SFA3D upstream dependency pins](https://github.com/maudzung/SFA3D/blob/master/requirements.txt)
- [KITTI 3D object detection benchmark](https://www.cvlibs.net/datasets/kitti/eval_object.php?obj_benchmark=3d)
