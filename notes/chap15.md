## 15 Exception

### try-catch 문

`try catch` 문은 `swtich case` 문처럼 단독으로 사용할 수 없습니다.

아래 코드는 배열이 넘친다는 오류(`ArrayIndexOutOfBoundsException` 오류)를 뱉는 코드입니다.

아래 코드를 기준으로 `try - catch` 문을 적용해 보겠습니다.

```java
public class Main {

	public static void main(String[] args) {
		
		int [] Arr = new int[3];
		
		for(int j = 0 ; j < 4 ; j++) {
			Arr[j] = j;
		}
	}
}
```

아래와 같이 `ArrayIndexOutOfBoundsException` 오류 코드에 대응하는 코드를 작성할 수 있습니다.

```java
public class Main {

	public static void main(String[] args) {
		
		int [] Arr = new int[3];
		
		try {
			for(int j = 0 ; j < 4 ; j++) {
				Arr[j] = j;
			}
		} catch (ArrayIndexOutOfBoundsException e) {
			System.out.println("Exception!!!");
		}
	}
}
```

### Exception

`Exception` 은 위에서 언급했던 것처럼 런타임 오류가 발생했을 때 어떤 오류인지 정의해 놓은 클래스입니다.

`Exception` 클래스를 시작으로 수많은 `Exception` 클래스들이 자식 클래스로 파생되어 있습니다.

- 데이터 입출력 오류  발생 시 : I/O Exception
- 수학 연산 오류 발생 시 : ArithmeticException …
- 등등

이러한 `Exception` 클래스를 통해 예상치 못한 오류가 발생했을 때 개발자와 사용자에게 피드백을 줄 수 있습니다.
