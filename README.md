# Squatto
Domain name squatter's Swiss army knife

This tool is designed for domain name enthusiasts and investors who want to track the availability and expiration status of domain names. It scans a list of domains, checks their availability, and identifies those that are soon to expire—allowing users to be notified of potentially valuable domain names coming up for purchase.

## Features

- **Domain Availability Check**: Performs a DNS lookup to see if a domain is unregistered.
- **WHOIS Expiration Check**: For registered domains, checks the expiration date using WHOIS data to identify those expiring within the next 30 days.
- **HTTP Status Check**: Attempts an HTTP request to detect active domains, providing a better sense of which domains are in current use.
- **Output Files**:
  - `available.txt`: Lists unregistered and available domains.
  - `comingsoon.txt`: Lists registered domains expiring within 30 days.

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/peteralcock/squatto.git
   cd domain-squatting-tool
   ```

2. **Install required dependencies**:
   Ensure Python 3.x is installed, then run:
   ```bash
   pip install python-whois requests
   ```

## Usage

1. **Prepare Domain List**:
   Create a text file named `domains.txt` in the same directory as the script. Add one domain per line, like so:
   ```
   example.com
   mydomain.net
   testsite.org
   ```

2. **Run the Script**:
   Execute the script:
   ```bash
   python main.py
   ```
   The tool will:
   - Check if each domain is unregistered and save available ones to `available.txt`.
   - Identify soon-to-expire domains based on WHOIS data and save them to `comingsoon.txt`.

3. **Review Results**:
   - **`available.txt`**: Lists domains that are unregistered.
   - **`comingsoon.txt`**: Lists registered domains with expiration dates within the next 30 days.

## Example Output

Upon running the tool, you’ll see output similar to this:

```
example.com is available
mydomain.net is expiring soon on 2024-12-01
testsite.org is active and taken
Available domains saved to available.txt
Domains expiring soon saved to comingsoon.txt
```

## Notes

- **Expiration Threshold**: The default threshold for "soon-to-expire" domains is set to 30 days. Adjust this by changing `EXPIRATION_THRESHOLD_DAYS` in the code.
- **Error Handling**: WHOIS lookups may occasionally fail or be incomplete. Errors are logged to the console, but the script will continue processing other domains.

## License

This project is licensed under the MIT License.
