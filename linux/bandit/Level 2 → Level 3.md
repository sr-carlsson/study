# Bandit Level 2 → Level 3
The password for the next level is stored in a file called --spaces in this filename-- located in the home directory
이전 문제에서 찾은 비밀번호로 2번 문제에 접속
--spaces in this filename--이라는 이름의 파일에 저장된 비밀번호 찾기

<img width="537" height="143" alt="image" src="https://github.com/user-attachments/assets/3e08ae70-496c-41a3-aca4-968e3b552e94" />

이후 - 파일과 같이 cat --spaces in this filename-- 만으로는 출력이 되지 않는 것을 확인.
문제에 Google Search for “spaces in filename” 라고 적힌대로 spaces in filename 검색.

출력이 되지 않는 이유는 터미널이 네 개의 다른 파일( --spaces, in, this, filename--)로 각각 분리해서 생각하기 때문에 띄어쓰기 들어간 파일을 읽으려고 하면 에러가 생긴다는 것을 알게 됨.

<img width="577" height="154" alt="image" src="https://github.com/user-attachments/assets/65eae75a-f4f0-4ce9-ae3d-8909b8243c9a" />

cat "./--spaces in this filename--"으로는 내용이 출력되지만 cat "--spaces in this filename--"은 오류가 나오는 이유가 궁금해 더 알아봄.
이유는 따옴표가 인자들을 하나로 묶는 역할만 하고 --가 옵션으로 인식되는 문제는 해결을 해주지 않는다고 함.

- 2026.06.04
