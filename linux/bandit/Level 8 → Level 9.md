# Bandit Level 8 → Level 9
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once
<br>

7번 문제와 같이 data.txt 파일에 무수히 많은 문자열이 들어있음, 그 중 딱 한번만 출력되는 텍스트 줄을 찾아야 함.<br>

<img width="394" height="554" alt="image" src="https://github.com/user-attachments/assets/459b93c2-281a-4d92-9803-aa2769b13d37" />

sort data.txt | uniq -u 명령어로 빠르게 찾을 수 있음.
<br>
알아본 결과 uniq는 연속된 중복만 처리하기 때문에 sort로 같은 문자열들을 모아 연속 중복 상태로 만들고 uniq로 처리하는 것이다. <br>
+ uniq -u는 횟수가 1회인 문자열만 출력하고, uniq -c는 문자열이 나온 횟수를 보여줌.
<img width="401" height="273" alt="image" src="https://github.com/user-attachments/assets/a53d6445-70fc-42d2-8035-1a6a183da093" />
<br>4CKMh1JI91bUIZZPXDqGanal4xvAg0JM만이 한번 출력된 것을 확인할 수 있음.

- 2026.06.05
