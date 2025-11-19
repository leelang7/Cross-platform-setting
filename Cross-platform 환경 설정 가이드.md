<Cross-platform 환경 설정 가이드>

Windows 기준, VS Code 및 Git은 설치되어 있다고 가정

1. Java 설치

   1-1) https://adoptium.net/temurin/releases/?version=17

   1-2) 설치 확인

   ```
   java -version
   ```

   ```
   C:\Users\leesc>java -version
   openjdk version "17.0.17" 2025-10-21
   OpenJDK Runtime Environment Temurin-17.0.17+10 (build 17.0.17+10)
   OpenJDK 64-Bit Server VM Temurin-17.0.17+10 (build 17.0.17+10, mixed mode, sharing)
   ```

   기존의 cmd창을 끄고 새로 켠 후 확인해서 위와 같이 나오면 잘 설치 된 것

   

2.  Android Studio 설치

   2-1) https://developer.android.com/studio?hl=ko 에서 다운로드 후 설치

   2-2) Android Studio 실행 → More Actions → SDK Manager

   ​      **설치 시 반드시 체크할 것**

   ​    ✔ Android SDK
   ​    ✔ Android SDK Platform
   ​    ✔ Android Virtual Device(AVD) → 필요시
   ​    ✔ Android SDK Command-line Tools (중요)
   

   2-3) SDK path 확인(보통 아래와 같음)

   ```
   C:\Users\<계정명>\AppData\Local\Android\Sdk
   ```


   2-4) 환경 변수 추가

<img width="922" height="1081" alt="스크린샷 2025-11-19 154024" src="https://github.com/user-attachments/assets/ce224f6c-3dcc-4d76-935a-60ed6100c37a" />

<img width="746" height="1520" alt="스크린샷 2025-11-19 154312" src="https://github.com/user-attachments/assets/55fd430b-1b7a-4765-b75f-0cf7542da932" />



3. Flutter 설치

   3-1) https://marketplace.visualstudio.com/items?itemName=Dart-Code.flutter

   ​       접속하면 VS code의 확장팩으로 설치됨

   3-2 ) VS code에서 Control + Shift + P를 하면  '>' flutter를 검색하면 3가지가 출력되는데 Flutter: New Project를 선택하면 SDK 경고 문구가 출력되면 설치 진행

   3-3) 환경변수 등록 문구가 나오면 yes를 누르면 편함.

   3-4) cmd 창을 끄고 다시 켠 후 flutter doctor를 실행하면 진단 정보가 출력됨. 혹시 놓친 부분이 있더라도 다시 설치하면됨

   3-5) Android 라이선스 승인

   ```
   flutter doctor --android-licenses
   ```

   y로 모두 승인

   3-6) 프로젝트 생성 테스트(반드시 알맞은 경로에서 flutter 명령어 실행)

   ```
   flutter create myapp
   ```

   ```
   cd myapp
   ```

   ```
   flutter run
   ```



4. yolo-flutter-app 커스텀

   4-1) 프로젝트 클론 및 임베딩

   ```
   git clone https://github.com/ultralytics/yolo-flutter-app.git
   ```

   ```
   cd yolo-flutter-app\example
   ```

   ```
   flutter pub get
   ```

   ```
   flutter run -d chrome # 크롬
   ```

   ```
   flutter run -d <device ID> # 디바이스 및 에뮬레이터
   ```



※ 개발자 옵션 설정

✔ 개발자 모드 활성화

1. **설정 → 휴대전화 정보(About phone)**
2. **소프트웨어 정보(Software information)** 또는 **빌드 번호(Build number)**
3. **빌드 번호 7회 연속 터치**
4. PIN 입력
5. “개발자 모드가 활성화되었습니다” 문구 뜸

------

✔ USB 디버깅 켜기

1. 설정 → **개발자 옵션(Developer options)**

2. **USB 디버깅(USB debugging)** → ON

3. PC에 USB로 연결하면:

   - “이 컴퓨터를 신뢰하시겠습니까?” → **허용(Allow)** 클릭

     

✔ 주요명령어(Updating...)

```
adb devices # 실기기 연결 확인
```

```
flutter devices # Flutter가 폰을 인식하는지 확인
```



