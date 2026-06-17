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
<br>
mkdir -p /home/sunrin/html으로 디렉터리 생성, docker run -d --name nginx-test -p 80:80 -v /home/$USER/html:/usr/share/nginx/html nginx로 백그라운드에서 nginx 컨테이너를 실행 및 /home/sunrin/html/ 경로를 컨테이너에 마운트 한다.<br>

<img width="1864" height="502" alt="image" src="https://github.com/user-attachments/assets/53f4ed3d-6db7-42f4-b54e-234addbfaa37" />
<br>
이후 localhost로 접속하면 403 Forbidden Error를 확인할 수 있다.<br>
<img width="906" height="404" alt="image" src="https://github.com/user-attachments/assets/190a9cc0-419f-452e-8638-08ec57df5b82" />
해당 오류가 뜨는 이유는 /home/sunrin/html/ 안에 내용물이 없기 때문.<br>echo 명령어로 index.html 파일을 만들면 접속이 잘 되는 것을 볼 수 있다.
<img width="1752" height="466" alt="image" src="https://github.com/user-attachments/assets/ef033ceb-b288-4e7d-8206-9f8518248b25" />

# 과제 2
- 아래 조건에 맞는 compose.yml 파일을 작성하여 제출
    - 3개의 서비스 지원
        - `web`: Flask 기반 웹 애플리케이션
        - `db`: MYSQL 5.7 데이터베이스
        - `nginx`: Reverse Proxy 역할 수행
    - 클라이언트 PC에서 접속 가능한지 확인
 <hr>
과제 수행을 위해 /home/sunrin/server 디렉터리를 생성한다.<br>그 뒤, app.py와 requirements.txt과 이를 참조할 Dockerfile이 들어간 /home/sunrin/server/web 디렉터리를 생성한다.<br>
이후 web 디렉터리 안에 app.py에 해당 내용을 저장한다.

    from flask import Flask

    app = Flask(__name__)

    @app.route("/")
    def home():
        return "Hello Flask + Nginx + MySQL"

    if __name__ == "__main__":
        app.run(host="0.0.0.0", port=5000)
<br>
nano /home/sunrin/server/web/requirements.txt 에는

    flask

/home/sunrin/server/web/Dockerfile 에는 

    FROM python:3.11-slim

    WORKDIR /app

    COPY requirements.txt .
    RUN pip install -r requirements.txt

    COPY . .

    CMD ["python", "app.py"]

그 뒤, nginx를 설정할 /home/sunrin/server/nginx 디렉터리를 생성한다.
<br>/home/sunrin/server/nginx/default.conf 를 생성한 뒤 해당 내용을 저장한다.

    server {
        listen 80;

        location / {
            proxy_pass http://web:5000;

            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
        }
    }

다음으로 /home/sunrin/server/compose.yml 에는 해당 내용을 저장한다.

    services:
      web:
        build: ./web
        container_name: flask_web
    
      db:
        image: mysql:5.7
        container_name: mysql_db
        restart: always
        environment:
          MYSQL_ROOT_PASSWORD: 1234
          MYSQL_DATABASE: testdb
        volumes:
          - mysql_data:/var/lib/mysql
    
      nginx:
        image: nginx:latest
        container_name: nginx_proxy
        ports:
          - "80:80"
        volumes:
          - ./nginx/default.conf:/etc/nginx/conf.d/default.conf:ro
        depends_on:
          - web
    
    volumes:
      mysql_data:

/home/sunrin/server으로 이동한 뒤, docker compose up -d로 docker compose에 정의된 서비스를 생성하고 실행한다.

<img width="2304" height="1098" alt="image" src="https://github.com/user-attachments/assets/b21c5c1f-63a0-418d-b7a6-a9b4b2b84033" />

해당 과정을 거쳐 서비스의 생성 및 실행이 완료되면 

<img width="2338" height="660" alt="image" src="https://github.com/user-attachments/assets/d25c04c0-b2cf-4e52-b1f0-98c138450a1e" />

docker ps로 확인했을 때 3개의 컨테이너가 생성된 것을 볼 수 있다.
<br>localhost를 확인하면 Hello Flask + Nginx + MySQL가 출력되며, 클라이언트 pc에서 접속시 Hello Flask + Nginx + MySQL가 출력되는 페이지를 확인할 수 있다.
<img width="1270" height="126" alt="image" src="https://github.com/user-attachments/assets/eb6ecda8-9a0a-4b5c-b6c7-319233f3ecd8" />

<img width="1178" height="498" alt="image" src="https://github.com/user-attachments/assets/dc6d9659-bc02-4ca4-87d8-85fefd786e12" />

# 과제 3
### 나만의 컨테이너 만들기

- 원하는 서비스가 담긴 컨테이너를 Docker 이미지로 직접 빌드하고 docker-compose를 활용하여 실행
- Dockerfile 작성 및 docker-compose.yml 등 구성 과정을 캡처하여 제출
<hr>
