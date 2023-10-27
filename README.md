# gate-sniffer
## Information:
- Uses a steam installation of [Spiral Knights](https://www.spiralknights.com/) to sniff streamed network packets for Arcade gates in rotation and copies the latest gate in JSON to `../gatemap-viewer/gates/` and updates `../gatemap-viewer/gates/gate_list.txt`
## Requirements:
- Works with [Python 3](https://www.python.org/downloads/)
- [Npcap](https://npcap.com/)
- [Construct](https://construct.readthedocs.io/en/latest/)
> pip install construct
- [scapy](https://scapy.readthedocs.io/en/latest/)
> pip install scapy

# Configuring
## [fetch_and_start_app.py](fetch_and_start_app.py)
- Edit `PACKET_FILTER = 'dst net 192.168.1 and tcp and ip'` to reflect your local network configuration.<br>
E.g. If your local IP address is 192.168.5.109, replace `192.168.1` with `192.168.5`<br>
- Edit `SK_PATH = 'C:\\SteamLibrary\\steamapps\\common\\Spiral Knights'` to reflect the location of your Steam Spiral Knights installation.
- Edit `SK_ARGS = 'java_vm/bin/javaw.exe -jar getdown-pro.jar . "" username password'` with your own credentials.

# Usage
- Run [process_new_gate.bat](process_new_gate.bat)
- View gates with [gatemap-viewer](https://github.com/Magnus0SK/gatemap-viewer) or at [https://magnus0sk.github.io/gatemap-viewer/?show_timer=1](https://magnus0sk.github.io/gatemap-viewer/?show_timer=1)<br>
For local use, run `python -m http.server` on the command line and navigate to `127.0.0.1:8000/?show_timer=1`.
