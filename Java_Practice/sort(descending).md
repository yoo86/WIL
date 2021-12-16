Q. 세 개의 정수를 내림차순으로 정렬합니다. 정렬에 필요한 숫자는 모두 입력받습니다.  
ex)  
정수(3개) : 31 19 77
내림차순 : 77 31 19

#### My code (가독성이 떨어지고, 정수의 개수가 늘어났을 때는 사용불가능한 코드로 작성함)
```
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		
		System.out.println("세개의 정수를 입력하세요(한칸씩 띄어서): ");
		
		Scanner sc = new Scanner(System.in);
		int input1 = sc.nextInt();
		int input2 = sc.nextInt();
		int input3 = sc.nextInt();
		
		if (input1 > input2 && input2 > input3)
			System.out.println("내림차순: " + input1 + " " + input2 + " " + input3);
		else if (input1 > input3 && input3 > input2)
			System.out.println("내림차순: " + input1 + " " + input3 + " " + input2);
		else if (input2 > input1 && input1 > input3)
			System.out.println("내림차순: " + input2 + " " + input1 + " " + input3);
		else if (input2 > input3 && input3 > input1)
			System.out.println("내림차순: " + input2 + " " + input3 + " " + input1);
		else if (input3 > input1 && input1 > input2)
			System.out.println("내림차순: " + input3 + " " + input1 + " " + input2);
		else
			System.out.println("내림차순: " + input3 + " " + input2 + " " + input1);
      
		sc.close();	
	}
}
```

#### swap을 이용한 코드
```
import java.util.Scanner;

public class Answer_1 {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		System.out.println("세개의 정수를 입력하세요(한칸씩 띄어서)> ");
		
		Scanner sc = new Scanner(System.in);
		int temp = 0;
		int data1 = sc.nextInt();
		int data2 = sc.nextInt();
		int data3 = sc.nextInt();
		
		if(data1 < data2) {
			temp = data1;	// data1에 있는 값이 temp로 들어감
			data1 = data2;	// data2에 있는 값이 data1으로 들어감
			data2 = temp;	// temp에 있는 값이 data2로 들어감
		}
		if(data2 < data3) {
			temp = data2;
			data2 = data3;
			data3 = temp;
		}
		if(data3 < data1) {
			temp = data3;
			data3 = data1;
			data1 = temp;
		}
		
		System.out.println("내림차순: " + data1 + " " + data2 + " " + data3);
		
		sc.close();
	}
}
```
