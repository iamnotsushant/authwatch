# AuthWatch — Security Log Dashboard

AuthWatch is a browser-based SSH authentication log explorer. It parses a supported subset of OpenSSH `sshd` authentication records, summarizes successful and failed attempts, and highlights source IPs whose failure count reaches a configurable review threshold.

## Try it

Open `index.html` in a modern browser, or publish this folder with GitHub Pages. The page loads a synthetic sample automatically. Use **Analyze a log** to choose a local `.log` or `.txt` file (up to 5 MB).

No server, package installation, or third-party library is needed. The selected file is read and processed in the browser tab; it is not sent to a server. For safety, start with the included sample rather than sensitive production logs.

## Features

- Counts recognized successful and failed SSH login events.
- Charts the most frequent source IPs with failed attempts.
- Lets the user set a 2, 3, 5, or 10 failure review threshold.
- Filters and searches event rows, with pagination for larger files.
- Reports lines that do not match the supported record pattern.
- Uses synthetic sample records and documentation-only IPv4 ranges.

## Supported records

The parser currently recognizes common OpenSSH messages such as:

```text
Oct 13 08:41:02 host sshd[2411]: Failed password for invalid user admin from 192.0.2.44 port 51001 ssh2
Oct 13 08:42:02 host sshd[2501]: Accepted publickey for deploy from 198.51.100.23 port 44120 ssh2
```

## Limitations and safe use

This is an educational dashboard, not an intrusion detection system. It supports a narrow SSH log format and IPv4 addresses; it does not parse every operating-system or OpenSSH variation, correlate activity across time, geolocate addresses, or prove malicious intent. Repeated failures are a reason to investigate, not proof of an attack. Analyze only logs you are authorized to access, and follow your organization's privacy and retention rules.

## Skills demonstrated

JavaScript parsing and aggregation, client-side file handling, accessible interactive UI, filtering and pagination, data visualization, and privacy-conscious design.
