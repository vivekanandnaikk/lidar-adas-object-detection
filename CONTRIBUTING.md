# Contributing

Thanks for your interest in improving this project. The repository currently focuses on documentation and establishing implementation provenance; runnable project code and tests have not yet been added.

## Issues

- Search existing issues before opening a new one.
- For a bug, include the commit, environment, exact command, expected and actual behavior, and a small reproducible example where possible.
- Remove credentials and private or restricted sensor data from reports and attachments.
- For proposed features, describe the use case and how the change can be validated.

## Pull requests

- Keep changes focused and explain their purpose.
- Add/update tests and documentation when implementation changes.
- Identify code copied or adapted from SFA3D or other projects and preserve required notices.
- Do not commit KITTI data, private recordings, checkpoints, or other large assets without documented permission and maintainer approval.
- Support performance claims with reproducible commands, hardware/software details, and a documented baseline.
- Avoid describing roadmap items as implemented.

## Development environment

No project-specific dependency manifest or executable code is currently present. Do not assume the upstream SFA3D dependency pins will work in a current Python/CUDA environment. See [SFA3D reference notes](docs/SFA3D_REFERENCE.md) and validate a dedicated environment before contributing code.
