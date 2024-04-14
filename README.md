# subdomain-script :satellite:

<p align="center">
  <img src="bg.png">
</p>

This bash script is designed to quickly filter subdomains for wfuzz, optimizing the process of identifying viable targets by automatically filtering out subdomains with invalid status codes. This script simplifies the first steps in penetration testing and security assessment tasks.

## Features :sparkles:

- Automatically filters subdomains with invalid status codes.
- Interactive GUI prompts to set the target and protocol (HTTP/HTTPS) via Zenity.
- Uses `ffuf` (Fuzz Faster U Fool) for rapid fuzzing and filtering.
- Dynamically adjusts filters based on initial fuzzing results.

## Prerequisites :clipboard:

To use this script, you'll need the following:
- Bash shell (Unix/Linux environment)
- `zenity` for GUI input dialogs
- `ffuf` installed and available in your system path
- Access to `/usr/share/seclists/Discovery/DNS/subdomains-top1million-110000.txt` or a similar list of subdomains

## Installation :gear:

To install the script, follow these steps:

1. Clone the repository or download the 'subdomains' script.
2. Make the script executable and move it to a directory in your PATH for easy execution:
   ```bash
   chmod +x subdomains
   sudo cp subdomains /bin/subdomains
   ```

## Usage :computer:

To run the script, simply type `subdomains` in your terminal. The script will proceed through several steps:

1. **Set Target Domain:** You will be prompted to enter the target domain if it is not set as an environment variable.
2. **Select Protocol:** Choose between HTTP and HTTPS for the target.
3. **Initial Fuzzing:** The script runs a short `ffuf` session to gather initial data.
4. **Analysis:** Analyzes the initial fuzz output to create filter strings for common values.
5. **Refined Fuzzing:** Re-runs `ffuf` with the generated filters to refine the results.
6. **Cleanup:** Removes temporary files created during the script execution.

### Example :memo:

Running the script from the command line:
```bash
subdomains
```

## Contributing :handshake:

Contributions to the `subdomain-script` are welcome. Please submit pull requests or open issues to suggest improvements or report bugs.

## License :balance_scale:

This project is licensed under the FAFO License
