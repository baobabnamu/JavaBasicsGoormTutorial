## 03 메모리와 자료형

### 컴퓨터의 저장 공간

컴퓨터가 데이터를 저장하는 공간의 종류는 3가지가 있습니다.

1. Register : CPU 내부에서 사용되는 저장 공간
2. Storage : 파일, 프로그램 등을 저장하는 공간
3. Memory : **RAM이라고 불리는 하드웨어 장치가 Storage의 느린 속도, 큰 용량과 Register의 빠른 속도, 작은 용량을 유용하게 활용할 수 있도록 중간에 위치하여 다른 속도 및 용량을 가지고 있는 저장소들을 보완하는 역할을 수행합니다.**



### 프로그램 동작 원리

1. 바탕화면에 있는 메모장을 실행합니다.
2. Storage에 저장되어 있던 메모장 프로그램이 OS에 의해 Memory에 로드됩니다.
3. Memory에 Load 된 프로그램은 하나의 프로세스로 부르게 됩니다.

### 변수와 상수

**변수**

변수는 아래와 같이 자료형과 변수명을 선언하고 값을 할당하는 방식으로 사용합니다.

선언(Declare) : 메모리에 데이터를 저장할 수 있는 공간을 만드는 것을 말함.

```java
import java.io.*;
class Main {
	public static void main(String[] args) {
		int a;
		a = 1;
		System.out.println(a);
	}
}
```

> **정리 : 변수를 선언하면 선언한 변수가 지정한 자료형에 맞게 메모리 공간을 확보하고, 확보된 메모리 주소와 변수명을 연결한다.**
> 

`a=1` 은 연결된 메모리 주소에 1라는 값을 할당하는 것을 말한다.

메모리 주소에 데이터를 처음으로 할당하는 작업을 초기화라고 한다.

**상수**

상수도 변수와 사용 방법은 같으나 `final` 키워드를 추가하여 사용해야 한다.

**변수와 상수의 가장 큰 차이점은 변수 값 변경 가능 여부이다.**

따라서 변수 선언과 동시에 값을 초기화해야 한다는 특징도 있다.

```java
import java.io.*;
class Main {
	public static void main(String[] args) {
		final int a = 2;
		System.out.println(a);	
	}
}
```

### 자료형 > 기본형 > 정수 숫자형 (Data Type > Primitive Type > Integral Type)

자료형의 기본형 중 정수 숫자형의 자료형 종류는 `short`, `integer`, `long` 세 가지이다.

각각 2Byte, 4Byte, 8Byte 크기의 데이터를 표현할 수 있다.

`long`, `short` 는 모두 다 정수형을 저장할 수 있다는 점에서는 동일하지만, 선언 시 Memory에 할당되는 공간의 크기는 각각 다릅니다.

### 자료형 > 기본형 > 실수 숫자형 (Data Type > Primitive Type > Floating Point Type)

자료형의 기본형 중 실수 숫자형의 자료형 종류는 `float`, `double` 두 가지이다.

각각 4Byte, 8Byte 크기의 데이터를 표현할 수 있다.

정수 숫자형과 실수 숫자형 모두 자료형의 크기에 따라 표현할 수 있는 수가 다양해 집니다.

자바에서는 일반적인 실수는 `double` 형으로 선언됩니다.

따라서, `float` 자료형을 사용하여 실수를 표현하고자 할 때는 `12.1f` 와 같이 `f` 라는 키워드를 붙여 사용해야 합니다.

```java
import java.io.*;
class Main {
	public static void main(String[] args) {
		float varFloat = 12.34f;
		double varDouble = 98.76543;
		
		System.out.println(varFloat);
		System.out.println(varDouble);
	}
}
```

### 자료형 > 기본형 > 참/거짓형 (Data Type > Primitive Type > Boolean Type)

자료형의 기본형 중 참/거짓형은 참/거짓(True/False)을 저장하는 `boolean` 자료형이다.

데이터 길이는 1bit에 해당하며, 주로 조건문에서 사용된다.

### 자료형 > 기본형 > 문자형 (Data Type > Primitive Type > Char Type)

자료형의 기본형 중 문자형은 문자를 저장하는 `Char` 자료형이다.

데이터 길이는 2Byte에 해당한다.

이때, 문자와 문자열은 엄연히 다르다.

문자는 단순히 한 글자의 문자를 뜻하는 것이고, 문자열은 문자들의 모임을 뜻한다.

즉 `char` 형은 1개의 문자만 저장할 수 있고 여러 개의 문자를 저장하기 위해서는 기본형이 아닌 `string` 형을 사용해야 한다.

문자는 아래와 같이 `‘` 로 감싸서 표현한다.

```java
import java.io.*;
class Main {
	public static void main(String[] args) {
		char varChar = 'A';
		System.out.println(varChar);
	}
}
```

### 자료형 > 참조형 (Data Type > Reference Type)

기본형이 아닌 자료형은 모두 참조형이라고 부릅니다.

참조형의 종류는 아래와 같습니다.

1. Class Type
2. Interface Type
3. Array Type
4. Enum Type

참조형은 **값이 저장된 주소를 저장하는 자료형으로, 모두 객체의 주소를 의미**합니다.

### 기본형 자료형 형변환 (Type Casting)

프로그래밍을 하다보면 어쩔 수 없이 변수의 자료형을 변경해야 할 때가 있습니다.

이럴 때 사용하는 것을 `타입 캐스팅(Type Casting, 형변환)` 이라고 합니다.

형변환의 종류는 두 가지로 구분할 수 있습니다.

1. 명시적 형변환
2. 묵시적 형변환

**명시적 형변환**

명시적 형변환은 직접 코드에 명시적으로 형을 변환하는 것을 말합니다.

형변환 시 표현할 수 없는 값은 버려지기 때문에 주의해야 합니다.

예시로 아래 코드를 들 수 있습니다.

`(int)` 를 통해서 `varDoulbe`에 저장된 98.76 값을 정수형 타입인 `varInteger` 변수에 저장했습니다.

`varInteger` 의 값은 98로 0.76 값은 유실되었습니다.

```java
import java.io.*;
class Main {
    public static void main(String[] args) {
        double varDouble = 98.76;
        int varInteger = (int)varDouble;
        System.out.println(varInteger);	
    }
}
```

**묵시적 형변환**

묵시적 형변환은 형태를 별도로 명시하지 않고도 변환되는 것을 말합니다.

아래 코드를 실행해 보면 정수형으로 저장되어 있던 5가 double에 저장되면서 5.0으로 변환됩니다.

묵시적 형변환에는 중요한 조건이 있습니다.

**자신보다 큰 자료형으로만 묵시적 형변환을 수행할 수 있습니다.**

```java
import java.io.*;
class Main {
    public static void main(String[] args) {
        short varShort = 5;
        double varDouble = varShort;
        System.out.println(varDouble); 
    }
}
```

**형변환 핵심**

형변환은 `boolean` 형을 제외한 모든 기본형 자료형에서만 타입 캐스팅을 사용할 수 있습니다.

참조형 자료형은 참조형 자료형 간의 타입 캐스팅만 지원하며, 기본형 자료형 간의 타입 캐스팅과는 다르게 조건이 까다롭습니다.
