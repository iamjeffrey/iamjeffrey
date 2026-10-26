# [Capacitor + Vue] 현대적인 모바일 앱 개발 환경 및 명령어 가이드
- Ionic CLI 최신 트렌드, npx 활용, 불필요해진 구형 도구 대체, Vite 기반 `npm run dev` 권장,
  Capacitor PWA Elements 등  **현대적인 Capacitor(V8~) + Vue 개발 환경** 구축 핵심 팁

## 1. 사전 환경 확인 명령어

현재 시스템에 설치된 주요 도구들의 버전 확인

```powershell
ionic --version
npm view @ionic/cli version
npm list -g typescript --depth=0
tsc -v

```

---

## 2. 프로젝트 생성: 글로벌 설치 vs `npx` (권장)

### ❌ 과거 방식 (Global 설치 후 실행)

```powershell
npm install -g @ionic/cli
ionic start myApp tabs --type vue

```

* **단점:** 시스템 글로벌 디렉터리에 고정 바이너리가 영구 잔류하며, 버전을 갱신하려면 수동으로 `npm update -g @ionic/cli` 실행 필요

### ⭕ [권장] 최신 npx 일회성 실행 방식

```powershell
npx @ionic/cli start my-capacitor-app tabs --type=vue --capacitor

```

* **장점:**
* 사전 설치가 필요 없음
* npx 캐시 공간에 임시 다운로드 후 실행
* 매 실행 시 최신 공식 버전을 동적으로 조회하여 실행하므로 항상 최신 상태 유지
* 실행 후 로컬에 불필요한 전역 패키지가 남지 않음



---

## 3. 이제 쓰지 않는 구형 도구들 (과감한 생략)

Capacitor 최신 버전(3 이상) 환경에서는 아래 구형 도구들을 더 이상 설치할 필요가 없습니다.

1. **`native-run` (불필요)**
* 과거 에뮬레이터나 기기로 앱을 띄우던 도구입니다.
* **현재:** Capacitor CLI 자체의 `run` 명령어로 완전히 통합되었습니다.


2. **`cordova-res` (대체됨)**
* Cordova 시절부터 쓰이던 구형 아이콘/스플래시 생성 도구입니다. 최신 Android Adaptive Icon이나 최신 iOS 해상도 규격을 지원하지 못합니다.
* **현재:** 공식 도구인 `@capacitor/assets`를 프로젝트 로컬 패키지로 설치해 사용합니다.
```powershell
# 1. 로컬 패키지 설치
npm install -D @capacitor/assets

# 2. assets/icon.png, assets/splash.png 준비 후 리소스 자동 생성
npx capacitor-assets generate

```



---

## 4. 개발 서버 구동: `ionic serve` vs `npm run dev`

| 구분 | `ionic serve` | `npm run dev` (**권장**) |
| --- | --- | --- |
| **특징** | Ionic CLI가 감싸서 실행 | Vite 개발 서버 직접 구동 |
| **필수 여부** | `@ionic/cli` 전역 설치 필요 | 불필요 (`package.json` 스크립트 이용) |
| **장점** | Ionic Lab(`--lab`), 브라우저 자동 오픈 등 부가 기능 제공 | 훨씬 빠르고 가벼운 HMR(Hot Module Replacement) 지원 |

---

## 5. 기타 유용한 명령어 및 팁

* **지원하는 스타터 템플릿 목록 확인:**
```powershell
ionic start --list

```


* **Capacitor 플러그인의 웹 지원 (`@ionic/pwa-elements`):**
* 카메라, 사진첩 등 상당수의 Capacitor 플러그인은 웹 브라우저에서 실행될 때 자체 UI가 없어 에러가 발생할 수 있습니다.
* 브라우저 환경에서도 동일한 UI(파일 업로드, 카메라 모달 등)를 띄우려면 PWA Elements를 설치해야 합니다.


```powershell
npm install @ionic/pwa-elements

```



---
