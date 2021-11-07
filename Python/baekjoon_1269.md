![image](https://user-images.githubusercontent.com/93065107/140655007-19703f77-c22d-40f9-b98e-d06fc601a23d.png)
이 문제는 차집합을 구하기 때문에 set 함수를 사용하는 것이 편하다.  
a, b 집합의 원소를 따로 입력받는 부분만 오류가 나지 않게 작성하면 될 것 같다.

### 1. 코드
***
<pre>
<code>
a, b = map(int, input().split())
a_set = set(map(int, input().split()))
b_set = set(map(int, input().split()))
print(len(a_set - b_set) + len(b_set - a_set))
</code>
</pre>
1. map함수는 map(function, iterable) -> function에 iterable에 적용될 함수를 넣고, iterable에는 list, tuple, string 형태가 들어간다. 이 함수를 사용해 입력을 받았다.
2. 대칭 차집합의 길이를 구하는 것이 이 문제의 핵심이기 때문에 print할 때 len 함수로 길이를 출력하였다.
