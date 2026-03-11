# Domain: Cybersecurity

## Recommended Stack

| Layer | Tool | Why |
|---|---|---|
| UI | Streamlit / CLI | Streamlit for dashboards, CLI for tools |
| Packet analysis | Scapy / Pyshark | Scapy for crafting, Pyshark for reading |
| Log analysis | Pandas + regex | Fast for structured log parsing |
| ML detection | Scikit-learn | Good for anomaly detection and classification |
| LLM-assisted | Groq (LLaMA 3.1) | For NLP on threats, report generation |
| Network scanning | python-nmap | Python wrapper for Nmap |
| Web security | requests + BeautifulSoup | For passive recon and analysis |
| SIEM-like | SQLite + Pandas | Lightweight event storage and querying |
| Visualization | Plotly / Folium | Plotly for metrics, Folium for geo-IP maps |
| CTF tools | pwntools, z3, Pillow | Binary exploitation, crypto, steganography |

## Best Practices

- **Never run offensive tools against systems you don't own** — always note this in project docs
- Sanitize all user inputs — especially in tools that handle URLs, IPs, or file paths
- Use `subprocess` with a list (not string) to avoid command injection
- Store logs with timestamps in ISO 8601 format
- For detection tools: document your false positive rate honestly
- Use environment variables for API keys, never hardcode them
- For SIEM/monitoring: define alert thresholds clearly in config, not in code
- Rate-limit API calls in scanning tools — don't hammer endpoints
- Add a disclaimer to security tools: intended use, legal limits
- For CTF writeups in READMEs: note the platform (TryHackMe, HTB) and difficulty
