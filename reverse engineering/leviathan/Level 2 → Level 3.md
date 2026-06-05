# Leviathan Level 2 → Level 3
There is no information for this level, intentionally.
이전 문제에서 알아낸 비밀번호로 문제2에 접속한 뒤, 곧바로 ls -al로 파일들을 확인해보면<br>printfile이 Leviathan3의 권한을 가지고 있음을 확인할 수 있다.
<img width="1432" height="364" alt="image" src="https://github.com/user-attachments/assets/e9e4f566-c42d-4bc6-952d-dcd31bad4be6" />
<br>
파일을 실행시켜보면 파일의 내용을 출력하는 프로그램임을 확인할 수 있다.<br>
<img width="736" height="186" alt="image" src="https://github.com/user-attachments/assets/b190b54d-2174-4114-9041-dbe9e3410880" />
<br>곧바로 이를 이용해 /etc/leviathan_pass/leviathan3의 내용의 출력을 시도하면<br>You cant have that file...이라는 문구가 출력된다.( + leviathan2로 시도하면 Permission denied가 뜬다.<br>
<img width="1568" height="144" alt="image" src="https://github.com/user-attachments/assets/8a75ebd7-5ce8-4fe4-a144-adfaafde6495" />
<br>
ltrace로 확인해보면 access 함수를 통해 파일에 접근을 시도한다.<br>
<img width="1728" height="348" alt="image" src="https://github.com/user-attachments/assets/3e500c80-ed12-4516-a0c8-876f2519b13f" />
이에 access 함수가 어떤 동작을 하는지 검색해보았다.
<br> 함수 기능 : 인자로 지정한 파일에 대해 사용자 , 프로세스 접근가능한지 판단하는 시스템호출. 리턴값 : 성공시 0 에러시 -1 리턴<br>이라고 한다.
