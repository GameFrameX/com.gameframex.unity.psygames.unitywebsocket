<div align="center">
  <img src="https://download.alianblank.com/gameframex/gameframex_logo_320.png" alt="Game Frame X Logo" width="160" />
</div>

# Game Frame X UnityWebSocket

[![License](https://img.shields.io/github/license/GameFrameX/com.gameframex.unity.psygames.unitywebsocket)](https://github.com/GameFrameX/com.gameframex.unity.psygames.unitywebsocket/blob/main/LICENSE)
[![Version](https://img.shields.io/github/v/release/GameFrameX/com.gameframex.unity.psygames.unitywebsocket)](https://github.com/GameFrameX/com.gameframex.unity.psygames.unitywebsocket/releases)
[![Documentation](https://img.shields.io/badge/Documentation-docs-blue)](https://gameframex.doc.alianblank.com)

> 独立游戏前后端一体化解决方案 · 独立游戏开发者的圆梦大使

[文档](https://gameframex.doc.alianblank.com) · [快速开始](#快速开始) · [QQ群](https://qm.qq.com/q/5U9Fvebw) · [语言](#语言)

---

## 语言

[English](README.md) | **简体中文** | [繁體中文](README.zh-TW.md) | [日本語](README.ja.md) | [한국어](README.ko.md)

---

## 项目简介

用于 Unity 的 WebSocket 库支持。该库主要服务于 `https://github.com/AlianBlank/GameFrameX` 作为子库使用。

## 快速开始

### 安装方式（三种方式）

1. 直接在 `manifest.json` 文件中添加以下内容
   ```json
   {"com.gameframex.unity.psygames.unitywebsocket": "https://github.com/AlianBlank/com.gameframex.unity.psygames.unitywebsocket.git"}
   ```

2. 在 Unity 的 `Packages Manager` 中使用 `Git URL` 的方式添加库，地址为：https://github.com/AlianBlank/com.gameframex.unity.psygames.unitywebsocket.git

3. 直接下载仓库放置到 Unity 项目的 `Packages` 目录下。会自动加载识别。

### 改动功能

1. 增加 `IsConnected` 的属性。

## 使用示例

### 在线示例

- **[https://psygames.github.io/UnityWebSocket/](https://psygames.github.io/UnityWebSocket/)**

### 基本用法

```csharp
// 命名空间
using UnityWebSocket;

// 创建实例
string address = "ws://echo.websocket.org";
WebSocket socket = new WebSocket(address);

// 注册回调
socket.OnOpen += OnOpen;
socket.OnClose += OnClose;
socket.OnMessage += OnMessage;
socket.OnError += OnError;

// 连接
socket.ConnectAsync();

// 发送 string 类型数据
socket.SendAsync(str);

// 或者发送 byte[] 类型数据（建议使用）
socket.SendAsync(bytes);

// 关闭连接
socket.CloseAsync();
```

### Unity 编译宏（可选项）

- `UNITY_WEB_SOCKET_LOG` 打开底层日志输出。
- `UNITY_WEB_SOCKET_ENABLE_ASYNC` 针对非 WebGL 平台使用异步线程处理消息（需自行处理跨线程访问 Unity 组件问题）。

## 更新日志

详见 [CHANGELOG.md](CHANGELOG.md)。

## 开源协议

详见 [LICENSE](LICENSE) 文件。
