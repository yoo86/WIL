## 문제 : pile개의 돌이 플레이어 앞에 놓여있다. 돌을 1 ~ max value 범위 내에서 플레이어들은 가져갈 수 있으며 마지막에 남은 돌을 가져가는 플레이어가 승리한다.   
('play_stones' 함수를 사용하여 코드를 작성)

### 1. 코드
***
<pre>
<code>
# 첫번째 버전
def play_stones(pile, max_stones):

  print(f'There are {pile} stones, and you can choose (1 ~ {max_stones}) stones')
  
  while pile > 0:
    user_num1 = int(input(f'(P1) : How many stones? (1 ~ {max_stones}) '))
    if user_num1 >= 1 and user_num1 <= max_stones:
      pile = pile - user_num1
      print(f'There are {pile} stones left')
      
      while pile > 0:
        user_num2 = int(input(f'(P2) : How many stones? (1 ~ {max_stones}) '))
        if user_num2 >= 1 and user_num2 <= max_stones:
          pile = pile - user_num2
          print(f'There are {pile} stones left')
          
        else:
          print('Invalid choice! Try again')
          
    else:
      print("Invalid choice! Try again")
      
  print('Game over')
</code>
</pre>

<pre>
<code>
# 최종
def play_stones(pile, max_stones):
  print(f'There are {pile} stones, and you can choose (1 ~ {max_stones}) stones')
  
  while pile > 0:
    user_num1 = int(input(f'(P1) : How many stones? (1 ~ {max_stones}) '))
    
    if user_num1 >= 1 and user_num1 <= max_stones:
      pile = pile - user_num1
      
      if pile > 0:
        print(f'There are {pile} stones left')
      else:
        print('Player 1 wins!')
      
      while pile > 0:
        user_num2 = int(input(f'(P2) : How many stones? (1 ~ {max_stones}) '))
        if user_num2 >= 1 and user_num2 <= max_stones:
          pile = pile - user_num2
          if pile > 0:
            print(f'There are {pile} stones left')
            break
          else:
            print('Player 2 wins!')
            
        else:
          print('Invalid choice! Try again')
          
  print('Game over')
</code>
</pre>

input값을 받으면 그 값만큼 pile에서 빼고 pile이 0보다 작아질때까지 반복한다.   

### 2. 문제점
***
- P1은 범위 외의 값을 입력했을 때 다시 입력하라는 문장이 출력되고 다시 입력할 수 있지만 P2는 문장만 출력된 후 P1으로 입력이 넘어간다.
  - 해결 : while문을 하나 더 만들어 P2는 틀리면 다시 입력하라는 문장이 출력되고 다시 입력하고 입력이 완료되면 while문이 break되도록 코드 작성
  
- 위의 문제가 해결되지 않아 아직 누가 우승했는지 출력하는 문장을 코드에 넣지 못했다.
  - 해결 : pile값이 0보다 클 때는 남은 돌 개수를 알려주는 문장을 출력하고 pile값이 0보다 작을 때는 누가 이겼는지 출력한다.
