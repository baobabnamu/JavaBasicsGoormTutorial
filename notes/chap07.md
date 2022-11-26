## 07 메소드

### 메소드의 기본

메소드에는 입력과 출력 값이 존재합니다.

입력은 매개변수 혹은 파라미터라고 합니다.

- 매개변수로 사용된 변수들은 함수 내에서만 지역 변수처럼 사용할 수 있습니다.

출력은 반환값(리턴값)이라고 합니다.

메소드는 아래와 같은 구조로 구성된다.

1. 메소드 리턴 값의 자료형
2. 메소드 이름
3. 매개변수
4. 메소드 내용
5. return

```java
import java.io.*;
class Main {
	
	public static	int add(int a, int b) {
	
		int result = a+b;
	
		return result;
	}

	public static void main(String[] args) throws Exception {
		System.out.print(add(4, 6)); // 10
	}
}
```

### return

메소드의 종료를 나타내는 용어입니다.

작성된 값을 결과로 내보내는 과정을 “값을 반환한다”라고 표현합니다.

return 값의 형태는 반드시 메소드를 선언할 때 지정한 자료형을 사용해야 합니다.

위 예제에서 `public static **int** add(int a, int b)` 를 선언하여 메서드를 정의하였습니다.

이때 public static ‘`int`’ 부분을 통해 해당 메서드가 int 값을 반환한다는 것을 알 수 있습니다.

### void

`return` 값에 예외로 판단되는 특별한 자료형입니다.

`void` 형은 해당 함수가 어떠한 자료형도 반환하지 않을 때 사용합니다.

오로지 `void` 문을 사용했을 때만 `return` 을 생략할 수 있습니다.

앞서 사용 했었던 `main` 문은 대부분 `void` 형에 해당합니다.

즉, `void` 문으로 선언된 메서드는 `return;` 또는 `return` 자체를 생략해야 합니다.

### main method

메소드는 main, 사용자정의 메소드로 구분됩니다. 

`main` 메소드는 굉장히 특별합니다.

`main` 메소드 기준으로 프로그램의 시작과 끝이 결정되기 때문입니다.

모든 자바프로그램은 `main` 메소드를 시작으로 `main` 메소드의 리턴과 함께 종료됩니다.

```java
import java.io.*;
class Test {
		public static void main(String[] args) {
			for(int i = 1 ; i <= 3 ; i++) {
				System.out.println(i + "번째 반복");
			}
		}
}
```

## Overloading

`오버로딩` 이란 메소드의 **이름은 동일하게 정의하고 매개변수 혹은 리턴 값만 변경하여 정의**하는 기법을 말합니다.

만약 `overloading` 이 없다면 각 자료형 별로 새로운 메소드가 필요할 것입니다.

예시로 `minus` 함수를 들 수 있습니다.

```java
import java.io.*;
class Main {
		static int minus(int a, int b) {
			return a - b;
		}
	
		static double minus(double a, double b) {
			return a - b;
		}
	
		public static void main(String[] args) throws Exception {				
			
			int result1 = minus(2, 5);
			System.out.println(result1);
			
			double result2 = minus(5.1, 3.9); 			
			System.out.println(result2);
		}
}
```

### Call By Value (값에 의한 호출)

변수 이름이 모두 동일하더라도 컴퓨터 내부적으로는 각각 다른 메모리 공간을 차지하고 있습니다.

따라서, times 메소드 내부의 값을 변경 시키더라도 main 메소드 내부의 값은 변경되지 않습니다.

이러한 현상을 `call by value` 라고 부릅니다.

- **함수 내부의 인자 값이 변경되어도, 함수 외부의 변수의 값은 변경되지 않는다.**

```java
import java.io.*;
class Main {
		static int times(int a, int b, int c) {
			c = a + b; // 6, 그러나 지역 변수이므로 main 함수에는 영향 주지 못함.
			return a * b; // return을 통해 5 반환
		}
	
		public static void main(String[] args) throws Exception {
			int a = 1;
			int b = 2;
			int c = 3;
			
			int result = times(a, 5, c);
			
			System.out.println("result = " + result); // 5
			System.out.println("int c = " + c); // 3
		}
}
```
