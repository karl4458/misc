# docker 컨테이너 안에서 GUI프로그램 실행하고 호스트에서 인터페이스 띄우기
## 1.xhost 사용해서
## 2. x virtual frame buffer 사용해서 가상 모니터만들고 vnc로 송출
xvfb , vnc 설치
Xvfb :1 -screen 0 1024x768x16 &
fluxbox &
x11vnc -display :1 -bg -forever -nopw -quiet -listen 0.0.0.0 -xkb &



스크린 번호 export DISPLAY=:1 로 환경변수에 저장하면 모든 GUI프로그램이 알아서 전송함.
x11vnc는 5900번 포트를 사용하고 호스트 os의 vnc client와 연결될 수 있도록 localhost가 아닌 0.0.0.0으로 리스닝하기.
