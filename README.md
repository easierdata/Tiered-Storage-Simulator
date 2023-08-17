# Tiered-Storage-Simulator

This repository contains code to fetch data stored in a distributed storage system with hot, warm, and cold layers.

## Installation

```shell
git clone git@github.com:easierdata/tiered-storage-simulator.git
cd tiered-storage-simulator
# Make sure you have installed Python 3 with Tkinter
brew install python3-tk
python3 -m venv venv
source venv/bin/activate
pip install -- upgrade pip && pip install -r requirements.txt
```

## Usage

tieredStorageSimulation.py - This file contains the code to fetch data from various storage systems with hot, warm, and cold layers. It can be run either as a standalone file or as a Tinker GUI. In order to switch between the two, change the value of IN_GUI_MODE to True or False. Because our storage provider has not yet given us an HTTP web server, a flask web server is used to simulate the storage provider. The flask web server is run in a separate thread by running flask_web_server.py.

cacheHitSimulations.py - This file contains the code to run simulations for various cache hit rates. Depending on the number of scenes requested and the cache lifetime, the 'cold storage hit rate' is calculated. The results are stored in a csv file called results.csv.
