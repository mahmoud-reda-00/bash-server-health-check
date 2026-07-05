# Server Health Check

A Bash automation script that connects to multiple remote Linux servers over SSH and collects essential system health information. This project demonstrates Bash scripting best practices, including strict mode, argument parsing, logging, error handling, and automation.

## Features

* Connects to multiple servers via SSH
* Displays system uptime
* Checks root disk usage
* Reports memory usage
* Counts failed SSH login attempts
* Supports multiple servers from a configuration file
* Input validation and error handling
* Logging to both terminal and log file
* Automatic cleanup using `trap`
* Uses Bash Strict Mode (`set -euo pipefail`)

## Requirements

* Bash 4.0+
* SSH client
* Linux/Unix environment
* Access to the target servers via SSH

## Project Structure

```text
server-health-check/
├── server_health_check.sh
├── servers.txt.example
├── README.md
├── LICENSE
└── screenshots/
```

## Usage

Make the script executable:

```bash
chmod +x server_health_check.sh
```

Run the script:

```bash
./server_health_check.sh -f servers.txt -u <remote_user>
```

Example:

```bash
./server_health_check.sh -f servers.txt -u ubuntu
```

## Example Server List

```text
192.168.1.10
192.168.1.20
server.example.com
```

## Sample Output

```text
[INFO] Configuration valid. Starting health checks...
[INFO] Found 3 servers to check.

--- Checking Server: 192.168.1.10 ---

--- System Uptime ---
up 5 days, 4 hours

--- Disk Usage (Root /) ---
Used: 42% (8.3G/20G)

--- Memory Usage ---
Used: 835MB / Total: 1972MB (42.34%)

--- Security (SSH) ---
Failed SSH Attempts: 5

[INFO] All checks completed.
```

## Bash Concepts Demonstrated

* Functions
* Variables and constants
* Arrays
* Loops
* Conditional statements
* Argument parsing with `getopts`
* Here Documents
* SSH automation
* Logging
* Input validation
* Error handling
* `trap` and cleanup
* Bash Strict Mode (`set -euo pipefail`)

## Future Improvements

* Export results to CSV or JSON
* Parallel execution for faster checks
* CPU utilization monitoring
* Email notifications
* HTML health reports
* Support for custom health checks

## License

This project is licensed under the MIT License.
