# Tiered Storage Simulator

This repository simulates fetching data from a distributed storage system with hot, warm, and cold layers.

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

### cacheHitSimulations.py

This script runs simulations to analyze cache hit rates under different configurations.

It varies:

- Number of scenes requested per request
- Cache expiration time

For each combination, it simulates cache requests and counts the number of "cold storage hits". This represents when a request cannot be served from cache and must fetch from cold storage.

The hit rate is calculated as:

```
cold_storage_hits / number_of_requests
```

Results are saved to `results.csv` including:

- Number of requests
- Cache expiration
- Scenes per request
- Cold storage hits
- Hit rate

Rows are sorted by highest to lowest hit rate.

This allows analyzing which factors increase the cache hit rate and reduce trips to slow cold storage.
