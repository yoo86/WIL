Q. 다음처럼 입력시 출력되도록 하시오.  
입력 : 3 5 7  
출력 : 7 5 3

#### My code
```
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		Scanner sc = new Scanner(System.in);
	
		System.out.println("a");
		int a = sc.nextInt();
		
		System.out.println("b");
		int b = sc.nextInt();
		
		System.out.println("c");
		int c = sc.nextInt();
		
		System.out.println(c);
		System.out.println(b);
		System.out.println(a);
		
		sc.close();
	}
}
```

#### Professor
```
import java.util.Scanner;

public class Answer {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		System.out.println("변수 실습과제");
		
		System.out.println("세개의 숫자 입력 (한칸씩 띄어서)");
		Scanner sc = new Scanner(System.in);
		int data1 = sc.nextInt();
		int data2 = sc.nextInt();
		int data3 = sc.nextInt();
		
		System.out.println(data3 + " " + data2 + " " + data1);
		
		sc.close();
	}
}
```
