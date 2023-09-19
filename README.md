# Cyber_Defense
This repository houses a curated collection of scripts designed for proactive, detective, and defensive measures on Windows systems. These scripts aim to identify, mitigate, and protect against potential vulnerabilities and misconfigurations.


# Windows Service Path Vulnerability Checker
This PowerShell script identifies Windows services that are potentially vulnerable due to unquoted service paths containing spaces. If an attacker has write permissions to one of the directories in the path before the executable, it might be possible for them to exploit this vulnerability.

## Background
Windows services are integral components of the Windows operating system. They run in the background and provide various functionalities to the system. Each service has a path to its executable, specified in the PathName property. If this path is unquoted and contains spaces, it might be vulnerable to hijacking. An attacker with write permissions to one of the directories in the path (before the actual executable) could potentially place a malicious executable in that directory, which would be run the next time the service starts.

## Features
Identifies services with unquoted PathName properties that contain spaces.
Checks each directory in the path of the service's executable for write permissions.
Generates a "VulnerableServices.txt" file on the desktop if any vulnerabilities are found.
Displays a warning message to the user if vulnerabilities are detected.

## Usage
Open PowerShell with administrative privileges.
Navigate to the directory containing the script.
Run the script: .\script_name.ps1
If any vulnerable services are found, a warning message will be displayed, and a "VulnerableServices.txt" file will be generated on the desktop.

## Caution
This script is intended for educational and defensive purposes only. Always have backups and understand the implications before running scripts, especially in production environments.

## Contribution
Contributions are welcome! If you find any issues or have suggestions, please open an issue or submit a pull request.
