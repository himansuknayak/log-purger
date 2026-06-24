# log-purger.py

## Project Overview

log-purger.py is used to clean up old log files from the server to maintain the disk space.

## Usage Guide

To run this script, python 3.8 or above is required.

> [!WARNING]
> Using older version earlier than 3.8 will crash the server

## Installation Guide

To run this, install `requests` and `psutil` libraries

```
pip install requests psutil
```

```
import requests
import psutil
```

## Running the Script

To run the script, type the following command on terminal.

```
python log-purger.py --dir /var/log --days 30
```

The `--dir` is the target directory where the logs are stored, and `--days` is the threshold (like, any logs older than that number of days get deleted permanently).

It returns the following JSON output

```
{"status": "success", "files_deleted": 14, "space_saved_mb": 42.5}
```

Wrong directory path will throw following error.

```
{"status": "error", "message": "Directory not found"}
```

> [!WARNING]
> Script exceuted once can't be undone resulting the permanent deletion of the file.
