# Project plan and reproducibility checklist

This repository is currently a documentation foundation. The checklist below is a roadmap, not a statement that these implementation tasks are complete.

## Establish provenance and environment

- [ ] Add the internship source/notebook that was actually used, with origin and revision.
- [ ] Record upstream SFA3D commit, modifications, and attribution.
- [ ] Confirm Python, PyTorch, torchvision, OpenCV, NumPy, CUDA, and GPU versions from the working environment.
- [ ] Record checkpoint origin, filename, checksum, and usage terms.
- [ ] Document KITTI subset, split, sequence IDs, access requirements, and local directory layout.

## Make the pipeline inspectable

- [ ] Identify actual entry points and supported arguments.
- [ ] Document point-cloud schema, coordinate frames, units, filtering, and BEV parameters.
- [ ] Document calibration matrix conventions and projection behavior.
- [ ] Add tests for transforms, BEV encoding, detection decoding, and output writing where applicable.
- [ ] Include small synthetic or redistribution-cleared fixtures; do not add restricted dataset data.
- [ ] Add representative output images/video only when they are actual outputs and publishing rights are clear.

## Reproduce results

- [ ] Record experiment code revision and exact command/configuration.
- [ ] Record GPU, CPU, RAM, driver, CUDA, and software versions.
- [ ] Define FPS timing boundaries, warm-up, sequence, and aggregation; repeat the GTX 1080 Ti result before presenting it as reproduced.
- [ ] Define the localization metric, baseline, evaluation split, sample count, and calculation before validating the 30% claim.
- [ ] Report failure cases, especially sparse/distant and occluded objects.

## Release responsibly

- [ ] Review KITTI, checkpoint, dependency, and third-party code terms.
- [ ] Choose a license for original code only after checking incorporated material and permissions.
- [ ] Add tested setup and run instructions for local and Colab environments.
- [ ] Add automated tests/CI that do not download restricted datasets or large checkpoints.
- [ ] Keep datasets, credentials, private captures, model weights, and generated outputs outside Git unless authorized.
