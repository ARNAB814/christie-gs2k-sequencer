# Christie GS 2K Command Sequencer
 
A projector control and command sequencing tool designed for theatrical use at École Handsworth Secondary School.
 
Built for the **Christie GS Series 2K** laser projector. Sends TCP/IP API commands directly to the projector, and exports bash scripts compatible with **QLab Script Cues** for live production use.
 
---
 
## What it does
 
- Build sequences of Christie API commands in a visual interface
- Execute commands live over the network (Fire Now mode)
- Export sequences as `.sh` bash scripts for use in QLab
- Save and load templates for common sequences
- Supports all major GS 2K command categories: power, shutter, lens, input, image, color, light source, test patterns, geometry, and more
## What it is NOT
 
This is not a general-purpose projector tool. It is specifically designed for the **Christie GS Series 2K** and the command syntax documented in:
 
> Christie GS Series 2K Serial Commands Technical Reference — 020-103480-07 Rev. 1 (06-2025)
 
---
 
## Requirements
 
- Christie GS Series 2K projector connected to your network
- Projector TCP/IP API enabled (port 3002)
- macOS (primary), Windows, or Linux
- Node.js 16+ (to run from source)
- `nc` (netcat) installed — required for exported scripts on macOS/Linux
---
 
## Download
 
Go to [Releases](../../releases) and download the latest version for your platform:
 
| Platform | File |
|----------|------|
| macOS (Apple Silicon) | `Christie.GS.2K.Command.Sequencer-arm64.dmg` |
| macOS (Intel) | `Christie.GS.2K.Command.Sequencer-x64.dmg` |
| Windows | `Christie.GS.2K.Command.Sequencer-Setup.exe` |
 
### macOS: "App is damaged" error
 
macOS Gatekeeper will block unsigned apps. Run this in Terminal after downloading:
 
```bash
xattr -cr "Christie GS 2K Command Sequencer.app"
```
 
Then open normally.
 
---
 
## Run from source
 
```bash
git clone https://github.com/<your-repo>.git
cd christie-gs2k-command-sequencer
npm install
npm start
```
 
---
 
## QLab integration
 
1. Build your command sequence in the app
2. Click **Export Script** — saves a `.sh` file
3. In QLab, create a **Script Cue** → set type to **Shell Script** → select your file
4. Test with Go
The exported script uses `echo '(COMMAND)' | nc $PROJECTOR_IP $PORT` — the same format that works directly in Terminal.
 
---
 
## License
 
MIT License — free to use, modify, and distribute.
 
---
 
## Credits
 
Developed by **Arunav Saha** and **Nicole Erickson**  
For the **Handsworth Secondary School Theatre Program** (SD44)  
École Handsworth Secondary School
 
© 2026 — Released under the MIT License
 
