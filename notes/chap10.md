## 10 클래스와 객체

### 클래스와 객체

이번 파트에서는 클래스의 기본 원리와 캡슐화를 중점으로 알아봅니다.

클래스는 사용자가 직접 정의하여 사용할 수 있는 자료형입니다.

이러한 클래스를 통해 만들어진 변수를 `객체` 라고 부릅니다.

동일한 클래스로 변수를 생성하더라도 내부의 값은 다를 수 있습니다.

**즉, 같은 클래스로 생성했더라도 엄연히 내부는 다른 객체라는 것입니다.**

```java
String str1 = "초코붕어빵"; // String 클래스의 str1 객체입니다.
String str2 = "슈크림붕어빵"; // String 클래스의 str2 객체입니다.
```

### 멤버

멤버란 클래스를 구성하는 요소를 말합니다.

예로 클래스 내부에 변수를 선언했다면, 이는 멤버 변수라고 부릅니다.

```java
class ClassExample {	
	
	double mDouble; // 멤버 변수
	
	void CE_Print_mDouble() { // 메소드
		System.out.println(mDouble);
	}
	
	void CE_Set_mDouble(double dInput) {
		mDouble = dInput;
	}
}
```

**멤버 변수 혹은 메소드는 갯수 제한 없이 필요한 만큼 선언**하여 사용할 수 있습니다.

클래스와 객체, 멤버의 개념을 이해했는지 확인하기 위해 아래 코드를 실행해 봅니다.

```java
import java.io.*;
class Main {
	public static void main(String[] args) {
		ClassExample ce;
		ce = new ClassExample();
		
		ce.mDouble = 10;
		ce.CE_Print_mDouble();
		
		ce.CE_Set_mDouble(30);
		ce.CE_Print_mDouble();
	}
}

class ClassExample {
	
	double mDouble;
	
	void CE_Print_mDouble() {
		System.out.println(mDouble);
	}
	
	void CE_Set_mDouble(double dInput) {
		mDouble = dInput;
	}
}
```

1. main 문이 실행됩니다.
2. `ClassExample` 라는 형태의 클래스를 자료형으로 선언하고 `ce` 라는 변수를 생성합니다.
3. `ce` 변수의 `ClassExample()` 생성자 함수를 실행합니다.
    1. 해당 작업을 통해서 멤버 변수의 값 및 메소드들이 `ce` 객체에 담기게 됩니다.
4. `ce` 의 멤버 변수 값을 10으로 지정합니다.
    1. 묵시적 형변환을 통해 멤버 변수에는 10.0이 저장됩니다.
5. 그 후 출력합니다. // `10.0`
6. `ce` 의 멤버 변수 값을 30으로 지정합니다.
    1. 묵시적 형변환을 통해 멤버 변수에는 30.0이 저장됩니다.
7. 그 후 출력합니다. // `30.0`

### 생성자(Constructor)

생성자는 **사용자가 객체를 생성할 때 자동으로 호출되는 메소드**를 말합니다.

생성자는 `return` 를 하지 않으며, 클래스 이름과 동일한 이름을 가져야 합니다.

`ClassExample` 클래스의 `ClassExample` 생성자 함수를 선언한 코드입니다.

- 매개 변수가 존재하지 않는 생성자를 `기본 생성자` 라고 칭합니다.
- 주로, 멤버 변수들의 초기화 및 객체의 복사와 같은 역할로 많이 사용됩니다.

```java
import java.io.*;
class Main {
	public static void main(String[] args) {
		ClassExample ce;
		System.out.println("ce object Called");
		ce = new ClassExample();
		System.out.println("ce Object Created");
	}
}

class ClassExample {
 	ClassExample() { // 생성자 함수
		System.out.println("Constructor Called!!!");
	}
}
```

### 접근 제한자

접근 제한자는 OOP의 특성인 캡슐화랑 가장 큰 관련을 갖고 있습니다.

접근 제한자를 이용하여 메소드의 공개 범위를 지정할 수 있습니다.

이를 통해 프로그래머는 **정보 은닉의 효과 및 중요 정보의 보안성을 높일 수 있습니다.**

1. `public` : 제한 없음
2. `protected` : 자식 클래스에게만 공유
3. `NOT USE` : 같은 패키지에서만 공유
4. `private` : 본인 객체 내에서만 공유

```java
import java.io.*;
class Main {
	public static void main(String[] args) {
		ClassExample ce;
		ce = new ClassExample();
		
		ce.mDouble = 10;	// 오류 발생
		ce.CE_Print_mDouble();
		
		ce.CE_Set_mDouble(30);
		ce.CE_Print_mDouble();
	}
}

class ClassExample {
	
	private double mDouble; // 멤버 변수를 private 로 지정했기 때문에 Main 클래스에서 접근 불가
	
	public void CE_Print_mDouble() {
		System.out.println(mDouble);
	}
	
	public void CE_Set_mDouble(double dInput) {
		mDouble = dInput;
	}
	
}
```

### Static에 대하여

main 메소드는 무조건 `static` 키워드가 붙여야 합니다.

그렇다면 왜 `static` 을 붙여야하는 걸까요?

`**static`이 붙은 멤버들은 프로그램이 시작될 때 우선 메모리에 할당되기 때문입니다.**

즉, main 메소드에 static을 붙이지 않는다면 main 메소드를 실행할 메모리 공간이 확보되지 않아 자바 프로그램이 동작할 수 없습니다.

이와 별개로, **클래스 안의 멤버에 `static` 이 붙으면 그 멤버는 클래스의 객체를 선언하지 않고 바로 콜할 수 있습니다.**

```java
import java.io.*;
class Main {
	public static void main(String[] args) {
		
		ClassExample.mInt = 3; // ClassExample 클래스의 객체가 없음에도 멤버 변수(전역 멤버 변수)를 사용
		ClassExample.Print(); // 3 출력, 전역 메소드 사용
		
		ClassExample c = new ClassExample(); // c 객체 생성
		c.mInt = 20; // 멤버 변수에 20 저장
		c.Print(); // 20 출력, c 객체의 메소드 호출
	}
}

class ClassExample {
	
	public static int mInt;
	
	public static void Print() {
		System.out.println( mInt );
	}
	
}
```
