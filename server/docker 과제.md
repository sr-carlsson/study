# 과제 1
- 각 단계의 문제를 해결하고, 해결에 사용된 명령어 또는 해결 방법을 작성하여 제출
    - Docker
        - Ubuntu 20.04 이미지를 이용하여 이름이 test-ubuntu-2004인 컨테이너를 만들고 /bin/bash에 접속
        - test-ubuntu-2004 컨테이너를 정지하지 않은 상태로 /bin/bash를 빠져나온 후 다시 컨테이너에 /bin/bash로 접속
        - /home/$USER/html/ 경로를 nginx 컨테이너에 마운트하여 빌드
        - 403 Forbidden Error 해결
- 아래 조건에 맞는 Dockerfile을 작성하여 제출
    - app.py와 requirements.txt를 참조하여 Dockerfile을 작성하고, port 3001로 Flask 웹 서버 실행
        - **컨테이너 이름**: docker-flask
        - **작업 디렉터리**: /usr/src/app
    - docker run을 이용하여 /home/$USER/sunrin-server/lab01-dockerfile/templates와 /usr/src/app/templates를 마운트
<hr>
docker run -it --name test-ubuntu-2004 ubuntu:20.04 /bin/bash 명령으로 test-ubuntu-2004 컨테이너를 생성함과 동시에 /bin/bash에 접속한다.

<img width="1698" height="180" alt="image" src="https://github.com/user-attachments/assets/60956ba7-8c05-47be-9dad-cb4adfadaaac" />
<br>이후 Ctrl + P, Ctrl + Q를 입력하면 /bin/bash를 빠져나올 수 있다.<br>docker ps로 아직 컨테이너가 실행 중인 것을 확인할 수 있다.<br>
<img width="1832" height="260" alt="image" src="https://github.com/user-attachments/assets/b63c5909-6a81-4f88-a704-3a82af640900" />
<br> docker exec -it test-ubuntu-2004 /bin/bash로 다시 컨테이너에 /bin/bash로 접속한다.
<img width="1532" height="166" alt="image" src="https://github.com/user-attachments/assets/6bf8725c-3d33-4e79-a1df-a07c2b0637f6" />

# 과제 2
- 아래 조건에 맞는 compose.yml 파일을 작성하여 제출
    - 3개의 서비스 지원
        - `web`: Flask 기반 웹 애플리케이션
        - `db`: MYSQL 5.7 데이터베이스
        - `nginx`: Reverse Proxy 역할 수행
    - 클라이언트 PC에서 접속 가능한지 확인
 <hr>

# 과제 3
### 나만의 컨테이너 만들기

- 원하는 서비스가 담긴 컨테이너를 Docker 이미지로 직접 빌드하고 docker-compose를 활용하여 실행
- Dockerfile 작성 및 docker-compose.yml 등 구성 과정을 캡처하여 제출
<hr>
