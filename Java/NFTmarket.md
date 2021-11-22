## NFT거래소를 캡슐화하여 진행한 코드
```
import java.util.Scanner;

class Creater {
	private String cre_name, work_name;	// 크리에이터 이름, 작품 이름
	private int re_klay, to_work, re_work;	  // 작품 가격, 총 작품의 수, 남은 작품의 수
	
	Creater() {	}
	
	Creater(String cre_name, String work_name) {
		this.cre_name = cre_name;
		this.work_name = work_name;
	}
	int get_reKlay() {
		return re_klay;
	}
	
	void set_reKlay(int klay) {
		if(klay < 0)
			System.out.println("판매가를 다시 입력해주십시오.");
		else
			this.re_klay = klay;
	}
	
	void set_toWork(int work) {
		if(work < 0)
			System.out.println("작품 개수를 다시 입력해주십시오.");
		else {
			this.to_work = work;
			this.re_work = work;
		}
	}
	int get_reWork() {
		return re_work;
	}
	
	void sell(int buy) {
		re_work -= buy;
	}
	
	void show_1() {
		System.out.println(cre_name + "의 " + work_name + "을 구매하려면 " + re_klay + " KLAY가 필요합니다.");	
	}
	
	void show_3() {
		System.out.println("총 " + to_work + "개 중 " + re_work + "개 구매 가능");
	}
}

class Consumer {
	private String con_name;	// 구매자 이름
	private int balance;	// 잔고

	Consumer() { }
	
	Consumer(String con_name) {
		this.con_name = con_name;
	}
	
	void setBalance(int money) {
		this.balance += money;
	}

	int getBalance() {
		return balance;
	}
	
	void spend(int buy) {
		this.balance -= buy;
	}
	
	void show_2() {
		System.out.println(con_name + "님의 잔고는 " + balance + " KLAY입니다.");
	}
}

public class Main {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		Creater _and_ = new Creater("_and_", "W&E");
		_and_.set_toWork(25);
		_and_.set_reKlay(107);
		_and_.sell(20);
		Consumer yji = new Consumer("유정인");
		int mode = 10;
		
		menu();
		
		Scanner sc = new Scanner(System.in);
		while(mode != 0) {
			System.out.print("\n> ");
			mode = sc.nextInt();
			switch(mode) {
			case 0:
				System.out.println("종료되었습니다.");
				break;
			case 1:
				_and_.show_1();
				_and_.show_3();
				if(_and_.get_reWork() <= 0) {
					System.out.println("품절되었습니다.");
					break;
				} else if(yji.getBalance() < _and_.get_reKlay()) {
					System.out.println("잔고가 부족합니다.");
				} else {
					_and_.sell(1);
					yji.spend(107);
					System.out.println("구매가 완료되었습니다.\n");
					_and_.show_3();
				}				
				break;
			case 2:
				yji.show_2();
				break;
			case 3:
				System.out.print("입금할 금액을 입력해주세요> ");
				int deposit = sc.nextInt();
				if(deposit <= 0) {
					System.out.println("입금은 0 KLAY보다 큰 금액만 가능합니다.");
				} else {
					yji.setBalance(deposit);
					System.out.println("입금되었습니다.");
					yji.show_2();
				}
				break;
			case 4:
				menu();
				break;
			}
		}
		sc.close();
	}
	
	static void menu() {
		System.out.println("MetaGalaxia\n");
		System.out.println("[메뉴]");
		System.out.println("0 : 나가기");
		System.out.println("1 : 구매하기");
		System.out.println("2 : 잔고 확인");
		System.out.println("3 : 입금하기");
		System.out.println("4 : 메뉴");
	}

}
```
### 출력 결과
```
MetaGalaxia

[메뉴]
0 : 나가기
1 : 구매하기
2 : 잔고 확인
3 : 입금하기
4 : 메뉴

> 1
_and_의 W&E을 구매하려면 107 KLAY가 필요합니다.
총 25개 중 5개 구매 가능
잔고가 부족합니다.

> 2
유정인님의 잔고는 0 KLAY입니다.

> 3
입금할 금액을 입력해주세요> 200
입금되었습니다.
유정인님의 잔고는 200 KLAY입니다.

> 1
_and_의 W&E을 구매하려면 107 KLAY가 필요합니다.
총 25개 중 5개 구매 가능
구매가 완료되었습니다.

총 25개 중 4개 구매 가능

> 2
유정인님의 잔고는 93 KLAY입니다.

> 3
입금할 금액을 입력해주세요> 500
입금되었습니다.
유정인님의 잔고는 593 KLAY입니다.

> 1
_and_의 W&E을 구매하려면 107 KLAY가 필요합니다.
총 25개 중 4개 구매 가능
구매가 완료되었습니다.

총 25개 중 3개 구매 가능

> 1
_and_의 W&E을 구매하려면 107 KLAY가 필요합니다.
총 25개 중 3개 구매 가능
구매가 완료되었습니다.

총 25개 중 2개 구매 가능

> 1
_and_의 W&E을 구매하려면 107 KLAY가 필요합니다.
총 25개 중 2개 구매 가능
구매가 완료되었습니다.

총 25개 중 1개 구매 가능

> 1
_and_의 W&E을 구매하려면 107 KLAY가 필요합니다.
총 25개 중 1개 구매 가능
구매가 완료되었습니다.

총 25개 중 0개 구매 가능

> 1
_and_의 W&E을 구매하려면 107 KLAY가 필요합니다.
총 25개 중 0개 구매 가능
품절되었습니다.

> 4
MetaGalaxia

[메뉴]
0 : 나가기
1 : 구매하기
2 : 잔고 확인
3 : 입금하기
4 : 메뉴

> 0
종료되었습니다.
```
