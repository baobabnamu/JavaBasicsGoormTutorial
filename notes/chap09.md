## 09 String

### 배열과 String

배열은 연속된 자료들을 저장하는 자료형입니다.

만약 자바에서 문자열을 표현하고자 한다면 어떻게 표현할 수 있을까요?

char 형을 배열로 받으면 되지 않을까요?

다만 위와 같이 char 형의 배열로 받는 경우, 정의한 배열의 크기만큼만 문자를 받을 수 있는 단점이 있습니다.

- **char 형을 배열로 받는 건 C 프로그래밍에서만 가능합니다.**

`String` 형은 이러한 단점을 상쇄 시켜줍니다.

```java
import java.io.*;
class Main {
        public static void main(String[] args) throws Exception {
            
            String str;
            str = "GURUM";
            
            System.out.println(str);

            char [] cArr = new char[5];
            //cArr = "GURUM"; 이렇게 사용하는 것은 불가능합니다.
        }
}
```

`String` 자료형으로 선언된 변수 `str` 에는 우리가 이제까지 초기화한 문자열을 입력할 수 있지만, char형 배열에는 주석 처리된 방법 처럼 저장할 수 없습니다.

굳이 char형 배열로 저장하고 싶다면 일일이 인덱스를 지정하여 `cArr[0] = ‘G’` 형태로 하나하나 저장해야 합니다.

### Char 심화 이론 : ASCII 코드

`ASCII 코드` 란 1바이트로 표현할 수 있는 숫자를 각각의 문자와 매칭 시킨 코드입니다.

`swtich` 문의 `case` 문은 `int` 형의 값만 인식할 수 있습니다.

이때, 문자형인 경우 ASCII 코드를 활용하여 case 문에 응용할 수 있습니다.

`‘A’ = 65 / ‘a’ = 97`

```java
import java.io.*;
class Main {
	public static void main(String[] args) throws Exception {
		char a = 'A';
		
		switch(a) {
			case 65:
				System.out.println("a is A");
				break;
			default:
				System.out.println("a == ?");
		}
	}
}
```

### String 심화 이론

문자열을 저장할 때는 문자열의 끝을 나타내는 `0(Nul)` 를 반드시 고려해야 합니다.

컴퓨터는 공백 또한 하나의 문자로 인식합니다.

만약 `String hello = “Hello Java”`를 통해 hello 변수를 저장하면 실제 공간을 차지하는 것은 11 Byte 입니다.

`H, e, l, l, o, 공백, J, a, v, a, Nul` 순으로 구성됩니다.

이때, `Nul`은 출력되지 않으므로 프로그래머가 항상 이를 고려하고 있어야 합니다.

### String 추가로.…

String 형은 참조형인데도 불구하고 `new` 키워드를 사용하지 않습니다.

String 변수 선언과 동시에 메모리 공간이 할당되므로 바로 변수로 사용할 수 있습니다.

단, String은 Class 형태로 이루어져 있으며 내부에 더 다양한 기능이 포함되어 있습니다. (캡슐화)

자세한 내용은 클래스 파트에서 정리하도록 하겠습니다.
