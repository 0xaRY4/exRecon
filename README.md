# exRecon - Advanced Subdomain Reconnaissance Tool 🔍

**exRecon** is a powerful subdomain enumeration and reconnaissance tool designed for bug bounty hunters, penetration testers, and security researchers. It automates the process of discovering subdomains and identifying live hosts with their technologies.

## Features ✨

- **Comprehensive Subdomain Enumeration** using multiple data sources
- **DNS Validation** to filter out non-resolving domains
- **HTTP Probing** with status codes and technology detection
- **Clean Output** with organized results
- **Customizable** for different reconnaissance needs

## Installation 🛠️

### Prerequisites

Before using exRecon, ensure you have the following tools installed:

1. **[Subfinder](https://github.com/projectdiscovery/subfinder)**
  
  ```bash
  go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
  ```
  
2. **[Assetfinder](https://github.com/tomnomnom/assetfinder)**
  
  ```bash
  go install github.com/tomnomnom/assetfinder@latest
  ```
  
3. **[github-subdomains](https://github.com/gwen001/github-subdomains)**
  
  ```bash
  go install github.com/gwen001/github-subdomains@latest
  ```
  
4. **[dnsx](https://github.com/projectdiscovery/dnsx)**
  
  ```bash
  go install -v github.com/projectdiscovery/dnsx/cmd/dnsx@latest
  ```
  
5. **[httpx](https://github.com/projectdiscovery/httpx)**
  
  ```bash
  go install -v github.com/projectdiscovery/httpx/cmd/httpx@latest
  ```
  

### Installing exRecon

```bash
git clone https://github.com/aRY4/exRecon.git
cd exRecon
chmod +x exrecon.sh
```

## Usage 🚀

Basic usage:

```bash
./exrecon.sh example.com
```

Advanced usage:

```bash
# Save output to a specific directory
./exrecon.sh example.com > results.txt

# Run with custom wordlist (optional)
cat custom_wordlist.txt | ./exrecon.sh example.com
```

## Workflow 🔄

1. **Subdomain Enumeration**:
  
  - Subfinder (Passive DNS)
  - Assetfinder (Public archives)
  - github-subdomains (GitHub scraping)
  - AbuseIPDB (Additional sources)
2. **Data Processing**:
  
  - Merges and deduplicates results
  - Sorts subdomains alphabetically
3. **DNS Resolution**:
  
  - Validates which subdomains have active DNS records
  - Filters out non-resolving domains
4. **HTTP Probing**:
  
  - Identifies live web services
  - Detects HTTP status codes
  - Fingerprints web technologies

## Output Files 📂

The tool generates three main output files:

1. `final-subdomains.txt` - All unique subdomains found
2. `resolved-subdomains.txt` - Subdomains with valid DNS records
3. `live-subdomains-with-status.txt` - Live hosts with status codes and technologies

## Customization ⚙️

You can customize the tool by:

- Editing the curl headers in the script for AbuseIPDB
- Adding additional subdomain enumeration tools
- Modifying httpx flags for different scanning options

## Contribution 🤝

Contributions are welcome! Please open an issue or submit a pull request for any:

- Bug fixes
- Feature additions
- Performance improvements

## License 📜

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Disclaimer ⚠️

This tool is intended for **legal security research and authorized penetration testing only**. The developer is not responsible for any misuse of this tool.

---

### Sample Output Preview

```
.d8888b. dP.  .dP 88d888b. .d8888b. .d8888b. .d8888b. 88d888b. 
88ooood8  `8bd8'  88'  `88 88ooood8 88'  `"" 88'  `88 88'  `88 
88.  ...  .d88b.  88       88.  ... 88.  ... 88.  .88 88    88 
`88888P' dP'  `dP dP       `88888P' `88888P' `88888P' dP    dP

[+] PHASE 1: Subdomain Enumeration
[1] Running Subfinder......... Done! (142 subs)
[2] Running Assetfinder...... Done! (98 subs)
[3] Running github-subdomains. Done! (73 subs)
[4] Fetching AbuseIPDB...... Done! (15 subs)

[+] Scan completed!
Results saved in current directory:
    - final-subdomains.txt
    - resolved-subdomains.txt
    - live-subdomains-with-status.txt
```
