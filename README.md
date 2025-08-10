# JPass  
**Secure, Cross-Platform Folder Access Utility**  
*Developed by Beastros*  

JPass is a lightweight utility for controlled access to a hidden folder on macOS and Windows systems. It uses a password-gated lock/unlock mechanism and includes an optional, thematic error response for failed authentication attempts. The design draws subtle influence from classic cinematic depictions of computer security systems.  

---

## Key Features
- **Cross-Platform Compatibility** — Native support for both macOS and Windows environments.  
- **Password Authentication** — Default credentials provided; configurable within source scripts.  
- **Hidden Data Storage** — Creates a concealed `.data` directory within the user’s home path.  
- **Thematic Error Handling** — Incorrect password attempts trigger both visual and audible alerts, inspired by iconic film sequences.  
- **Portable Deployment** — Delivered as a self-contained package; no system modifications required.  

---

## System Requirements
- **macOS**: 10.13 or later  
- **Windows**: 10 or later  
- Terminal/Command Prompt or PowerShell access  

---

## Installation
1. Download the latest release from the [Releases](../../releases) page.  
2. Extract the package for your operating system.  

---

## Usage
1. Run the appropriate executable or script for your OS.  
2. Enter the password to unlock the hidden folder.  
3. Re-run the utility and authenticate to re-lock the folder.  

---

## Quick Start

### macOS
```bash
# 1) Download and unzip (from the Releases page)
cd ~/Downloads
unzip JPass-crossplatform.zip
cd JPass-crossplatform/macos

# 2) (If macOS Gatekeeper flags the app) remove quarantine and run
xattr -dr com.apple.quarantine JPass.app || true

# 3) Make scripts executable (if you’re using the shell scripts)
chmod +x jpass.sh setup.sh

# 4) Run the app or the script
open JPass.app
# or:
./jpass.sh
Windows
bat
Copy
Edit
:: 1) Download and extract the ZIP (from Releases)
cd %USERPROFILE%\Downloads

:: 2) If you used built-in extractor, the folder will be created automatically:
cd JPass-crossplatform\windows

:: 3) Run via CMD (recommended)
JPass.cmd
PowerShell (alternative):

powershell
Copy
Edit
# If PowerShell blocks scripts, unblock first:
Unblock-File .\JPass.ps1
.\JPass.ps1
Default Credentials
Password: Admin1!

To change: see Change Password section below.

Change Password
To set your own password:

macOS (jpass.sh):

Open macos/jpass.sh in a text editor.

Locate the line:

bash
Copy
Edit
PASSWORD="Admin1!"
Replace Admin1! with your desired password. Save the file.

Windows (JPass.cmd):

Open windows/JPass.cmd in a text editor.

Locate the line:

bat
Copy
Edit
set PASSWORD=Admin1!
Replace Admin1! with your desired password. Save the file.

Windows (JPass.ps1):

Open windows/JPass.ps1 in a text editor.

Locate the line:

powershell
Copy
Edit
$PASSWORD = "Admin1!"
Replace Admin1! with your desired password. Save the file.

Folder Behavior
On unlock, a hidden folder is created at:

macOS: ~/JPass.data

Windows: %USERPROFILE%\JPass.data

Re-run and authenticate to re-lock.

Verify Download (optional)
macOS:

bash
Copy
Edit
shasum -a 256 JPass-crossplatform.zip
Windows (PowerShell):

powershell
Copy
Edit
Get-FileHash .\JPass-crossplatform.zip -Algorithm SHA256
Troubleshooting
macOS “app is damaged or can’t be opened” → run the xattr command in Quick Start, then try open JPass.app again.

Windows “blocked by policy” → use Unblock-File in PowerShell or run JPass.cmd from an Administrator CMD if your org policies require it.

License
This project is provided as-is for personal and educational use.
© 2025 Beastros. All rights reserved.


