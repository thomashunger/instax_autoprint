Markdown
# instax_autoprint

An automated bridge that turns your professional camera into an instant photo printer. 

This installer sets up a complete, ready-to-run project in just two commands. It spins up a local FTP server on your Raspberry Pi to receive images directly from your camera, automatically post-processes them, and prints them out via Bluetooth on an **Instax Mini Link** printer.

---

## 🛠️ Hardware Requirements

* **Camera** with built-in FTP transfer capabilities
* **Instax Mini Link** (compatible with versions 1, 2, or 3)
* **Raspberry Pi** (3, 4, 5, Zero, or Zero W2)
* **Battery shield module for Raspberry Pi** *(Optional, but recommended for a completely wireless setup)*

---

## 🔄 Connection Flow

Camera --(FTP)--> Raspberry Pi (ftp_user) --(BLE)--> Instax Mini Link Printer
🚀 Quick Installation
Navigate to the directory where you cloned or downloaded the project files, then run the following commands in your terminal:

Bash
sudo sed -i 's/[^[:print:]\t]/ /g' instax_project_installer.sh
sudo bash instax_project_installer
Once the script finishes running, the project is fully installed and operational!

⚙️ FTP Server Credentials
Configure your camera to send images to the Raspberry Pi FTP server using these default credentials:

Username: ftp_user

Password: ftp_user
