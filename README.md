<div align="center">

<img src="https://download.alianblank.com/gameframex/gameframex_logo_320.png" alt="Game Frame X Logo" width="160" />

# Game Frame X UnityWebSocket

[![License](https://img.shields.io/github/license/GameFrameX/com.gameframex.unity.psygames.unitywebsocket)](https://github.com/GameFrameX/com.gameframex.unity.psygames.unitywebsocket/blob/main/LICENSE.md)
[![Version](https://img.shields.io/github/v/release/GameFrameX/com.gameframex.unity.psygames.unitywebsocket)](https://github.com/GameFrameX/com.gameframex.unity.psygames.unitywebsocket/releases)
[![Unity Version](https://img.shields.io/badge/Unity-2019.4-black?logo=unity)](https://unity.com/)
[![Documentation](https://img.shields.io/badge/Documentation-docs-blue)](https://gameframex.doc.alianblank.com)

All-in-One Solution for Indie Game Development · Empowering Indie Developers' Dreams

<br />

[Documentation](https://gameframex.doc.alianblank.com) · [Quick Start](#quick-start) · QQ Group: 467608841 / 233840761

<br />

**English** | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | [日本語](README.ja.md) | [한국어](README.ko.md)

</div>

## Language

**English** | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | [日本語](README.ja.md) | [한국어](README.ko.md)

---

## Project Overview

WebSocket library for Unity. This library primarily serves as a sub-library for `https://github.com/AlianBlank/GameFrameX`.

## Quick Start

### Installation

Choose one of the following methods:

1. Edit your Unity project's `Packages/manifest.json` and add the `scopedRegistries` section:
   ```json
   {
     "scopedRegistries": [
       {
         "name": "GameFrameX",
         "url": "https://gameframex.upm.alianblank.uk",
         "scopes": [
           "com.gameframex"
         ]
       }
     ],
     "dependencies": {
       "com.gameframex.unity.psygames.unitywebsocket": "2.9.2"
     }
   }
   ```

   `scopes` controls which packages are resolved through this registry. Only packages whose names start with `com.gameframex` will be fetched from it.

2. Add to `manifest.json` dependencies:
   ```json
   {
      "com.gameframex.unity.psygames.unitywebsocket": "https://github.com/gameframex/com.gameframex.unity.psygames.unitywebsocket.git"
   }
   ```
3. Use **Package Manager** in Unity with **Git URL**: `https://github.com/gameframex/com.gameframex.unity.psygames.unitywebsocket.git`
4. Clone the repository into your Unity project's `Packages` directory. It will be loaded automatically.
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


## Dependencies

| Package | Description |
|---------|-------------|
| (无) | - |


## Documentation & Resources

- [Documentation](https://gameframex.doc.alianblank.com)

## Community & Support

- QQ Group: 467608841 / 233840761
## License

See the [LICENSE](LICENSE) file for details.
