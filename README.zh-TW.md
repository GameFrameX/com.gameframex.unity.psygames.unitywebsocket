<div align="center">
  <img src="https://download.alianblank.com/gameframex/gameframex_logo_320.png" alt="Game Frame X Logo" width="160" />
</div>

# Game Frame X UnityWebSocket

[![License](https://img.shields.io/github/license/GameFrameX/com.gameframex.unity.psygames.unitywebsocket)](https://github.com/GameFrameX/com.gameframex.unity.psygames.unitywebsocket/blob/main/LICENSE)
[![Version](https://img.shields.io/github/v/release/GameFrameX/com.gameframex.unity.psygames.unitywebsocket)](https://github.com/GameFrameX/com.gameframex.unity.psygames.unitywebsocket/releases)
[![Documentation](https://img.shields.io/badge/Documentation-docs-blue)](https://gameframex.doc.alianblank.com)

> 獨立遊戲前後端一體化解決方案 · 獨立遊戲開發者的圓夢大使

[文檔](https://gameframex.doc.alianblank.com) · [快速開始](#快速開始) · [QQ群](https://qm.qq.com/q/5U9Fvebw) · [語言](#語言)

---

## 語言

[English](README.md) | [简体中文](README.zh-CN.md) | **繁體中文** | [日本語](README.ja.md) | [한국어](README.ko.md)

---

## 項目簡介

用於 Unity 的 WebSocket 庫支援。此套件主要服務於 `https://github.com/AlianBlank/GameFrameX` 作為子套件使用。

## 快速開始

### 安裝方式（三種方式）

1. 直接在 `manifest.json` 檔案中新增以下內容
   ```json
   {"com.gameframex.unity.psygames.unitywebsocket": "https://github.com/AlianBlank/com.gameframex.unity.psygames.unitywebsocket.git"}
   ```

2. 在 Unity 的 `Packages Manager` 中使用 `Git URL` 的方式新增套件，地址為：https://github.com/AlianBlank/com.gameframex.unity.psygames.unitywebsocket.git

3. 直接下載倉庫放置到 Unity 專案的 `Packages` 目錄下。會自動載入識別。

### 改動功能

1. 新增 `IsConnected` 屬性。

## 使用範例

### 線上範例

- **[https://psygames.github.io/UnityWebSocket/](https://psygames.github.io/UnityWebSocket/)**

### 基本用法

```csharp
// 命名空間
using UnityWebSocket;

// 建立實例
string address = "ws://echo.websocket.org";
WebSocket socket = new WebSocket(address);

// 註冊回調
socket.OnOpen += OnOpen;
socket.OnClose += OnClose;
socket.OnMessage += OnMessage;
socket.OnError += OnError;

// 連接
socket.ConnectAsync();

// 傳送 string 類型資料
socket.SendAsync(str);

// 或者傳送 byte[] 類型資料（建議使用）
socket.SendAsync(bytes);

// 關閉連接
socket.CloseAsync();
```

### Unity 編譯宏（可選項）

- `UNITY_WEB_SOCKET_LOG` 開啟底層日誌輸出。
- `UNITY_WEB_SOCKET_ENABLE_ASYNC` 針對非 WebGL 平台使用非同步執行緒處理訊息（需自行處理跨執行緒存取 Unity 元件問題）。

## 更新日誌

詳見 [CHANGELOG.md](CHANGELOG.md)。

## 開源協議

詳見 [LICENSE](LICENSE) 檔案。
