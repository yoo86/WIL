Q. 실세계의 대상을 선정하여 ADT를 설계하고, Java 클래스로 구현하시오.  
조건 1. ADT는 UML표기법에 따라 그리시오.  
조건 2. 필드는 문자열, int 각각 하나 이상  
조건 3. 메소드는 2개 이상 구현하고, 최소 하나는 대상과 관련된 연산 알고리즘을 구현

#### My code (식물)
```
class Plant {
	
	int grow;	// 하루에 몇 cm씩 자라는지
	int period;		// 며칠이 지났는지
	boolean get_sun;	// 햇빛 아래에 있는지
	String type;
	void growth() {
		System.out.println(type + "은 광합성 여부는 " + get_sun + " 입니다.");
		
	}
	void height() {
		System.out.println(type + "의 높이는 " + grow*period + " 입니다.");
	}
}

public class Main {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		Plant bean = new Plant();
		
		bean.grow = 3;
		bean.period = 5;
		bean.type = "강낭콩";
		bean.get_sun = true;
		
		bean.growth();
		bean.height();
	}
}
/*
---------------
|    Plant    |
---------------
|    grow     |
|   period    |
|   get_sun   |
---------------
|   growth()  |
|   height()  |
---------------
*/
```

#### 자동차 예시
```
public class Car {
	String gameID;
	int fuelGauge;
	int carSpeed;
	void show() {
		System.out.print("게임ID: " + gameID);
		System.out.print("\t 연료: " + fuelGauge + "l");
		System.out.println("\t 속도: " + carSpeed + "km/h");
	}
	void Accel() {
		if(fuelGauge <= 0)
			System.exit(0);
		else
			fuelGauge--;
		carSpeed += 10;
	}
	void Brake() {
		if(carSpeed < 10) {
			carSpeed = 0;
			System.exit(0);
		}
		carSpeed -= 10;
	}
	
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		System.out.println("ADT & 클래스\n");
		
		Car rider = new Car();
		rider.gameID = "run99";
		rider.fuelGauge = 50;
		rider.carSpeed = 20;
		rider.show();
		rider.Accel();
		rider.Accel();
		rider.show();
		rider.Brake();
		rider.show();
	}

}
/*
 ADT
 --------------------------
 |           Car          |
 --------------------------
 |          gameID        |
 |         fuelGauge      |
 |         carSpeed       |
 --------------------------
 |          Accel()       |
 |          Brake()       |
 --------------------------
 */
```
