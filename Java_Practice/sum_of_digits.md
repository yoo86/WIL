Q. 키보드로부터 최대 세자리의 정수를 입력받습니다. 자릿수들의 합계는 얼마입니까? (2자리, 1자리도 가능해야 된다)
ex) 입력(3자리) -> 1 2 3
    출력        -> 자릿수 합계 : 6
    
#### My code
```
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		System.out.println("최대 세자리의 정수를 입력하세요");
		Scanner sc = new Scanner(System.in);
		int input = sc.nextInt();
		
		int a = input/100;
		int b = (input%100)/10;
		int c = (input%100)%10;
		int sum = a+b+c;
		
		System.out.println("자릿수 합계 : " + sum);
		sc.close();
	}
}
```

#### Professor

```
import java.util.Scanner;

public class Answer_1 {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		System.out.println("최대 세자리의 정수를 입력하세요> ");
		Scanner sc = new Scanner(System.in);
		int input = sc.nextInt();
		sc.close();
		
		int a = input/100;
		int b = (input%100)/10;
		int c = (input%100)%10;
		int sum = a + b + c;
		
    /*
    자릿수를 이 방법으로도 나눌 수 있음
    int a = input/100;
		int b = (input - a*100)/10;
		int c = (input - a*100 - b*10);
		int sum = a + b + c;
    */
    
		System.out.println("자릿수의 합계는: " + sum);
	}
}
```
