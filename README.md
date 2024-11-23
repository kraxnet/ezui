# Raspberry Pi Image Builder with Node-RED and Dashboard

This repository automates the creation of a custom Raspberry Pi image pre-installed with [Node-RED](https://nodered.org/) and its Dashboard. Using GitHub Actions, the image is built with [pi-gen](https://github.com/RPi-Distro/pi-gen) and deployed as downloadable releases.

## Features

- Automated image building and release using [pi-gen-action](https://github.com/usimd/pi-gen-action).
- Pre-installed [Node-RED](https://nodered.org/) and [Node-RED Dashboard](https://flows.nodered.org/node/node-red-dashboard).
- Configured to work out-of-the-box for Raspberry Pi devices.

## Getting Started

### Download the Image

Head to the [Releases](https://github.com/kraxnet/ezui/releases) section to download the latest Raspberry Pi image. Flash it to your SD card using a tool like [Raspberry Pi Imager](https://www.raspberrypi.com/software/) or [Balena Etcher](https://www.balena.io/etcher/).

### Prerequisites

- A Raspberry Pi
- A microSD card (8 GB or larger recommended).
- Optional: Ethernet or Wi-Fi setup if network connectivity is required.

### Flashing the Image

1. Download the `.img` file from the [Releases](https://github.com/kraxnet/ezui/releases) section.
2. Use [Raspberry Pi Imager](https://www.raspberrypi.com/software/) or [Balena Etcher](https://www.balena.io/etcher/) to flash the image to your microSD card.
3. Insert the microSD card into your Raspberry Pi and power it on.

### Accessing Node-RED

1. Open a web browser and navigate to `http://<your-pi-ip>:1880`.
2. Customize and deploy your flows using the built-in Node-RED editor.
3. Use the Node-RED Dashboard at `http://<your-pi-ip>:1880/ui` to interact with your projects.

## How It Works

### GitHub Actions

This project uses [pi-gen-action](https://github.com/usimd/pi-gen-action) to automate the build process. Upon every push to the `main` branch or when manually triggered, GitHub Actions:

1. Clones the [pi-gen](https://github.com/RPi-Distro/pi-gen) repository.
2. Applies customizations for Node-RED and the Dashboard.
3. Builds the Raspberry Pi image.
4. Uploads the image as a release artifact.

### Directory Structure

- `stage-ezui`: Contains customization scripts and configuration for Node-RED.
- `.github/workflows`: Defines the GitHub Actions workflows.

## Development and Customization

### Modifying Node-RED Configuration

To customize the Node-RED environment:

1. Update the files in the `stage-ezui` directory.
2. Push changes to the repository. The new image will be built and released automatically.

### Testing Locally

You can build the image locally using `pi-gen`. Refer to the [pi-gen documentation](https://github.com/RPi-Distro/pi-gen) for setup instructions.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request to suggest changes or enhancements.

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgments

- [pi-gen](https://github.com/RPi-Distro/pi-gen) - The official Raspberry Pi image builder.
- [pi-gen-action](https://github.com/davestephens/pi-gen-action) - GitHub Action for pi-gen.
- [Node-RED](https://nodered.org/) - Low-code programming for event-driven applications.

---

Make sure to replace placeholders like `your-username` and `your-repo-name` with the appropriate values from your project. Let me know if you need further adjustments!

