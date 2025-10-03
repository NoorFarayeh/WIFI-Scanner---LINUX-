# WiFi Network Scanner - Linux Edition

A standalone Linux application for analyzing nearby WiFi networks and generating detailed reports. Built with Python, compiled with Cython to C, and packaged as a single executable file.

## Features

* **Network Discovery**: Scans all visible WiFi networks using nmcli/iw
* **Signal Analysis**: Measures and categorizes signal strength (Strong/Good/Weak)
* **Security Assessment**: Identifies open networks vs secured networks
* **Device Identification**: Vendor lookup through MAC address analysis (embedded OUI database)
* **Network Classification**: Distinguishes between regular WiFi, mobile hotspots, hidden networks, and device sharing
* **Data Export**: Saves results to JSON and CSV formats
* **Portable**: Single executable file, no Python installation required

## Download

**Latest Release**: [Download wifi-scanner](https://github.com/NoorFarayeh/WIFI-Scanner---LINUX-/releases/download/v1/wifi-scanner)

File size: ~7.9 MB (includes Python runtime)

## System Requirements

* Linux (any modern distribution)
* x86_64 architecture
* `nmcli` (NetworkManager) or `iw` (wireless-tools)
* Root access for scanning

## Installation

```bash
# Ubuntu/Debian/Kali
sudo apt install network-manager wireless-tools

# Fedora/RHEL
sudo dnf install NetworkManager wireless-tools

# Arch Linux
sudo pacman -S networkmanager wireless_tools
```

## How to Use

1. Download `wifi-scanner` from the releases section
2. Make it executable: `chmod +x wifi-scanner`
3. Run with root: `sudo ./wifi-scanner`
4. Results are saved to `wifi_results_*.json` and `wifi_results_*.csv` in the same folder

## Sample Output

```
WIFI NEIGHBORHOOD SCAN

NETWORKS DETECTED: 12
Your area shows normal WiFi activity.

NETWORK BREAKDOWN:
- Regular WiFi Networks: 9
- Mobile Phone Hotspots: 2
- Device Sharing (P2P/Accessory): 0
- Hidden Networks: 1

SIGNAL STRENGTH ANALYSIS:
- Strong Signal (70%+): 4 networks
- Good Signal (50-69%): 6 networks
- Weak Signal (<50%): 2 networks

SECURITY STATUS:
- Password Protected: 11 networks
- Open Networks: 1 network

TOP DEVICE VENDORS:
- TP-Link: 3 devices
- Netgear: 2 devices
- Apple: 2 devices
- Unknown: 5 devices
```

## Technical Details

* **Language**: Python 3.13
* **Compilation**: Cython (Python → C)
* **Packaging**: PyInstaller
* **APIs Used**: Linux nmcli and iw commands
* **Output Formats**: Console display, JSON, CSV
* **Architecture**: Single-threaded with retry logic for reliability
* **Protection**: Obfuscated binary, stripped symbols

## Use Cases

* Network site surveys for small businesses
* WiFi environment analysis before router placement
* Connectivity assessment for real estate evaluation
* Basic network security awareness
* IT troubleshooting and planning

## Troubleshooting

**No networks found:**
* Ensure WiFi adapter is enabled: `nmcli radio wifi on`
* Run with sudo: `sudo ./wifi-scanner`
* Check NetworkManager status: `systemctl status NetworkManager`

**Permission denied:**
* Always run with sudo for hardware access

**nmcli/iw not found:**
* Install dependencies as shown in Installation section

**WSL/VM limitations:**
* This tool requires physical WiFi hardware
* Does not work in WSL or most virtualized environments

## About This Project

This tool demonstrates practical system programming skills including:
* Linux API integration (nmcli/iw)
* Data parsing and validation
* Error handling and retry mechanisms
* Cross-distribution compatibility
* Professional software distribution
* Code obfuscation and compilation

Built as a portfolio project showcasing real-world application development beyond typical coding exercises.

## Privacy & Security

* No data is transmitted or stored remotely
* Only scans publicly broadcast WiFi beacon information
* Creates local files only in the execution directory
* No network connections are established
* Source code protected through compilation and obfuscation

## Related Projects

Windows version: [WiFi-Scanner for Windows](https://github.com/NoorFarayeh/WIFI-Scanner)

## License


MIT License - See LICENSE file for details

