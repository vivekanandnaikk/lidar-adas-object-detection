# Project plan

This repository is an initial project foundation. Use this checklist to turn the described project into a working, reviewable, reproducible implementation without implying that unverified capabilities are already complete.

## 1. Define the experiment

- [ ] Select the LiDAR sensor or dataset and document its license and access instructions.
- [ ] Identify available camera data and calibration files if RGB projection is required.
- [ ] Specify coordinate frames, axis conventions, units, point fields, and timestamp handling.
- [ ] Choose the detection approach and record its citation, version, configuration, and checkpoint source.
- [ ] Define the target platform and what “real-time” means (frame rate or latency, and measurement scope).
- [ ] Define the localization metric, baseline, and exact method behind the reported 30% improvement.

## 2. Implement in small, testable stages

1. Add data loading and validation with a small, redistributable or synthetic fixture.
2. Add preprocessing with documented parameters and unit tests.
3. Add detector integration and a reproducible inference entry point.
4. Add coordinate transforms and detection output schema.
5. Add BEV visualization and tests for geometry/coordinate conventions.
6. Add calibrated RGB projection visualization where corresponding camera images and calibration are available.
7. Add evaluation scripts and benchmark metadata; do not silently compare incompatible splits or metrics.

## 3. Suggested layout as code is added

```text
src/lidar_adas/       reusable pipeline modules
configs/              versioned experiment settings
scripts/               explicit command-line entry points
tests/                 unit and integration tests
examples/              small, redistributable examples
outputs/               local generated results (ignored by Git)
docs/                  design, data, and benchmark documentation
```

Keep large datasets, model weights, captured sensor recordings, and generated outputs outside ordinary Git history unless their licensing, size, and distribution are explicitly addressed. Add data acquisition instructions instead of uploading material without permission.

## 4. Benchmark evidence for the 30% claim

Before presenting the reported improvement as a verified result, publish:

- Baseline method and exact metric definition/formula.
- Dataset, sequences, split, sample count, and any filtering.
- Baseline and proposed-system results under identical conditions.
- Hardware, software versions, configurations, and commands to reproduce.
- Aggregation method and relevant limitations or failure cases.

If the original experiment details are unavailable, rerun the comparison and label the new results clearly; do not invent missing methodology.

## 5. Release readiness

- [ ] Add install/run instructions that work from a clean environment.
- [ ] Add tests and automated checks appropriate to the actual implementation.
- [ ] Document known limitations and supported data formats.
- [ ] Choose a license before inviting reuse.
- [ ] Verify that example data, images, model weights, and dependencies can legally be distributed.
