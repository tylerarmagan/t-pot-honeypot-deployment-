# Security Policy

## Project Scope

This repository is a portfolio record of a completed T-Pot honeypot deployment and contains documentation and sanitized evidence only. It does not distribute T-Pot, operate a production service, or provide a supported software package.

Only the current `main` branch is considered the maintained version of this documentation.

## Reporting a Repository Security Issue

If you discover exposed credentials, access tokens, private keys, personal information, an active infrastructure address, or another sensitive item in this repository, please do not disclose it in a public issue.

Use GitHub's private vulnerability-reporting option on the repository's **Security** tab when available. Otherwise, contact the repository owner privately through the GitHub profile associated with this project. Include:

- The affected file or screenshot
- A concise description of the exposure
- Any recommended redaction or remediation

Reports concerning vulnerabilities in T-Pot itself should be submitted to the official T-Pot project through its published security-reporting process.

## Sensitive Data Handling

The repository intentionally excludes:

- Cloud-provider API tokens and account details
- SSH private keys and authentication material
- Passwords and administrative credentials
- Environment files and local configuration
- Raw packet captures, logs, and exported telemetry
- Unredacted personal or active infrastructure information

The included `.gitignore` provides additional protection against accidentally committing common secret, log, capture, and environment files. It does not replace reviewing every file and screenshot before publication.

## Responsible Use

This material documents defensive research conducted on infrastructure controlled by the repository owner. Honeypots should be isolated, monitored, and operated only with proper authorization and in accordance with provider terms and applicable law.
