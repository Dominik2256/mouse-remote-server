# Mouse Remote Pro - Server

A lightweight, portable Windows application that turns your smartphone into a wireless mouse, keyboard, and file-transfer hub for your PC. This repository contains the C# .NET server-side application.

## ▣ Mobile App
To use this server, you need the companion mobile app (Android). 
**[⯈ Get the Mobile App repository here](https://github.com/Dominik2256/mouse-remote-client)**

## ❖ Features
* **Remote Mouse & Keyboard:** Control your PC cursor and type remotely with low latency.
* **Two-Way File Transfer:** Easily send files from your PC to your phone, or receive photos and documents from your phone directly to a local `temporary` folder on your PC.
* **Fully Portable:** No installation required. All settings (like your custom PIN and Windows AutoStart preference) are saved locally in a simple `config.json` file.
* **Auto-Update System:** Built-in updater that automatically fetches and installs the latest releases directly from GitHub.
* **Secure Connection:** Local WebSocket connection protected by a custom PIN.

## ⯈ How to Use
1. Go to the **Releases** section on the right side of this repository and download the latest `.zip` file.
2. Extract the files to a folder of your choice (e.g., on your Desktop or a USB drive).
3. Run `MouseRemotePro.exe`.
4. **Important:** Allow the application through the Windows Firewall when prompted by the system (otherwise, the phone won't connect).
5. Go to the "Settings" tab, set your custom PIN, and click Save (you can leave it empty).
6. Open the companion mobile app, enter the IP address displayed on the server's screen along with your PIN, and tap Connect.

## ⚙ How it Works
The application runs a lightweight WebSocket server (powered by the `Fleck` library) strictly on your local Wi-Fi network. It listens for JSON-formatted commands from the mobile client and translates them into system-level Windows inputs (using `WindowsInput.dll`) or file I/O operations.
