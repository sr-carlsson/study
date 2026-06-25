https://dreamhack.io/wargame/challenges/2650

<img width="1058" height="1572" alt="image" src="https://github.com/user-attachments/assets/f3817588-8940-4c1f-ba64-351a22dcc61b" />
<img width="1382" height="1234" alt="image" src="https://github.com/user-attachments/assets/e871929f-804f-446e-ba8c-39111aa08715" />
<br>scanf로 s에 문자열을 입력받은 뒤 문자열의 길이가 59라면 dest에 s를 복사<br>
for문으로 순회하며 dest[i]에 ^= (v5 + I) 계산이후 dest == Please_input_the_correct_new_year_greetings_at_this_problem라면 플래그를 출력하는 코드
<br>
<br>v5[0]부터 v7의 값을 key로 저장한뒤, Please_input_the_correct_new_year_greetings_at_this_problem를
dest로 두고 for문으로 (dest[i] ^ key[i])을 반복하는 코드를 짜면 플래그를 얻어낼 수 있다. <br>
코드를 실행하면 Happy_new_2026_I_love_you_and_dreamhack_lets_happy_together 라는 결과값을 얻어낼 수 있다.<br>

```python
dest = b"Please_input_the_correct_new_year_greetings_at_this_problem"

v6 = bytearray(11)
v6[0:4] = (738656770).to_bytes(4, "little")
v6[3:11] = (0x2C1018043E1C3E2C).to_bytes(8, "little")

key = (
    (0xC313A0A11150D18).to_bytes(8, "little") +
    (0x2C37426D44472F19).to_bytes(8, "little") +
    (0x1B1A3A1704000F00).to_bytes(8, "little") +
    (0x1301263B1904312A).to_bytes(8, "little") +
    (0x361F06041A0A3E17).to_bytes(8, "little") +
    bytes(v6) +
    (0x1F0004160A151F2B).to_bytes(8, "little")
)

flag = ""

for i in range(len(dest)):
    flag += chr(dest[i] ^ key[i])

print(flag)
```
이를 실행하면 다음과 같은 결과가 나온다.
<img width="1086" height="290" alt="image" src="https://github.com/user-attachments/assets/53a06372-8cdf-4328-a75e-c304e6a37d6f" />

