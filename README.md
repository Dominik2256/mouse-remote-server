# ◽ MouseRemotePro — Server
---
A high-performance, portable Windows background service that bridges your PC with the MouseRemote mobile ecosystem. 

## 🔘 System Specifications
| Category | Details |
| :--- | :--- |
| **Framework** | .NET 10.0 (Windows Forms) |
| **Deployment** | Self-contained Portable EXE (111 MB) |
| **Networking** | Asynchronous TCP/IP Sockets |
| **Port** | 8765 (Default) |
| **OS Support** | Windows 10 / 11 (x64) |

---

## 📱 Mobile Companion
To control this server, you need the official Android client.
▫️ **[Get the Mobile App (.apk)](https://github.com/Dominik2256/mouse-remote-client)** ▫️
---

## 🚀 Key Features
* ◽ **Ultra-Low Latency**: Optimized socket communication for real-time cursor response.
* ◽ **System Integration**:
    * ▫️ **Tray Operation**: Runs silently in the system tray.
    * ▫️ **Auto-Start**: One-click Windows Registry integration for boot-up launch.
* ◽ **Volume Management**: Deep integration with Windows CoreAudio API for master and app-level volume control.
* ◽ **GitHub Sync**: Built-in update engine that checks for new releases directly via GitHub API.
* ◽ **No-Install**: Completely portable; all configurations are stored locally in `config.json`.

---

## 🔧 How It Works
The server operates as a listener on your local network.

### ▫️ Connection Flow
1. **Listening State**: Upon startup, the server opens a TCP socket on port `8765`.
2. **Discovery**: It responds to broadcast pings from the mobile app for easy pairing.
3. **Security**: Validates incoming packets using a user-defined PIN.
4. **Execution**: Translates mobile gestures into native Windows `Input` events (Mouse/Keyboard).

```mermaid
graph LR
  A[Mobile App] -- TCP Packet --> B(Port 8765)
  B --> C{PIN Validation}
  C -- Success --> D[Windows Input API]
  C -- Fail --> E[Drop Connection]
