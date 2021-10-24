![2004](https://user-images.githubusercontent.com/93065107/138590918-08fe5911-cb39-4a9f-9017-63f869423b71.PNG){: width = "100" height = "70"}

조합 0의 개수를 구하는 문제에 대해 고민해봤다.   
nCm = n!/(m!(n-m)!) 이라는 공식 자체에 초점을 두고 코드를 작성했다.

### 코드
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
</code>
</pre>

for문을 활용해 mul 함수를 정의하여 팩토리얼(!)을 계산하였다.   
조합 공식을 이용한 결과값을 cal에 넣어주고 cal의 값을 자릿수별로 나누어 a에 넣었다.   
리스트 a의 값을 reverse하여 0의 개수를 세는 방법으로 코드를 작성했다.   

### 문제점
***
값을 입력받아서 계산을 해야되는데 n과 m의 값을 input()으로 바꿔서 코드를 실행시키면 오류가 발생했다.

