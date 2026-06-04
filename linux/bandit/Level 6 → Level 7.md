#Bandit Level 6 → Level 7
이전 문제에서 알아낸 비밀번호로 6번 문제 접속.<br>
The password for the next level is stored somewhere on the server and has all of the following properties:<br>

owned by user bandit7 <br>
owned by group bandit6<br>
33 bytes in size


find로 조건에 맞게 검색했지만 수많은 에러 메시지가 나타나 원하는 파일을 찾기 어려움.

<img width="952" height="528" alt="image" src="https://github.com/user-attachments/assets/e74049f9-6100-40c0-be4f-64af861bea22" />

명령어에 권한 오류 메세지를 숨기는 2>/dev/null를 추가하여 find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null를 입력하게 되면 권한 오류 메시지를 제외한, 파일 위치만을 볼 수 있음.
<img width="785" height="86" alt="image" src="https://github.com/user-attachments/assets/b4884ac6-9af7-4669-be0d-2f68c0ab4e66" /><br>
이후 찾은 파일을 cat으로 출력.
<img width="552" height="76" alt="image" src="https://github.com/user-attachments/assets/229132e8-cc29-4950-bf38-db557580c7b4" />

- 2026.06.05
