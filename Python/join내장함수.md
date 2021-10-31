### 리스트 내 문자열 합치는 방법 2가지
***
__1. for문 이용__
- 이 방식을 이용하면 숫자와 문자 둘 다 합쳐서 출력하는 것이 가능하다.  

<pre>
<code>
lst = ['H','e','l','l','o']
for i in range(len(lst)):
  print(lst[i], end = ' ')

# 출력 : H e l l o
</code>
</pre>

__2. join 내장함수 사용__
- 문자가 아닌 원소들로 이루어진 리스트의 경우 join 함수 사용이 불가능하다.  

<pre>
<code>
lst = [1,2,3,4,5,6,7,8,9]
print(' '.join(lst))
# TypeError: sequence item 0: expected str instance, int found
# 에러 발생
</code>
</pre>

<pre>
<code>
lst = ['H','e','l','l','o']
print(' '.join(lst))

# 출력 : H e l l o
</code>
</pre>
