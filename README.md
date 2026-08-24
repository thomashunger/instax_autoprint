Markdown
# instax_autoprint

An automated bridge that turns your professional camera into an instant photo printer. 

This installer sets up a complete, ready-to-run project in just two commands. It spins up a local FTP server on your Raspberry Pi to receive images directly from your camera, automatically post-processes them, and prints them out via Bluetooth on an **Instax Mini Link** printer.

---

> [!WARNING]
> **Important Connectivity Notice & Recommended Setup**
> 
> * **Loss of External Wi-Fi:** During operation, this project configures the Raspberry Pi as an **Access Point (AP)** (`hostapd`) so your camera can connect directly to it via Wi-Fi. As a result, **the Pi will lose its connection to your home/office Wi-Fi network**.
> * **Recommended SSH Access (USB OTG):** If you are configuring or debugging the Pi headlessly, **it is highly recommended to work via USB OTG (Ethernet over USB)** (e.g., using a Pi Zero, Zero 2 W, Pi 4, or Pi 5). This allows you to keep an active SSH terminal over USB cable while the onboard Wi-Fi interface switches into Access Point mode.

---

## 🛠️ Hardware Requirements

* **Camera** with built-in FTP transfer capabilities
* **Instax Mini Link** (compatible with versions 1, 2, or 3)
* **Raspberry Pi** (3, 4, 5, Zero, or Zero 2 W)
* **Battery shield module for Raspberry Pi** *(Optional, but recommended for a completely wireless setup)*

---

## 🔄 Connection Flow

```text
Camera ---[ Wi-Fi (FTP) ]---> Raspberry Pi (ftp_user) ---[ Bluetooth (BLE) ]---> Instax Mini Link
🚀 Quick Installation
Note: Make sure you are connected via USB OTG or local serial/monitor before running the installer, as Wi-Fi network connections will be dropped when hostapd is initialized.

Navigate to the directory where you cloned or downloaded the project files, then run the following commands in your terminal:

Bash
sudo sed -i 's/[^[:print:]\t]/ /g' instax_project_installer.sh
sudo bash instax_project_installer.sh
Once the script finishes running, the project is fully installed and operational!

⚙️ FTP Server Credentials
Configure your camera to send images to the Raspberry Pi FTP server using these default credentials:

Username: ftp_user

Password: ftp_user
