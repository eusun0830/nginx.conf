# nginx.conf
nginx configuration files

## nginx.conf
- nginx의 기본적인 설정값을 정의해 놓은 파일

### default
- user: user 지정 (default nobody)
- worker_processes: core 수 지정
- error_log: 에러 로그 위치 및 타입 지정
- pid: master process ID 정보 저장
- worker_rlimit_nofile: 프로세스 당 파일 디스크립터의 상한 갯수

### event block
- event module 정의
- worker_connection: worker 하나가 동시에 처리할 수 있는 접속 수
- multi_accept: on 설정 시 한 번의 복수 접속 허용
- use: 커널이 2.6 이상일 epoll, BSD kqueue

### http block
- web server의 정의
- server_tokens: response header에 nginx 버전 표시
- include /etc/nginx/mime.types: mime 타입 지정
- default_type application/octet-stream: mime 타입에 지정되있지 않은 경우 해당 타입 지정
- log_format: 로그 포맷 지정 main or ltsv
- access_log: 접근 로그 위치 및 타입 지정
- charset: response header에 charset 지정

### upstream
- 하나의 서버에 여러 애플리케이션 서버 구축을 위한 모듈
- server: 포트로 구분한 서버 주소 (weight: 다른 서버 대비 가중치)

## proxy.conf
- proxy 서버 구성을 위한 설정

## fastcgi.conf
- fastcgi 구성을 위한 설정
