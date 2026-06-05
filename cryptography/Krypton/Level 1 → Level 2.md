# Krypton Level 1 → Level 2
The password for level 2 is in the file ‘krypton2’. It is ‘encrypted’ using a simple rotation. It is also in non-standard ciphertext format. When using alpha characters for cipher text it is normal to group the letters into 5 letter clusters, regardless of word boundaries. This helps obfuscate any patterns. This file has kept the plain text word boundaries and carried them to the cipher text. Enjoy!
<br>
1번 문제 디렉터리로 이동한 뒤, ls로 파일들을 확인해보면 다음 문제의 비밀번호가 적힌 krypton2 파일을 확인할 수 있다.
<img width="902" height="190" alt="image" src="https://github.com/user-attachments/assets/3920a313-de1e-40c2-94e7-f9fdc6006d59" />
<br>cat으로 krypton2 파일을 출력해보면 다음과 같은 문자열을 확인할 수 있다.<br>
<img width="970" height="122" alt="image" src="https://github.com/user-attachments/assets/443df3fa-0aca-45f1-9739-d149cda6a134" />
<br>
이후 README 파일의 내용을 출력해보면 ROT13을 사용했다고 적혀있다.<br>
<img width="1584" height="932" alt="image" src="https://github.com/user-attachments/assets/1f507a25-4d21-41b5-ae30-76f41d6ad7d6" />
<br>
https://rot13.com/ 에 접속하면 다음과 같은 페이지를 확인할 수 있다<br>
<img width="1496" height="1430" alt="image" src="https://github.com/user-attachments/assets/9bd72354-4bfa-4bc5-a679-9dfc8230a463" />
<br>
해당 사이트에 krypton2의 내용을 입력하면 LEVEL TWO PASSWORD ROTTEN 이라는 문자열이 반환된다.<br>
<img width="1602" height="1354" alt="image" src="https://github.com/user-attachments/assets/87542743-937e-4e95-b2b1-da66fb0a4640" /><br>
- 2026.06.05 
