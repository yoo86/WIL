Q. 요구사항에 맞게 메뉴를 만들어라.  
#### 요구사항 1  
1. 왕(King) 30명의 정보를 입출력 할 수 있는 시스템
2. 입출력은 화면으로 가능하면 된다. 파일 입출력 불필요
3. 왕의 정보는 이름, 즉위 순서 정도면 됨
4. 왕의 입력은 메뉴에서 한 명씩 입력하면 됨

#### 요구사항 2
1. 왕의 정보는 클래스로 구현한다.
2. 이름, 즉위순서를 private 필드로 구현한다.
3. 왕 클래스는 이름, 즉위순서를 인자로 하는 생성자를 오버로딩한다.
4. 왕들의 정보 출력 기능을 메소드로 구현한다.
5. 메뉴방식은 main()메소드에 구현된다.
6. 또한, 키보드 입력도 main()메소드에 구현한다.

#### My code  
```
import java.util.Scanner;
class King {
	private String name;
	private int order;
	King(String nm, int od) {
		name = nm;
		order = od;
	}
	void show() {
		System.out.println("조선"+order+"대왕 "+name);
	}
}

public class Main {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		System.out.println("실습과제\n");
		
		int mode=5, size=0;
		King[] Joseon = new King[30];
		menu();
    
		Scanner sc = new Scanner(System.in);
		while(mode!=0) {
			System.out.print("\n> ");
			mode = sc.nextInt();
			switch(mode) {
			case 0:
				System.out.println("종료되었습니다");
				break;
			case 1:
				System.out.print("왕의 이름 > ");
				String name = sc.next();
				System.out.print("왕의 순서 > ");
				int order = sc.nextInt();
				Joseon[size++] = new King(name, order);
				break;
			case 2:
				for(int i=0; i<size; i++)
					Joseon[i].show();
				break;
			case 3:
				menu();
				break;
			}
		}
		sc.close();
	}
  static void menu() {
    System.out.println("[menu]");
    System.out.println("0 : exit");
    System.out.println("1 : input (King Info.)");
    System.out.println("2 : show (King List)");
    System.out.println("3 : menu");
  }
}
```
