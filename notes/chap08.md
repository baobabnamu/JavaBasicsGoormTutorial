## 08 배열 기초

### 배열의 선언

배열은 `상수` 혹은 `변수`의 모음입니다.

배열은 아래와 같이 선언할 수 있습니다.

`자료형 [] 변수명 = new 자료형[배열 갯수];`

```java
import java.io.*;
class Main {
		public static void main(String[] args) throws Exception {				
			int [] Array = new int[10];
		}
}
```

`new` 는 변수에 메모리 공간을 할당할 때 사용하는 키워드로 참조형 자료형에 메모리 공간을 할당할 때 사용합니다.

기본형 자료형의 경우 `new` 키워드 없이 메모리 공간이 자동으로 할당된다.

배열 자체는 참조형 자료형이며, 배열 안에 들어갈 데이터를 기본형인 `int` 형으로 선언한 것이다.

### 배열 사용하기

배열의 순서는 `1`부터 시작하는 것이 아니라 `0`부터 시작합니다.

이러한 배열의 순서를 `index` 라고 부릅니다.

배열 안의 데이터 값을 사용할 때는 `배열변수명[인덱스]` 를 통해 호출하면 됩니다.

```java
import java.io.*;
class Main {
		public static void main(String[] args) throws Exception {
			
			int [] Array = new int[10];
			
			Array[0] = 1;
			Array[3] = 5;
			//Array[10] = 10; 잘못된 사용법입니다.
			
			System.out.println(Array[0]);
			System.out.println(Array[3]);
		}
}
```

### 배열과 반복문

`배열`은 `반복문`과 함께 사용되는 경우가 많습니다.

배열 자료형의 목적이 대량의 데이터들을 저장하는 것이기 때문입니다.

아래와 같이 주로 `for` 문을 활용하여 사용합니다.

```java
import java.io.*;
class Main {
		public static void main(String[] args) throws Exception {
			int iArraySize = 20;
			int [] Array = new int[iArraySize];
			for(int j = 0 ; j < iArraySize ; j++) {
				Array[j] = j;
			}
			for(int j = 0 ; j < iArraySize ; j++) {
				System.out.println(Array[j]);
			}
		}
}
```
