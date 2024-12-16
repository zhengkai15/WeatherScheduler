# WeatherScheduler
This repository contains scripts and utilities to automate forecast-related tasks. The execution is designed to run without `crontab`, using a simple loop to ensure the script executes twice daily at `UTC 00:00` and `UTC 12:00`.

## Repository Structure
```text
.
├── README.md            # Documentation
└── forecast
    ├── autorun.sh           # Script for running the automation loop
    ├── env.yml              # Conda environment configuration
    ├── main.py              # Main script to process forecasts
    ├── requirements.txt     # Python dependencies
    ├── synctooss.py        # Script for submitting results to OSS
    └── util.py              # Utility functions
```
## Setting Up the Environment

### 1. Install Conda Environment
```bash
conda env create -f forecast/env.yml
conda activate forecast-env
```
2. Install Python Dependencies
```bash
pip install -r forecast/requirements.txt
```
## Usage

Run Automation Script

The autorun.sh script ensures the tasks are executed at UTC 00:00 and UTC 12:00. You can start the script as follows:
```bash
bash forecast/autorun.sh
bash forecast/autorun.sh > forecast/logs/autorun.log 2>&1 &
```

Notes

	•	Ensure the system’s timezone is set to UTC or adjust autorun.sh accordingly.
	•	Logs are printed to the terminal for debugging. To redirect logs to a file:

