# pkg-camx-firmware-hamoa

This repository has debian packaging rules and scripts for [prebuilt CamX camera framework binaries](https://qartifactory-edge.qualcomm.com/ui/native/qsc_releases/software/chip/component/camx.qclinux.0.0/) for the Hamoa platform.

## Branches

- **qli-ci**: The primary branch containing workflow logic in the `.github/` folder, along with boilerplate documentation files such as license, contribution guidelines, and this README.
- **qcom/ubuntu/resolute**: This branch contains camx-hamoa debian packaging rules and scripts for Ubuntu 26.04 (Resolute Raccoon).
- **qcom/debian/trixie**: This branch contains camx-hamoa debian packaging rules and scripts for Debian Trixie.

## Typical Workflows

1. **Promote New Prebuilt Binary Version**: When new prebuilt binaries are available, the promote workflow updates `upstream.conf` in the packaging branch and opens a PR.
2. **PR Validation**: PRs in this repo are validated against the package build to catch breakages early.
3. **Build Debian Package**: Once PRs get merged, the build debian package workflow builds debian packages for the corresponding packaging branch.
4. **Release Version**: A manual dispatch finalizes the changelog, builds the package, uploads artifacts to S3, and notifies [qcom-distro-images](https://github.com/qualcomm-linux/qcom-distro-images).

## Development

Refer to the [CONTRIBUTING.md](CONTRIBUTING.md) file for guidelines on contributing to this project.

## Usage

**Build**: To build the package, go to the *Actions* tab, select the *Build Debian Package* workflow, then click 'Run workflow'.

**Upstream Version Promotion**: To promote a new upstream version, update `upstream.conf` with the new `TAG` and `PACKAGE_NAME`, then open a PR against the packaging branch.

The workflows of this repo use the reusable workflows from qcom-build-utils in the background. To understand more about how everything connects together, see https://github.com/qualcomm-linux/qcom-build-utils

## Installation Instructions

1. Install the camera hamoa firmware package:
    - `sudo dpkg -i camx-firmware-hamoa_<version>_arm64.deb`

## Getting in Contact

* [Report an Issue on GitHub](../../issues)
* [Open a Discussion on GitHub](../../discussions)
* [E-mail us](mailto:camera.deb.maintainers@qti.qualcomm.com) for general questions

## License

pkg-camx-firmware-hamoa is licensed under the [BSD-3-Clause license](https://spdx.org/licenses/BSD-3-Clause.html). See [LICENSE.txt](LICENSE.txt) for the full license text.
