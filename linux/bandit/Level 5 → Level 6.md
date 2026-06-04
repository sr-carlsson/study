#Bandit Level 5 → Level 6
이전 문제에서 알아낸 비밀번호로 5번 문제에 접속.
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

human-readable <br>
1033 bytes in size <br>
not executable

<img width="847" height="166" alt="image" src="https://github.com/user-attachments/assets/e438e642-c306-45b5-8c27-a7afe4301979" />

문제에 적힌것과 같이 1033 byte의 파일을 찾아야함.

find 명령어로 검색. find 현재위치(./) -size 1033c(1033byte인 파일 검색)
<img width="566" height="122" alt="image" src="https://github.com/user-attachments/assets/6ecd484c-97ca-45e1-9300-1adf014c830c" />

<img width="674" height="131" alt="image" src="https://github.com/user-attachments/assets/da43b4e5-2104-4fe8-92ef-b68cd11504d1" />


검색할 때 c가 byte를 의미하는 것을 처음 알게 됨.

- 2026.06.04
