---

# Cross-platform 환경 설정 가이드

Windows 기준 (VS Code 및 Git 설치되어 있다고 가정)

---

## 1. Java 설치

### 1-1) 다운로드

[https://adoptium.net/temurin/releases/?version=17](https://adoptium.net/temurin/releases/?version=17)

### 1-2) 설치 확인

```bash
java -version
```

예시 출력:

```
C:\Users\leesc>java -version
openjdk version "17.0.17" 2025-10-21
OpenJDK Runtime Environment Temurin-17.0.17+10 (build 17.0.17+10)
OpenJDK 64-Bit Server VM Temurin-17.0.17+10 (build 17.0.17+10, mixed mode, sharing)
```

➡ 기존 CMD 창을 닫고 새로 열어서 확인해야 적용됨.

---

## 2. Android Studio 설치

### 2-1) 다운로드

[https://developer.android.com/studio?hl=ko](https://developer.android.com/studio?hl=ko)

### 2-2) Android Studio 설정

Android Studio 실행 → **More Actions → SDK Manager**

필수 체크 항목:

* ✔ Android SDK
* ✔ Android SDK Platform
* ✔ Android Virtual Device(AVD) — 필요 시
* ✔ **Android SDK Command-line Tools (중요)**

### 2-3) SDK Path 확인

```
C:\Users\<계정명>\AppData\Local\Android\Sdk
```

### 2-4) 환경 변수 추가

아래 화면 참고:

<img width="922" alt="스크린샷 2025-11-19 154024" src="https://github.com/user-attachments/assets/ce224f6c-3dcc-4d76-935a-60ed6100c37a" />

<img width="746" alt="스크린샷 2025-11-19 154312" src="https://github.com/user-attachments/assets/55fd430b-1b7a-4765-b75f-0cf7542da932" />

---

## 3. Flutter 설치

### 3-1) VS Code 확장 설치

[https://marketplace.visualstudio.com/items?itemName=Dart-Code.flutter](https://marketplace.visualstudio.com/items?itemName=Dart-Code.flutter)

### 3-2) Flutter SDK 설치

VS Code → `Ctrl + Shift + P` → `>flutter` 검색
→ **Flutter: New Project** 실행
→ SDK 설치 안내 나오면 설치 진행

### 3-3) 환경변수 등록

설치 도중 “환경변수 등록” 팝업 → **Yes** 클릭

### 3-4) Flutter Doctor 확인

```bash
flutter doctor
```

### 3-5) Android 라이선스 승인

```bash
flutter doctor --android-licenses
```

→ `y`로 모두 승인

### 3-6) 프로젝트 생성 테스트

```bash
flutter create myapp
cd myapp
flutter run
```

---

## 4. yolo-flutter-app 커스텀 실행

### 4-1) 프로젝트 클론

```bash
git clone https://github.com/ultralytics/yolo-flutter-app.git
```

### 4-2) 예제 프로젝트 실행

```bash
cd yolo-flutter-app/example
flutter pub get
```

브라우저 실행:

```bash
flutter run -d chrome
```

실기기/에뮬레이터 실행:

```bash
flutter run -d <device_id>
```

---

# Android 개발자 옵션 설정

## ✔ 개발자 모드 활성화

1. **설정 → 휴대전화 정보(About phone)**
2. **소프트웨어 정보(Software information)**
3. **빌드 번호(Build number) 7회 연속 터치**
4. PIN 입력
5. “개발자 모드가 활성화되었습니다” 표시

## ✔ USB 디버깅

1. **설정 → 개발자 옵션(Developer options)**
2. **USB 디버깅(USB debugging)** → ON
3. PC 연결 시: “이 컴퓨터를 신뢰하시겠습니까?” → **허용(Allow)**

---

# 주요 명령어

기기 연결 확인:

```bash
adb devices
```

Flutter가 디바이스 인식 확인:

```bash
flutter devices
```

---
