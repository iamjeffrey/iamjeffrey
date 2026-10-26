

native-run (불필요)
과거 Ionic CLI가 기기/에뮬레이터로 앱을 바로 띄울 때 사용하던 도구입니다. Capacitor 3 버전 이후부터는 Capacitor CLI 자체의 run 명령어로 완전히 통합되었습니다.

npm install -g @ionic/cli native-run cordova-res
Cordova 시절부터 쓰이던 구형 리소스 생성 도구로, Capacitor 공식 도구인 @capacitor/assets로 완전히 대체되었습니다. 
최신 모바일 OS(Android Adaptive Icon, 최신 iOS 해상도 규격)를 지원하지 못합니다.

프로젝트 로컬 패키지로 @capacitor/assets를 설치해 사용합니다.
npm install -D @capacitor/assets
