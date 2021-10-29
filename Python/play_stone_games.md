문제 : pile개의 돌이 플레이어 앞에 놓여있다. 돌을 1 ~ max value 범위 내에서 플레이어들은 가져갈 수 있으며 마지막에 남은 돌을 가져가는 플레이어가 승리한다.   
('play_stones' 함수를 사용하여 코드를 작성)

### 1. 코드
***
<pre>
<code>
def play_stones(pile, max_stones):
  print(f'There are {pile} stones, and you can choose (1 ~ {max_stones}) stones')
  while pile > 0:
    user_num1 = int(input(f'(P1) : How many stones? (1 ~ {max_stones}) '))
    if user_num1 >= 1 and user_num1 <= max_stones:
      pile = pile - user_num1
      print(f'There are {pile} stones left')

      user_num2 = int(input(f'(P2) : How many stones? (1 ~ {max_stones}) '))
      if user_num2 >= 1 and user_num2 <= max_stones:
        pile = pile - user_num2
        print(f'There are {pile} stones left')
      elif user_num2 <= 1 and user_num2 >= max_stones:
        print('Invalid choice! Try again')
    else:
      print("Invalid choice! Try again")
      
  print('Game over')
  
</code>
</pre>

input값을 받으면 그 값만큼 pile에서 빼고 pile이 0보다 작아질때까지 반복한다.   

### 2. 문제점
***
- P1은 범위 외의 값을 입력했을 때 다시 입력하라는 문장이 출력되고 다시 입력할 수 있지만 P2는 문장만 출력된 후 P1으로 입력이 넘어간다.
- 위의 문제가 해결되지 않아 아직 누가 우승했는지 출력하는 문장을 코드에 넣지 못했다.