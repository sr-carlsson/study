https://dreamhack.io/wargame/challenges/3004

<img width="1172" height="972" alt="image" src="https://github.com/user-attachments/assets/835da27c-94ef-46fd-afb3-2e4db9909ca3" />
fgets으로 s에 문자열을 입력받음<br> s를 v4에, s의 길이를 v6에 저장함.<br>
이후 if문으로 v6가 340자인지 확인, 맞다면 for문으로 진입<br>
 v4 = &s[2 * i];로 s를 2글자씩 자름.<br>
  __isoc23_sscanf(v4, "%2hhx", (char *)&vm + i + 1088);로 2글자씩 자른 문자들을 16진수 형태의 1바이트 형태로 변환, 변환한 값을 vm이라는 배열에 i + 1088번째 배열에 지정.<br>
  
