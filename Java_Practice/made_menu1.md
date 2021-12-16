Q. switch~case를 사용해 메뉴를 출력하시오.  

#### My code
```
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		System.out.println(" [Practice3-6]\n");
		
		System.out.println(" [menu]");
		System.out.println(" 0 : exit");
		System.out.println(" 1 : input (array)");
		System.out.println(" 2 : show (array)");
		System.out.println(" 3 : menu");
		
		Scanner sc = new Scanner(System.in);
		int data=0;
		
		int arr[] = new int[10];
		int mode=5;
		
		while(mode!=0) {
			System.out.print("\n> ");
			mode = sc.nextInt();
			switch(mode) {
			case 0:
				System.out.println("종료되었습니다.");
				System.exit(0);
				break;
			case 1:
				System.out.print("정수 (개수, 값) > ");
				data = sc.nextInt();
				for(int i=0; i<data; i++) {
					arr[i] = sc.nextInt();
				}
				System.out.println("입력 완료");
				break;
			case 2:
				for(int i=0; i<data; i++) {
					System.out.print(arr[i] + " ");
				}
				break;
			case 3:
				System.out.println(" [menu]");
				System.out.println(" 0 : exit");
				System.out.println(" 1 : input (array)");
				System.out.println(" 2 : show (array)");
				System.out.println(" 3 : menu");
				break;
			}
		}
		sc.close();
	}
}
```
