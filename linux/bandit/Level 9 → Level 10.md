# Bandit Level 9 → Level 10
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.<br>
이전 문제에서 알아낸 비밀번호로 9번 문제에 접속.
<br> 몇 안 되는 사람이 읽을 수 있는 문자열 중 하나에 저장되어 있으며, 앞에는 여러 개의 '=' 문자가 붙어있다고 함.
<br>
텍스트 양이 적어 명령어 없이도 찾을 수는 있음.
<img width="1218" height="312" alt="image" src="https://github.com/user-attachments/assets/1da8be08-f216-4760-9817-366f80c32c75" />
<br>

하지만 리눅스 명령어를 익히는 것이 목적이기에 명령어를 이용해 찾아봄, 우선 grep으로 찾으려 해봤지만 바이너리 파일이기에 먹히지 않음.<br>
<img width="886" height="226" alt="image" src="https://github.com/user-attachments/assets/a9cdd829-0dbf-4a05-a64c-1534a0518f3b" />
<br>
이때 grep -a 옵션을 사용하면 바이너리 파일을 텍스트 파일처럼 처리하여 찾아낼 수 있음.
<br>
<img width="2328" height="1094" alt="image" src="https://github.com/user-attachments/assets/151cc6ed-8c85-4b44-a751-1547485031f9" />

- 2026.06.05
