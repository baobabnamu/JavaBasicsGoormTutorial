## 12 배열 심화

### 2차원 배열

배열 안에 배열을 넣을 수 있습니다.

주로 테이블, 행렬과 같은 구조로 표현할 때 사용됩니다.

```java
import java.io.*;

class Main {
	
	public static void main(String[] args) throws Exception {
		int [][] arr = new int[10][10];
		for(int j = 0 ; j < 10 ; j++) {
			for(int k = 0 ; k < 10 ; k++) {
				arr[j][k] = j * k;
			}
		}
		
		for(int j = 0 ; j < 10 ; j++) {
			for(int k = 0 ; k < 10 ; k++) {
				System.out.print(arr[j][k] + "\t");
			} System.out.println();
		}
	}
}
```

### 클래스 배열

우리가 정의한 클래스를 여러 개 만들어야 할 때 배열을 사용할 수 있습니다.

다른 자료형들과 배열 사용법은 거의 동일하나, 주의할 점은 객체 생성을 위해서 클래스의 생성자 함수를 매번 초기화해 줘야 한다는 것입니다.

- 반복문을 활용하여 클래스의 생성자 함수를 실행합니다.

```java
import java.io.*;

class Main {
	
	public static void main(String[] args) throws Exception {
		
		// 배열의 크기를 관리하는 변수 : ArrayNum
		final int ArrayNum = 5;
		
		// 클래스 배열 변수 : CE_Array
		// 배열 변수 사이즈 지정( ArrayNum크기 만큼 배열 사이즈 지정 )
		ClassExample[] CE_Array = new ClassExample[ArrayNum];
		
		// 각 배열칸의 객체 초기화( new 객체 )
		// 생성자를 통해 객체의 iIndex 변수 초기화
		for(int j = 0 ; j < ArrayNum ; j++) {
			CE_Array[j] = new ClassExample(j);
		}
		
		// 객체 사용( Print_iIndex 메소드 사용 )
		for(int j = 0 ; j < ArrayNum ; j++) {
			CE_Array[j].Print_iIndex();
		}
	}	
}

class ClassExample {
	int iIndex;
	
	public ClassExample(int i) {
		iIndex = i;
	}
	
	public void Print_iIndex() {
		System.out.println(iIndex);
	}
}
```
