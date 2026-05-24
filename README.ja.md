<div align="center">
  <img src="https://download.alianblank.com/gameframex/gameframex_logo_320.png" alt="Game Frame X Logo" width="160" />
</div>

# Game Frame X UnityWebSocket

[![License](https://img.shields.io/github/license/GameFrameX/com.gameframex.unity.psygames.unitywebsocket)](https://github.com/GameFrameX/com.gameframex.unity.psygames.unitywebsocket/blob/main/LICENSE)
[![Version](https://img.shields.io/github/v/release/GameFrameX/com.gameframex.unity.psygames.unitywebsocket)](https://github.com/GameFrameX/com.gameframex.unity.psygames.unitywebsocket/releases)
[![Documentation](https://img.shields.io/badge/Documentation-docs-blue)](https://gameframex.doc.alianblank.com)

> インディゲーム開発者向けオールインワンソリューション · インディ開発者の夢を支援

[ドキュメント](https://gameframex.doc.alianblank.com) · [クイックスタート](#クイックスタート) · [QQグループ](https://qm.qq.com/q/5U9Fvebw) · [言語](#言語)

---

## 言語

[English](README.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | **日本語** | [한국어](README.ko.md)

---

## プロジェクト概要

Unity 用 WebSocket ライブラリ。このライブラリは主に `https://github.com/AlianBlank/GameFrameX` のサブライブラリとして使用されます。

## クイックスタート

### インストール（3つの方法）

1. `manifest.json` ファイルに以下の内容を直接追加します：
   ```json
   {"com.gameframex.unity.psygames.unitywebsocket": "https://github.com/AlianBlank/com.gameframex.unity.psygames.unitywebsocket.git"}
   ```

2. Unity の `Package Manager` で `Git URL` を使用して追加：https://github.com/AlianBlank/com.gameframex.unity.psygames.unitywebsocket.git

3. リポジトリを直接ダウンロードして、Unity プロジェクトの `Packages` ディレクトリに配置します。自動的に読み込まれます。

### 変更点

1. `IsConnected` プロパティを追加。

## 使用例

### オンラインデモ

- **[https://psygames.github.io/UnityWebSocket/](https://psygames.github.io/UnityWebSocket/)**

### 基本的な使い方

```csharp
// 名前空間
using UnityWebSocket;

// インスタンスの作成
string address = "ws://echo.websocket.org";
WebSocket socket = new WebSocket(address);

// コールバックの登録
socket.OnOpen += OnOpen;
socket.OnClose += OnClose;
socket.OnMessage += OnMessage;
socket.OnError += OnError;

// 接続
socket.ConnectAsync();

// 文字列データの送信
socket.SendAsync(str);
// または byte[] データの送信（推奨）
socket.SendAsync(bytes);

// 接続を閉じる
socket.CloseAsync();
```

### Unity 定義シンボル（オプション）

- `UNITY_WEB_SOCKET_LOG` 内部ログ情報を有効化。
- `UNITY_WEB_SOCKET_ENABLE_ASYNC` ネットワークスレッドでメッセージを処理（WebGL 以外のプラットフォーム）。

## 変更履歴

詳細は [CHANGELOG.md](CHANGELOG.md) をご覧ください。

## ライセンス

詳細は [LICENSE](LICENSE) ファイルをご覧ください。
