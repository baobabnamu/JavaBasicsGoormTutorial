## 02 자바 프로그래밍 시작하기

### 자바 소스 코드가 프로그램이 되는 과정

1. 자바 소스(.java)를 `javac compiler` 가 컴파일링 합니다.
2. Byte Code(.class) 형태의 파일로 변환됩니다.
3. 각 운영 체제에 맞게 JVM이 해당 Byte Code(.class) 파일을 동작 시킵니다.

### 자바 프로그램을 사용하려면

1. **결국에는 JVM이 있어야 자바 프로그램을 사용할 수 있습니다.**
    
    **따라서 Java를 사용하는 모든 호스트에는 JVM이 설치되어야 합니다.**
    
    **그렇다고 무거운 JDK를 모두 설치해야 하는 것은 아닙니다.**
    
    ‘개발하는 호스트’가 아닌 **‘사용하는 호스트’는 JRE만 설치하면 됩니다.**
    
    J**RE에는 자바 클래스 라이브러리, 자바 클래스 로더, 자바 가상 머신 등 실행에 필요한 요소만 추려 포함되어 있습니다.**
    
2. **자바 소스 코드는 어느 운영체제던지 JVM에만 있으면 소스 코드 수정이 필요 없습니다.**
이러한 언어를 **Managed Language(반대말 : Native Language)** 라고 합니다.

### 자바 프로그램이 C/C+ 보다 속도가 느린 이유

- **Managed Language는 Native Language 보다 비교적 속도가 느립니다.**
어떻게 보면 당연합니다. 
Native Lang은 소스 코드 작업 단계에서 각 운영체제에 맞게 코드를 짜주기 때문입니다.
그에 반면 **Managed Lang인 Java는 Javac Compiler를 통해 Byte 코드로 JVM를 통해서 각 운영체제에 맞게 변환되기 때문에 속도가 더 느릴 수 밖에 없습니다.**

### C보다 자바가 더 확실하게 데이터형을 지정해야 함 (SDT, Strict Data Type)

- 예시)
    - C 언어의 if 조건문에는 `1 == 0` 식으로 int 형 변수라는 선언 없이 숫자만 입력해도 컴파일이 알아서 해석해 줍니다.
    - 그러나 자바에서는 이것이 불가능합니다.

### 가비지 컬렉터야, 안녕 또 보네!

위에서 언급한 내용이므로 간단하게 요약했습니다.

- 사용되지 않는 메모리 공간을 청소해 주는 객체
- 프로그램의 백그라운드에서 동작하며, 자바의 구간이 종료될 때 메모리를 다시 주어감
    - 구간 종료란 일정 구간`}` 이 닫힐 때를 의미함

### POP와 OOP

**POP(Procedure Oriented Program)**

- 순서대로 프로그래밍 하는 기법을 말함.
    - 데이터의 접근성이 용이함 → 데이터의 보안성이 떨어짐
    - 기능성을 우선시하기 때문에 생산성이 높음
    - POP는 데이터의 모듈화가 어려움

**OOP(Object Oriented Program)**

- POP의 단점을 보완한 개발된 개념을 말함.
    - 기능 위주의 POP과는 달리 **객체라는 개념을 통해 데이터 및 함수를 모듈화하여 프로그램의 유지보수성과 보안성을 강화**하였음.

### OOP 특성

1. 캡슐화 : 프로그램에서 접근 가능한 데이터(함수)를 지정할 수 있음
2. 추상화 : 객체의 기본적인 틀을 추상적으로 정의할 수 있음
3. 상속 : 코드의 재사용성 향상
4. 다형성 : 객체가 다양한 형태로 표현될 수 있음을 뜻함

### OOP 예시
SW 회사라는 클래스가 있다고 가정합니다.
클래스의 인스턴스로 회사A, 회사B, 회사C가 있습니다.
이를 OOP 관점에서 보겠습니다.

1. 캡슐화 : 회사 A, B, C는 서로의 함수에 접근할 수 없습니다.
2. 추상화 : SW 회사라는 하나의 추상화된 틀을 통해 회사 A, B, C는 생성되었습니다.
3. 상속 : SW 회사라는 클래스 안에 원래 있는 함수들을 회사 A, B, C는 그대로 상속 받아서 사용할 수 있습니다.
4. 다형성 : 상속받은 함수들을 각자 회사에 맞게 변경할 수 있습니다. 이를 오버라이딩(Overriding)이라고도 하며 수많은 다형성 중 하나의 예시입니다.

### 콘솔 출력

[https://edu.goorm.io/learn/lecture/19448/한-눈에-읽는-자바-기초/lesson/934045/콘솔-출력](https://edu.goorm.io/learn/lecture/19448/%ED%95%9C-%EB%88%88%EC%97%90-%EC%9D%BD%EB%8A%94-%EC%9E%90%EB%B0%94-%EA%B8%B0%EC%B4%88/lesson/934045/%EC%BD%98%EC%86%94-%EC%B6%9C%EB%A0%A5)

```java
import java.io.*;
class Main {
	public static void main(String[] args) {		
		System.out.println("제 이름은 [김재환] 입니다.");
		System.out.println("제 나이는 [22]살 입니다.");
	}
}
```


### 정리 문제
https://edu.goorm.io/learn/lecture/19448/%ED%95%9C-%EB%88%88%EC%97%90-%EC%9D%BD%EB%8A%94-%EC%9E%90%EB%B0%94-%EA%B8%B0%EC%B4%88/lesson/934048/%EC%A0%95%EB%A6%AC
