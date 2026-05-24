<div align="center">
  <img src="https://download.alianblank.com/gameframex/gameframex_logo_320.png" alt="Game Frame X Logo" width="160" />
</div>

# Game Frame X UnityWebSocket

[![License](https://img.shields.io/github/license/GameFrameX/com.gameframex.unity.psygames.unitywebsocket)](https://github.com/GameFrameX/com.gameframex.unity.psygames.unitywebsocket/blob/main/LICENSE)
[![Version](https://img.shields.io/github/v/release/GameFrameX/com.gameframex.unity.psygames.unitywebsocket)](https://github.com/GameFrameX/com.gameframex.unity.psygames.unitywebsocket/releases)
[![Documentation](https://img.shields.io/badge/Documentation-docs-blue)](https://gameframex.doc.alianblank.com)

> All-in-One Solution for Indie Game Development · Empowering Indie Developers' Dreams

[Documentation](https://gameframex.doc.alianblank.com) · [Quick Start](#quick-start) · [QQ Group](https://qm.qq.com/q/5U9Fvebw) · [Language](#language)

---

## Language

**English** | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | [日本語](README.ja.md) | [한국어](README.ko.md)

---

## Project Overview

WebSocket library for Unity. This library primarily serves as a sub-library for `https://github.com/AlianBlank/GameFrameX`.

## Quick Start

### Installation (three methods)

1. Add the following content directly to `manifest.json`:
   ```json
   {"com.gameframex.unity.psygames.unitywebsocket": "https://github.com/AlianBlank/com.gameframex.unity.psygames.unitywebsocket.git"}
   ```

2. Add via Unity's `Package Manager` using `Git URL`: https://github.com/AlianBlank/com.gameframex.unity.psygames.unitywebsocket.git

3. Download the repository directly and place it in the Unity project's `Packages` directory. It will be auto-loaded.

### Modifications

1. Added `IsConnected` property.

## Usage Examples

### Online Demo

- **[https://psygames.github.io/UnityWebSocket/](https://psygames.github.io/UnityWebSocket/)**

### Basic Usage

```csharp
// the namespace
using UnityWebSocket;

// create instance
string address = "ws://echo.websocket.org";
WebSocket socket = new WebSocket(address);

// register callback
socket.OnOpen += OnOpen;
socket.OnClose += OnClose;
socket.OnMessage += OnMessage;
socket.OnError += OnError;

// connect
socket.ConnectAsync();

// send string data
socket.SendAsync(str);
// or send byte[] data (suggested)
socket.SendAsync(bytes);

// close connection
socket.CloseAsync();
```

### Unity Define Symbols (Optional)

- `UNITY_WEB_SOCKET_LOG` Open internal log info.
- `UNITY_WEB_SOCKET_ENABLE_ASYNC` Use network thread handle message (not WebGL platform).

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for details.

## License

See the [LICENSE](LICENSE) file for details.
