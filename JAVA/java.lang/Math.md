# round()와 rint() 비교
* 둘 다 소수점 첫째자리에서 반올림한 값을 반환함
* round()는 반환타입이 long임
* rint()는 반환타입이 double이고, 1.5, 2.5, -3.5 처럼 두 정수의 정 가운데에 있는 값의 경우 가까운 짝수를 반환함

```java
public class ex {
	public static void main(String[] args) {
		System.out.println(Math.round(1.4)+", "+Math.rint(1.4));
		System.out.println(Math.round(1.5)+", "+Math.rint(1.5));
		System.out.println(Math.round(1.6)+", "+Math.rint(1.6));
		System.out.println(Math.round(2.4)+", "+Math.rint(2.4));
		System.out.println(Math.round(2.5)+", "+Math.rint(2.5));
		System.out.println(Math.round(2.6)+", "+Math.rint(2.6));
		System.out.println(Math.round(-1.5)+", "+Math.rint(-1.5));
		System.out.println(Math.round(-2.5)+", "+Math.rint(-2.5));
	}
}
```
```
1, 1.0
2, 2.0
2, 2.0
2, 2.0
3, 2.0
3, 3.0
-1, -2.0
-2, -2.0
```
