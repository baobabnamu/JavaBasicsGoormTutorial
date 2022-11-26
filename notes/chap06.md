## 06 반복문

### for 문

`for` 문의 구성 요소는 3가지이다.

1. 시작 조건
2. 실행 조건
3. 증감식

아래와 같은 형태로 사용된다.

```java
for(/* 시작조건 */ ; /* 실행조건 */ ; /* 증감식 */) {
	// 반복 내용
}
```

```java
import java.io.*;
class Main {
		public static void main(String[] args) throws Exception {
			for(int i = 1 ; i <= 3 ; i++) {
				System.out.println(i + "번째 반복");
			}
		}
}
```

동작 원리는 아래와 같다.

1. 시작 조건에 의해 변수 i의 값이 1로 초기화 되었습니다.
2. 변수 i 값은 실행 조건인 `i <= 3` 을 만족하기 때문에 반복문 `{ }` 안의 코드를 실행합니다.
3. 증감식에 의해 i가 1 증가하여 i의 값으로 2가 할당 되었습니다.
4. 실행 조건을 만족하면 반복문 `{ }` 안의 코드를 반복하여 실행합니다.
5. 위 과정이 반복되어 i가 4가 되면 실행 조건을 만족하지 못했기 때문에  반복문 `{ }` 안의 코드를 실행하지 않고 종료됩니다.

### 이중 for 문

아래 코드와 같이 for 문 안에 for 문을 배치하여 이중으로 반복 시킬 수 있습니다.

```java
import java.io.*;
class Main {
		public static void main(String[] args) throws Exception {
			for(int i = 1 ; i <= 3 ; i++) {
				for(int j = 1 ; j <= 5 ; j++) {
					System.out.println("i = " + i + "번째 반복");
					System.out.println("j = " + j + "번째 반복");
				}
			}
		}
}
```

### while 문

while 문은 오직 `실행 조건` 을 기준으로만 반복됩니다.

```java
while( /* true 혹은 false 형태의 동작 조건 */ ) {
	//동작 내용	
}
```

`for` 문에 비해 형태가 간소화 되어있다.

```java
import java.io.*;
class Main {
		public static void main(String[] args) throws Exception {
			int a = 1;
			while(a < 3) {
				int b = 0;
				System.out.println(a + " " + b);
				a++;
				b++;
			} // while 문 종료
		}
}
```

> while 문 안에 들어있는 **b는 지역 변수로 while 문이 끝나면 main 함수에서는 사용할 수 없다.**
> 

### do while 문

`do while` 문은 `while` 문의 변형한 형태입니다.

아래와 같은 형태로 사용됩니다.

```java
do {
	// 동작 내용
} while( /* 동작 조건 */ );
```

`while` 문과 차이점은 동작 조건을 먼저 확인하냐, 이후에 확인하냐 정도입니다.

`do while` 문은 동작 내용을 우선 1회 동작한 뒤 동작 조건을 판단하여 반복 여부를 판단합니다.

`break` 문을 사용한다면 `while` 문만 사용하더라도 `do while` 문처럼 동작 시킬 수 있습니다.

```java
import java.io.*;
class Main {
		public static void main(String[] args) throws Exception {
			int a = 1;
			do {
				System.out.println(a++); // 1 2 3 4 가 출력됩니다.
			}	while(a < 5); 
		}
}
```

### break / continue 문

**break 문**

`break` 문은 반복문을 실행하다가 탈출할 수 있게끔 해주는 문법입니다.

아래의 예제는 `do while` 문 예제와 동일한 작업을 수행합니다

```java
import java.io.*;
class Main {
		public static void main(String[] args) throws Exception {
			int a = 1;
			while(true) {
				System.out.println(a++);
				if(a > 5) {
					break;
				}
			} 
		}
}
```

**continue 문**

`continue` 문은 반복문의 실행 조건으로 컨텍스트를 이동 시킵니다.

```java
import java.io.*;
class Main {
		public static void main(String[] args) throws Exception {
			int a = 1;
			while(true) {
				
				if(a > 10) {
					break;
				} else if(a % 2 == 1) {
					a++;
					continue;
				}
				
				System.out.println(a++); // 2 4 6 8 10
				
			} 
		}
}
```
