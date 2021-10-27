![2004](https://user-images.githubusercontent.com/93065107/138590918-08fe5911-cb39-4a9f-9017-63f869423b71.PNG)

조합 0의 개수를 구하는 문제에 대해 고민해봤다.   
nCm = n!/(m!(n-m)!) 이라는 공식 자체에 초점을 두고 코드를 작성했다.

### 1. 코드
***
<pre>
<code>
n = 25
m = 12
cal = []

def mul(n):
  ans = 1
  for i in range(1,n+1):
    ans *= i
  return ans

cal = mul(n)//(mul(m)*mul(n-12))
a = list(map(int,str(cal)))
a.reverse()

result = []
for k in a:
  if k == 0:
    result.append(k)
  else:
    break

print(result.count(0))
</code>Cancel changes
</pre>

for문을 활용해 mul 함수를 정의하여 팩토리얼(!)을 계산하였다.   
조합 공식을 이용한 결과값을 cal에 넣어주고 cal의 값을 자릿수별로 나누어 a에 넣었다.   
리스트 a의 값을 reverse하여 0의 개수를 세는 방법으로 코드를 작성했다.   

### 2. 문제점
***
- 값을 입력받아서 계산을 해야되는데 n과 m의 값을 input()으로 바꿔서 코드를 실행시키면 오류가 발생했다.
![오류발생](https://user-images.githubusercontent.com/93065107/138591929-6f880a29-f385-436c-9f38-42bf244140c4.PNG)
  - 오류 발생 이유 : input으로 입력받으면 입력받은 값은 String타입으로 인식한다. 따라서, 입력받은 값을 타입변환하는 과정이 필요하다.  


- 예제에 나와있는 25와 12를 넣었을 땐 값이 잘 나오는데 다른 경우에는 값이 나오지 않는 경우가 있다.   

ex) n을 25로 하고 m을 14로 바꾸면 결과값이 4,457,400에서 총 0이 2개이므로 2가 나와야되는데 결과값으로 0이 나온다.

### 3. 과제
- 오류가 발생하는 원인을 이해하고 수정을 한다.
- 예제를 제외한 다른 경우에도 정확한 값이 나올 수 있도록 식을 수정한다.
- 모든 것이 해결되면 더 효율적인 방법을 생각해본다.
