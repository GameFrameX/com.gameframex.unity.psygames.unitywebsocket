<div align="center">

<img src="https://download.alianblank.com/gameframex/gameframex_logo_320.png" alt="Game Frame X Logo" width="160" />

# Game Frame X UnityWebSocket

[![License](https://img.shields.io/github/license/GameFrameX/com.gameframex.unity.psygames.unitywebsocket)](https://github.com/GameFrameX/com.gameframex.unity.psygames.unitywebsocket/blob/main/LICENSE.md)
[![Version](https://img.shields.io/github/v/release/GameFrameX/com.gameframex.unity.psygames.unitywebsocket)](https://github.com/GameFrameX/com.gameframex.unity.psygames.unitywebsocket/releases)
[![Unity Version](https://img.shields.io/badge/Unity-2019.4-black?logo=unity)](https://unity.com/)
[![Documentation](https://img.shields.io/badge/Documentation-docs-blue)](https://gameframex.doc.alianblank.com)

인디 게임 개발자를 위한 올인원 솔루션 · 인디 개발자의 꿈을 실현

<br />

[문서](https://gameframex.doc.alianblank.com) · [빠른 시작](#빠른-시작) · QQ 그룹: 467608841 / 233840761

<br />

[English](README.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | [日本語](README.ja.md) | **한국어**

</div>

## 언어

[English](README.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | [日本語](README.ja.md) | **한국어**

---

## 프로젝트 개요

Unity용 WebSocket 라이브러리 지원. 이 라이브러리는 주로 `https://github.com/AlianBlank/GameFrameX`의 하위 라이브러리로 사용됩니다.

## 빠른 시작

### 설치

다음 방법 중 하나를 선택하세요:

1. Unity 프로젝트의 `Packages/manifest.json`을 편집하여 `scopedRegistries` 섹션을 추가하세요:
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

   `scopes`는 이 레지스트리를 통해 어떤 패키지를 해석할지 제어합니다. `com.gameframex`로 시작하는 패키지만 이 레지스트리에서 가져옵니다.

2. `manifest.json`의 `dependencies`에 직접 추가:
   ```json
   {
      "com.gameframex.unity.psygames.unitywebsocket": "https://github.com/gameframex/com.gameframex.unity.psygames.unitywebsocket.git"
   }
   ```
3. Unity의 **Package Manager**에서 **Git URL**을 사용하여 추가: `https://github.com/gameframex/com.gameframex.unity.psygames.unitywebsocket.git`
4. 리포지토리를 Unity 프로젝트의 `Packages` 디렉토리에 클론하세요. 자동으로 로드됩니다.
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


## 의존성

| 패키지 | 설명 |
|--------|------|
| (无) | - |


## 문서 및 자료

- [문서](https://gameframex.doc.alianblank.com)

## 커뮤니티 및 지원

- QQ 그룹: 467608841 / 233840761
## 라이선스

자세한 내용은 [LICENSE](LICENSE) 파일을 참조하세요.
