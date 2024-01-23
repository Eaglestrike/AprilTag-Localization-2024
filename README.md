# Apriltag Localization 2024

This repo houses the code for Eaglestrike's Apriltag Localization system running on a Raspberry Pi.


## Setup

The code should be set to run on reboot. This can be done through a cron job or a systemctl service.

### Cron job setup

This guide assumes that you are using crontab.
1. Open cron editor
```bash
sudo crontab -e
```
2. Add the following lines:
```bash
MAILTO=""
SHELL=/bin/bash
@reboot /usr/bin/python3 -u /path/to/Apriltag-Localization-2024/run.py >> /path/to/Apriltag-Localization-2024/logs.log 2>&1
```
Note the `-u` flag on the python command. This disables buffering on stdout, which will allow the program to properly redirect to the log file.

