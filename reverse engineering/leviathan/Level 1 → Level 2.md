# Leviathan Level 1 → Level 2
There is no information for this level, intentionally.<br>
이번 문제 또한 아무런 정보를 제공하지 않는다.
<br>ls -al로 확인해보면 check 파일을 확인할 수 있으며, Leviathan2의 권한을 가지고 있음을 확인할 수 있다.<br>
<img width="1002" height="292" alt="image" src="https://github.com/user-attachments/assets/53e5bf9c-bcbf-4552-b4d3-644ea752e2f3" />
<br>
실행해보면 비밀번호를 입력받는 프로그램임을 확인할 수 있다.
<img width="890" height="240" alt="image" src="https://github.com/user-attachments/assets/6d022be7-3ec5-4e6e-8b7a-9b26856dea13" />
ltrace라는 명령어를 이용하면 프로그램의 동작 과정을 확인할 수 있다.<br>
123을 입력하자 실제 비밀번호와 비교하는 것을 확인할 수 있다.<br>
<img width="2306" height="504" alt="image" src="https://github.com/user-attachments/assets/416c0614-31e2-4831-b0dd-2e540467f8ee" />
<br>
비밀번호를 입력하면 Leviathan2의 권한을 얻은 채 shell을 사용할 수 있게 된다<br>
<img width="834" height="218" alt="image" src="https://github.com/user-attachments/assets/79102892-1a52-4602-9512-66b1f989e820" />
<br> 이후  /etc로 이동해 leviathan에 대한 파일을 찾아보면 leviathan_pass를 확인할 수 있다. 
<img width="610" height="316" alt="image" src="https://github.com/user-attachments/assets/0476ce50-6559-4c98-bdd5-a82fb838647c" />
leviathan_pass로 이동해 ls -l로 파일 목록과 권한을 확인해보면 현재 가지고 있는 Leviathan2 권한으로 leviathan2 파일을 열 수 있는 것을 확인할 수 있다.<br>
leviathan2 파일의 내용을 출력하면 비밀번호를 확인할 수 있다.
<img width="1318" height="570" alt="image" src="https://github.com/user-attachments/assets/589b0e60-0723-42b0-8071-64d1a6dd2949" />

- 2026.06.05
