# CODSOFT_TASKSNO_1

# 🦈 PyShark – Network Packet Analyzer

**PyShark** is a production‑ready, command‑line network packet analyzer built with Python and Scapy.  
It captures live packets, extracts key headers (Ethernet, IP, TCP/UDP/ICMP), and displays them in a clean, colour‑coded table.

## ✨ Features

- **Continuous monitoring** – runs until you press `Ctrl+C` (or capture a fixed number with `-c`).
- Extracts:
  - Timestamp
  - Source / Destination MAC addresses
  - Source / Destination IP addresses
  - Protocol (TCP, UDP, ICMP, etc.)
  - Source / Destination ports (for TCP/UDP)
  - Payload (hex dump + printable ASCII preview)
- BPF filter support (e.g., `tcp port 80`)
- Save captured packets to a `.pcap` file
- Graceful interrupt (Ctrl+C) and privilege checks
- Attractive ASCII logo with ANSI colours

## 📦 Installation

  bash

    # Clone the repository
    git clone https://github.com/yourusername/pyshark.git
    cd pyshark

    # Install Python dependencies
    pip install -r requirements.txt

    # Make the script executable
    chmod +x pyshark

    # (Optional) Install globally
sudo cp pyshark /usr/local/bin/
Note: On Windows, install Npcap in WinPcap‑compatible mode.

🚀 Usage
Run with root/administrator privileges:

bash
sudo ./pyshark
Or, if installed globally:

bash
sudo pyshark
Command‑line options
Option	Description
-i IFACE	Network interface (e.g., eth0, wlan0). Default: Scapy's default.
-c N	Capture N packets and exit. Default: 0 (unlimited, Ctrl+C to stop).
-f FILTER	BPF filter (e.g., "tcp port 443").
-o FILE.pcap	Save captured packets to a PCAP file.
-l	List available network interfaces.
Examples
bash
# Capture continuously (default) – press Ctrl+C to stop
sudo pyshark

# Capture 10 packets on the default interface
sudo pyshark -c 10

# Capture HTTPS traffic on wlan0 and save to file
sudo pyshark -i wlan0 -f "tcp port 443" -o https.pcap

# Capture all ICMP (ping) packets indefinitely
sudo pyshark -f "icmp"

# List all interfaces
sudo pyshark -l
🧪 Testing with Different Traffic
Terminal 1 – start the analyzer:
sudo pyshark -i eth0 -f "icmp"

Terminal 2 – generate traffic:
ping 8.8.8.8

Watch ICMP packets appear live in Terminal 1. Press Ctrl+C to stop.

🛡️ Security & Ethics
Only capture traffic on networks you own or have explicit permission to monitor.

Unauthorised sniffing may be illegal. Use responsibly.

📄 License
MIT – see LICENSE file.

## 🚀 Step‑by‑Step

1. **Create a new directory** and move into it:

   ```bash
   mkdir pyshark
   cd pyshark
Create all five files with the content above.
You can use nano, vim, or cat to write each file.

Make the script executable:

bash
chmod +x pyshark
Initialise Git and commit:

bash
git init
git add .
git commit -m "Initial commit: PyShark v2.2"
Go to GitHub and create a new repository (name it pyshark).
Do not initialise it with README, .gitignore, or license – we already have them.

Link your local repo and push:

bash
git remote add origin https://github.com/Krishnamanaidu2526/pyshark.git
git branch -M main
git push -u origin main
Replace yourusername with your actual GitHub username.

✅ Verifying the Tool
After cloning or installing, run:

bash
sudo ./pyshark
It will start capturing continuously until you press Ctrl+C.
You can test with different traffic as described in the README.

Happy sniffing! 🦈


