Q. 아래 main()메소드가 출력결과와 같이 나오도록 ArrList<E>클래스를 설계하시오.
  
```
public static void main(String[] args) {
  System.out.println("ArrList<E>클래스 설계");
  ArrList<Integer> arr = new ArrList<Integer>();
  arr.add(5);
  arr.add(4);
  arr.add(-1);
  
  System.out.println("ArrList요소수: " + arr.size());
  for(int i=0; i<arr.size(); i++) {
    System.out.println(arr.get(i));
  }
  System.out.println();
  
  arr.add(2, 100);
  arr.show();
                             
  arr.remove(1);
  arr.show();
}
                             
[출력결과]

ArrList<E>클래스 설계
ArrList요소수: 3
5
4
-1
  
5 4 100 -1
5 100 -1
```

#### My Code
```
class ArrList<E> {
	private E[] a;
	private int size;
	
	ArrList() {
		a = (E[]) new Object[50];
		size = 0;
	}
	public void add(E num) {
		a[size++] = num;
	}
	public int size() {
		return size;
	}
	E get(int pos) {
		return a[pos];
	}
	public void add(int pos, E num) {
		for(int i=size-1; i>=pos; i--)
			a[i+1] = a[i];
		a[pos] = num;
		size++;
	}
	public void remove(int pos) {
		for(int i=pos; i<size-1; i++)
			a[i] = a[i+1];
		size--;
	}
	public void show() {
		for(int i=0; i<size; i++) {
			System.out.print(a[i] + " ");
		}
		System.out.println();
	}
}

public class Main {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		System.out.println("ArrList<E>클래스 설계");
		ArrList<Integer> arr = new ArrList<>();
		arr.add(5);
		arr.add(4);
		arr.add(-1);
		
		System.out.println("ArrList요소수: " + arr.size());
		for(int i=0; i<arr.size(); i++) {
			System.out.println(arr.get(i));
		}
		System.out.println();
		
		arr.add(2, 100);
		arr.show();
		
		arr.remove(1);
		arr.show();
	}
}
```
