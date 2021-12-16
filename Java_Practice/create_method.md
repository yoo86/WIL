Q. 다음 3개의 메소드를 완성하시오.  

#### [1번 odd()]  아래 main()은 수정하지 않고, 그대로 사용  
```
public class Main {
  public static void main(String[] args) {
    Example ex = new Example();
    
    // 1번
    int a = 5;
    System.out.print("1번문제= ");
    if(ex.odd(a))
      System.out.println("홀수");
    else
      System.out.println("짝수");
```

#### [2번 next(), 3번 min()]
```
// 2번
char c = 's';
c = next(c);
System.out.println("2번문제= " + c);

// 3번
int[] data = {10,5,8,20,7,3,30,25,15);
System.out.println("3번문제= " + ex.min(data));
```

#### 출력결과  
1번문제= 홀수  
2번문제= t  
3번문제= 3  

***
#### My code
```
class Example {
	boolean odd(int n) {
		return n%2 != 0;
	}
	
	int min(int[] dat) {
		int min=dat[0];
		for(int i=1; i<dat.length; i++) {
			if(dat[i]<min)
				min = dat[i];
		}
		return min;
	}
}
public class Main {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		Example ex = new Example();
		
		// 1번
		int a = 5;
		System.out.print("1번문제= ");
		if(ex.odd(a))
			System.out.println("홀수");
		else
			System.out.println("짝수");
		
		// 2번
		char c = 's';
		c = next(c);
		System.out.println("2번문제= " + c);
		
		// 3번
		int[] data = {10,5,8,20,7,3,30,25,15};
		System.out.println("3번문제= " + ex.min(data));
	
	}	
	static char next(char ch) {
		return (char)(ch+1);
	}
}
```
