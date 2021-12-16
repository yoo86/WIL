Q. 아스키 코드표를 출력하세요.  
(단, 한 줄에 16개씩 수평으로 출력하고, 공백문자(32번)부터 마지막 번호는 키입력 받아 출력합니다.)  

ex)  
입력 : 63
출력 :  
 !"#$%&'()*+,-./  
0123456789:;<=>?

#### My code (아스키 코드표를 63까지 출력하고 번호를 입력했을 때 해당 번호의 코드를 출력하는 것으로 잘못 이해한 코드)
```
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		for(char a=32; a<64; a++) {
			System.out.print(a);
			
			if(a%16 == 15)
				System.out.println();
		}
		Scanner sc = new Scanner(System.in);
		int b = sc.nextInt();
		char c = (char)b;
		System.out.println(c);
		
	}
}
```

#### 문제에서 원한 코드
```
import java.util.Scanner;

public class Answer_1 {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		Scanner sc = new Scanner(System.in);
		System.out.println("ASCII출력 끝 번호 입력");
		int end = sc.nextInt();
		
		for(int i=32; i<end; i++) {
			System.out.print((char)i + " ");
			if((i+1)%16 == 0)
				System.out.println();
		}
		sc.close();
	}
}
```
