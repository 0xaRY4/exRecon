# exrecon - external subdomain reconnaissance automation 

## Quick Install

1. Install dependencies:
```bash
# Core tools
go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
go install github.com/tomnomnom/assetfinder@latest
go install github.com/gwen001/github-subdomains@latest
go install -v github.com/projectdiscovery/dnsx/cmd/dnsx@latest
go install -v github.com/projectdiscovery/httpx/cmd/httpx@latest
```

# Chaos (requires API key)
```bash
go install -v github.com/projectdiscovery/chaos-client/cmd/chaos@latest
```

2. Configure Chaos:
```bash
echo "export PDCP_API_KEY=<your-api-key-here>" >> ~/.bashrc  # Get from https://chaos.projectdiscovery.io
source ~/.bashrc
```

3. Get exRecon:
```bash
git clone https://github.com/aRY4/exRecon.git && cd exRecon
chmod +x exrecon
```

> **Note**: Chaos requires a free API key from ProjectDiscovery for subdomain enumeration.

Key additions:
1. Added Chaos installation command in the dependencies section
2. Included Chaos configuration note with API key instructions
3. Maintained the concise format while adding the new tool
4. Added visual separation between tool installation and configuration
5. Included note about API key requirement

The rest of your documentation can remain unchanged as the workflow and usage already include Chaos functionality.
