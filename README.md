# Tiered Storage Simulator

This repository simulates fetching data from a distributed storage system with hot, warm, and cold layers.

![image](https://github.com/easierdata/tiered-storage-simulator/assets/9572232/6914b60f-4ae3-46c2-927e-7bd054e23331)


## Installation

Clone the repository:

```bash
git clone git@github.com:easierdata/tiered-storage-simulator.git
```

Navigate into the project directory:

```bash
cd tiered-storage-simulator
```

Set up a virtual environment:

```shell
cd tiered-storage-simulator
# Install the tkinter version of python3 with brew
brew install python-tk@3.11
python3 -m venv .venv
source venv/bin/activate
```

Install dependencies:

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

## Usage

### tieredStorageSimulation.py

This script fetches data from a simulated distributed storage system with hot, warm, and cold layers.

It can run in two modes:

- Standalone - Runs the simulation logic without a GUI
- Tinker GUI - Renders an interactive GUI for visualizing the simulation

To switch between modes, set the `IN_GUI_MODE` variable to `True` or `False`.

The cold storage system is simulated using a Flask web server defined in `flask_web_server.py`. This runs in a separate thread to mimic requests to the storage provider API.

In order to use the S3 integration, rename `sample.env` to `.env` and fill in the environment variables with your AWS credentials.

