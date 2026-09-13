# DevShield 

Developer Security Toolkit - Secret Leak Prevention + Config Comparison.

Catches secrets before you push, compares configs.

## Usage
```
devshield scan .
devshield diff config1.yml config2.yml
```


## Overview
DevShield is a Developer Security Toolkit that includes a Secret Scanner, Config Diff, and Git Hooks.

## Features
- 15+ secret patterns (AWS, GitHub, Stripe keys)
- Shannon entropy analysis
- Config comparison with security impact
- Pre-commit hooks
- Full audit mode

## Architecture
CLI -> RuleEngine -> SecretScanner/ConfigDiff -> Report Generator

## Tech Stack
Python, Click, Rich, GitPython, regex

## How It Works
Scans files against regex patterns and entropy thresholds, flags matches by severity (CRITICAL, HIGH, MEDIUM, LOW).

## Screenshots/Demo
`	ext
> devshield scan .
[CRITICAL] AWS Key found in config.py
[HIGH] High entropy string in utils.py
`

## Installation
`ash
pip install -e .
# OR
pip install devshield
`

## Project Structure
`	ext
devshield/
â”œâ”€â”€ cli.py
â”œâ”€â”€ secret_scanner.py
â”œâ”€â”€ config_diff.py
â”œâ”€â”€ git_hook.py
â”œâ”€â”€ rules.py
â””â”€â”€ utils.py
tests/
.devshield.example.yml
`

## Future Improvements/Roadmap
- CI/CD integration
- VS Code extension
- Custom rule builder
- SAST integration

## License
MIT