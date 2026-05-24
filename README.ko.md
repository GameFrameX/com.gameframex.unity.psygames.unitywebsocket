<div align="center">
  <img src="https://download.alianblank.com/gameframex/gameframex_logo_320.png" alt="Game Frame X Logo" width="160" />
</div>

# Game Frame X UnityWebSocket

[![License](https://img.shields.io/github/license/GameFrameX/com.gameframex.unity.psygames.unitywebsocket)](https://github.com/GameFrameX/com.gameframex.unity.psygames.unitywebsocket/blob/main/LICENSE)
[![Version](https://img.shields.io/github/v/release/GameFrameX/com.gameframex.unity.psygames.unitywebsocket)](https://github.com/GameFrameX/com.gameframex.unity.psygames.unitywebsocket/releases)
[![Documentation](https://img.shields.io/badge/Documentation-docs-blue)](https://gameframex.doc.alianblank.com)

> 인디 게임 개발자를 위한 올인원 솔루션 · 인디 개발자의 꿈을 실현

[문서](https://gameframex.doc.alianblank.com) · [빠른 시작](#빠른-시작) · [QQ 그룹](https://qm.qq.com/q/5U9Fvebw) · [언어](#언어)

---

## 언어

[English](README.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | [日本語](README.ja.md) | **한국어**

---

## 프로젝트 개요

Unity용 WebSocket 라이브러리 지원. 이 라이브러리는 주로 `https://github.com/AlianBlank/GameFrameX`의 하위 라이브러리로 사용됩니다.

## 빠른 시작

### 설치 (세 가지 방법)

1. `manifest.json` 파일에 다음 내용을 직접 추가합니다:
   ```json
   {"com.gameframex.unity.psygames.unitywebsocket": "https://github.com/AlianBlank/com.gameframex.unity.psygames.unitywebsocket.git"}
   ```

2. Unity의 `Package Manager`에서 `Git URL`을 사용하여 추가: https://github.com/AlianBlank/com.gameframex.unity.psygames.unitywebsocket.git

3. 저장소를 직접 다운로드하여 Unity 프로젝트의 `Packages` 디렉토리에 배치합니다. 자동으로 로드됩니다.

### 변경 사항

1. `IsConnected` 속성 추가.

## 사용 예시

### 온라인 데모

- **[https://psygames.github.io/UnityWebSocket/](https://psygames.github.io/UnityWebSocket/)**

### 기본 사용법

```csharp
// 네임스페이스
using UnityWebSocket;

// 인스턴스 생성
string address = "ws://echo.websocket.org";
WebSocket socket = new WebSocket(address);

// 콜백 등록
socket.OnOpen += OnOpen;
socket.OnClose += OnClose;
socket.OnMessage += OnMessage;
socket.OnError += OnError;

// 연결
socket.ConnectAsync();

// 문자열 데이터 전송
socket.SendAsync(str);
// 또는 byte[] 데이터 전송 (권장)
socket.SendAsync(bytes);

// 연결 닫기
socket.CloseAsync();
```

### Unity 정의 기호 (선택 사항)

- `UNITY_WEB_SOCKET_LOG` 내부 로그 정보 활성화.
- `UNITY_WEB_SOCKET_ENABLE_ASYNC` 네트워크 스레드에서 메시지 처리 (WebGL이 아닌 플랫폼).

## 변경 로그

자세한 내용은 [CHANGELOG.md](CHANGELOG.md)를 참조하세요.

## 라이선스

자세한 내용은 [LICENSE](LICENSE) 파일을 참조하세요.
