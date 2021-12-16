Q. 출력결과에 맞게 main이 실행될 수 있도록 패키지를 이용해 클래스를 작성하시오.  

```
// 1번문제

public static void main(String[] args) {
  Quiz quiz = new Quiz();
  System.out.println("제한속도= " + quiz.speed_limit() + "km");

// 출력결과
// 제한속도= 60km

// 1번 main()에 이어서 작성
  
  String source = "The old man and the sea";
  System.out.println(quiz.count(source, "he"));
}

// 출력결과 : 문장에 포함된 문자열의 개수
// 2
```

#### My code
```
class Quiz {
	int speed_limit() {
		int n = (int)(Math.random()*4);
		switch(n) {
		case 0:
			return 60;
		case 1:
			return 70;
		case 2:
			return 80;
		case 3:
			return 100;
		}
		return 0;
	}
	
	int count(String src, String hunt) {
		int cnt=0;
		int cut = hunt.length();
		for(int i=0; i<(src.length()-cut+1); i++) {
			if(src.substring(i, i+cut).equals(hunt))
				cnt++;
		}
		return cnt;
	}
}

public class Main {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Quiz quiz = new Quiz();
		System.out.println("제한속도= " + quiz.speed_limit() + "km");
		
		String source = "The old man and the sea";
		System.out.println(quiz.count(source, "he"));
	}
}
```
