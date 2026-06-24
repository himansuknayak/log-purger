# Log Purger Utility (`log-purger.py`)

log-purger.py automates the deletion of historic log files to prevent disk space exhaustion.

## Prerequisite

- **Python** version 3.8 or higher is required.

  > [!WARNING]
  > Running this script Python version lower than 3.8 will cause runtime execution failure.
  > **Dependencies:** Install the required `requests` and `psutil`libraries before execution.

```
bash
pip install requests psutil
```

## Execution and Usage

Execute the script from the terminal using the following command

```
bash
python log-purger.py --dir /var/log --days 30
```

## Command-Line Argument

| Argument | Type    | Description                                                         |
| -------- | ------- | ------------------------------------------------------------------- |
| `--dir`  | string  | Specifies the absolute target directory where log files are stored. |
| `--days` | integer | Any log older than the specific number of days will be deleted.     |

> [!CAUTION]
> File deletion is immediate and permanent. There is no recovery mechanism once execution completes.

## Server Response

### Success Response (200 OK)

Upon successful execution, following JSON output is expected.

```json
{"status": "success", "files_deleted": 14, "space_saved_mb": 42.5}
```
### Error Response (400 Not Found)

Passing an invalid or unreachable directory will trigger a termination error. 

```json
{"status": "error", "message": "Directory not found"}
```


