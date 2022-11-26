## 05 조건문

### if 문

아래와 같은 형식으로 사용됩니다.

`if (조건식) {`

`실행문`

`}`

실행문이 한 줄인 경우 `{ }` 를 생략할 수 있다.

```java
import java.io.*;
class Main {
	public static void main(String[] args) throws Exception {
		int a = 5;
		
		if(a < 3) { // a가 3보다 작은 경우
			System.out.println("A가 3보다 작습니다.");
		}
	}
}
```

### else 문

`else` 문은 단독으로 사용할 수 없고, if 문 뒤에 붙여 사용됩니다.

if 조건을 만족하지 않았을 때 사용하는 문법입니다.

`else` 문도 `if` 문과 동일하게 한 줄인 경우 `{ }` 를 생략할 수 있다.

```java
import java.io.*;
class Main {
	public static void main(String[] args) throws Exception {
		int a = 4;
		
		if(a == 3 || a == 5) {
			System.out.println("A가 3또는 5입니다.");
		} 
		else {
			System.out.println("A가 3또는 5가 아닙니다.");
		}
	}
}
```

### else if 문

`else if` 문도 단독으로 사용할 수는 없으며, if 문과 연계하여 사용할 수 있다.

`else if` 문은 `if` 문의 조건을 만족하지 못하면서 다른 조건을 추가할 때 사용하는 문법이다.

```java
import java.io.*;
class Main {
	public static void main(String[] args) throws Exception {
		int a = 4;
		
		if(a == 3 || a == 5) {
			System.out.println("A가 3또는 5입니다.");
		} 
		else if(a == 4) {
			System.out.println("A는 4입니다.");
		}
		else if(a == 6) {
			System.out.println("A는 6입니다.");
		}
		else {
			System.out.println("else 문이 동작하였습니다.");
		}
	}
}
```

### switch 문

`switch` 문은 `if` 문과 다르게 `int` 형을 조건식으로 사용해야 합니다.

`switch` 문은 `case` 와 `default` 문으로 구성되어 있습니다.

`case` 문 뒤에는 `switch` 조건을 만족하는 숫자를 적고 `:` 를 사용합니다.

`switch` 문의 조건을 만족하는 숫자인 경우, 해당하는 `case` 문부터 `break` 문을 만날 때까지 실행됩니다.

`default` 문은 `case` 문으로 정의하지 않은 조건을 예외 처리하는 문법이다.

```java
import java.io.*;
class Main {
	public static void main(String[] args) throws Exception {
		int a = 1;
		
		switch(a) {
			case 1:
				System.out.println("a == 1");
				break;
			case 2:
				System.out.println("a == 2");
			default:
				System.out.println("a == ?");
		}
	}
}
```

### 연습 문제

[구름 서비스 로그인](https://edu.goorm.io/learn/lecture/19448/%ED%95%9C-%EB%88%88%EC%97%90-%EC%9D%BD%EB%8A%94-%EC%9E%90%EB%B0%94-%EA%B8%B0%EC%B4%88/lesson/934085/%EC%A0%95%EB%A6%AC)
