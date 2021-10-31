## 문제 : 다음 조건에 맞춰 단어를 바꿔 출력하시오.
### 조건
1. 단어는 모음으로 시작한다
2. 모음이 아닌 경우 맨뒤에 위치한다
3. 바꾼 단어는 "ay"로 끝난다

### 예외 조건
- 원래 단어가 모음으로 시작할 경우에는 "hay"를 붙여 출력한다  

__Example__ : "boot" -> "ootbay" / "image" -> imagehay"

(play_word 함수를 사용하여 코드 작성)

### 1. 코드
***
<pre>
<code>
# 최종

vowels = ['a','e','i','o','u']

def play_word(x):
  for letter in x:
    x_list.append(letter)
  if x_list[0] in vowels:
    return x + 'hay'
  for i in x_list:
    if i not in vowels:
      x_list.append(i)
      del x_list[0]
    else:
      return ''.join(x_list) + 'ay'
      break
</code>
</pre>

<pre>
<code>
# test code
word1 = 'boot'
word2 = 'image'

print(f'Word1: {word1} -> New word1: {play_word(word1)}')
print(f'Word2: {word2} -> New word2: {play_word(word2)}')
</code>
</pre>

### 2. 문제점
***
- join함수를 사용할 때, "."을 넣지 않아 계속 오류가 났었다.

### 3. 코드 설명
- 문자를 입력받은 그대로 변화를 줄 수 있을지에 대해서 고민을 했다. 지금까지 내가 배운 내용에서는 단어를 list에 넣고 재조합하는 것이 가장 간단한 방법이라고 생각되어 list를 활용한 코드를 작성해보았다.
- for문을 사용해 리스트 내 문자를 다시 조합할 수 있었지만 내장함수를 사용하는 것이 더 간단해서 사용해봤다.
