The password for the next level is stored in a file called - located in the home directory
이전 문제에서 찾아낸 비밀번호로 bandit1에 접속 - ssh bandit1@bandit.labs.overthewire.org -p 2220
이후 - 파일에 저장된 비밀번호 출력하기

<img width="833" height="560" alt="image" src="https://github.com/user-attachments/assets/d970497b-2b83-49a6-a85e-9fb99fb22317" />

<img width="324" height="92" alt="image" src="https://github.com/user-attachments/assets/644dd394-687e-475a-b24b-245b839622b5" />

접속한 뒤 ls 명령어로 - 파일을 확인했지만 cat 명령어로 내용이 출력되지 않음

문제 페이지에 Google Search for “dashed filename” 라고 써져있는 것을 보고 dashed filename를 검색함.
찾아본 결과 ./-와 같이 경로를 입력하면 출력이 되는 것을 확인

<img width="501" height="114" alt="image" src="https://github.com/user-attachments/assets/b29a5043-0afa-4bc0-9b72-cc549db019ee" />

-2026.06.04
