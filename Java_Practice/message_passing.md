Q. 집에서 출발할 때 자동차에 10L의 기름이 있었다. 학교 근처 주유소 사장은 500L의 기름을 주유소에 채워놓았다.  
그 주유소에 들러 50L의 기름을 넣었다. 현재 내 차의 기름양과 주유소에 남은 기름양을 출력한다.  
(자동차가 주유소에서 기름을 넣는 과정은 객체간 Message Passing으로 구현하시오.  
단, 필드는 모두 private으로)  

#### [출력결과]  
자동차와 주유소  
현재 주유량: 10l  
현재 재고량: 500l  
현재 주유량: 60l  
현재 재고량: 450l  
주유실패  

#### [main() 메소드]  
```
public static void main(String[] args) {
  System.out.println("자동차와 주유소");
  Car SM5 = new Car();
  GasStation GS = new GasStation();
  
  SM5.set_gas(10);
  GS.set_gas(500);
  SM5.show();
  GS.show();
  SM5.fill_gas(50, GS);
  SM5.show();
  GS.show();
  
  SM5.fill_gas(460, GS);
}
```

#### My code
```
public class Car {
	private int gas;
	void set_gas(int g) {
		gas = g;
	}
	void show() {
		System.out.println("현재 주유량: " + gas + "l");
	}
	void fill_gas(int g, GasStation st) {
		if(g==st.refuel(g))
			gas += g;
		else
			System.out.println("주유실패");
	}
}
public class GasStation {
	private int gas;
	void set_gas(int g) {
		gas = g;
	}
	void show() {
		System.out.println("현재 재고량: " + gas + "l");
	}
	int refuel(int g) {
		if(gas<g) {
			return -1;
		}
		gas -= g;
		return g;
	}
}
public class Main {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		System.out.println("자동차와 주유소");
		
		Car SM5 = new Car();
		GasStation GS = new GasStation();
		
		SM5.set_gas(10);
		GS.set_gas(500);
		SM5.show();
		GS.show();
		
		SM5.fill_gas(50, GS);
		SM5.show();
		GS.show();
		
		SM5.fill_gas(460, GS);
	}
}
```
