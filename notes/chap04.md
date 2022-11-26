## 04 연산자

### 대입연산자(=)

대입 연산자는 우측 값을 좌측에 대입하고자 할 때 사용하는 연산자입니다.

좌측과 우측의 자료형이 동일할 때만 대입 연산자를 사용할 수 있으며, 자료형이 다른 경우 타입 캐스팅을 통해 자료형을 일치시켜야 합니다.

```java
import java.io.*;
class Main {
	public static void main(String[] args) throws Exception {
		int a = 100;
		System.out.print(a);
	}
}
```

### 산술연산자(+, -, /, % *)

해당 부분은 생략합니다.

### 복합대입연산자

복합 대입 연산자는 대입 연산자와 산술 연산자를 함께 사용한 연산자를 말합니다.

그 종류로는 `+=`, `-=`, `/=`, `%=`, `*=` 가 있습니다.

연산자 왼쪽 값에 오른쪽 값을 산술연산 후 결과 값을 왼쪽에 대입하는 방식을 사용합니다.

```java
import java.io.*;
class Main {
    public static void main(String[] args) throws Exception {
        int a = 1;
        a += 2;	// a = a + 2; 와 같음
        System.out.println(a);

        int b = 5;
        b -= 1;	// b = b - 1; 과 같음
        System.out.println(b);
	
        int c = 2;
        c *= 3;	// c = c * 3; 과 같음
        System.out.println(c);

        int d = 6;
        d /= 2;	// d = d / 2; 와 같음
        System.out.println(d);

        int e = 9;
        e %= 2;	// e = e % 2; 와 같음
        System.out.println(e);
    }
}
```

### 비교 연산자

비교 연산자는 연산자의 좌우 값을 비교하여 `boolean` 타입 값인 true/false를 반환하는 연산자입니다.

```java
import java.io.*;
class Main {
    public static void main(String[] args) throws Exception {
        int a = 4;
        int b = 3;
        System.out.println(a < b); // false
    }
}
```

### 전위/후위 연산자

전위/후위 연산자는 `int` 자료형에서 사용할 수 있는 연산자입니다.

종류로는 `++`, `--` 가 있습니다.

사용하는 위치에 따라 전위/후위로 구분할 수 있습니다.

전위 연산자의 경우 해당 행에서 값을 바로 변경하며 ++인 경우 1를 더하고 -- 인 경우 1를 뺍니다.

후위 연산자의 경우 다음 행에서 값을 변경하며 값 변화는 전위 연산자와 동일합니다.

```java
import java.io.*;
class Main {
    public static void main(String[] args) throws Exception {
        int a = 5;
        ++a;
        System.out.println(a); // 6
			
        int b = 1;
        b++;
        System.out.println(b); // 2
			
        int c = 3;
        --c;
        System.out.println(c); // 2
			
        int d = 6;
        d--;
        System.out.println(d); // 5
    }
}
```

### 논리연산자

논리연산자는 비교 연산자를 조합한 true/false에 대한 논리조합 입니다.

`AND(&&)`, `OR(||)`, `NOT(!)` 로 구분할 수 있습니다.

```java
package project;

public class Main {

    /**
     * @param args
     */
    public static void main(String[] args) {
        
      System.out.println(true && true);		// true이고 true이면 true
      System.out.println(true && false);	// true이고 false이면 false
      System.out.println(false && true);	// false이고 true이면 false
      System.out.println(false && false);	// fasle이고 false이면 false
 
      System.out.println(true || true);		// true이거나 true이면 true
      System.out.println(true || false);	// true이거나 false이면 true
      System.out.println(false || true);	// false이거나 true이면 true
      System.out.println(false || false);	// flase이거나 false이면 false

      int a = 3;
      int b = 4;
      System.out.println(!(a == b)); // true
    }

}
```

### 비트/시프트 연산자

비트연산자는 비트 단위의 연산을 위한 연산자입니다.

1. `&` 연산자
    
    같은 위치의 비트를 비교 했을 때 모두 1이면 1
    
2. `|` 연산자
    
    같은 위치의 비트를 비교 했을 때 하나라도 1이면 1
    
3. `^` 연산자
    
    비트가 0이면 1로, 1이면 0
    
4. `~` 연산자
    
    같은 위치의 비트를 비교 했을 때 일치하지 않는다면 1
    

시프트연산자는 비트를 좌, 우로 밀어주는 연산자입니다.

1. `<<` 시프트 연산자는 비트를 왼쪽으로 밀어내고 공백은 0으로 채웁니다.
    
    `01100111 << 2` 의 결과 값은 `10011100` 입니다.
    
2. `>>`  시프트 연산자는 비트를 오른쪽으로 밀어내지만 공백을 0으로 채우는 것이 아니라, 밀어내기 전 가장 왼쪽에 있는 비트와 동일한 값으로 채웁니다.
    
    `01100111 >> 2`의 결과 값은 `00011001` 입니다.
    
    `10011000 >> 2`의 결과 값은 `11100110` 입니다.
    
3. `>>>` 시프트 연산자는 비트를 오른쪽으로 밀어내고 공백은 0으로 채웁니다.
    
    `01100111 >>> 2`의 결과 값은 `0011001` 입니다.
    

### 연산자 우선순위

1. 괄호
2. 전위연산자
3. 산술연산자
4. 시프트연산자
5. 비교연산자
6. 대입연산자
7. 후위연산자

### 오버플로, 언더플로

기본적으로 컴퓨터는 0, 1를 표현할 때 2진수 형태로 데이터를 저장합니다.

예시로 10이라는 수를 저장하기 위해서는 몇 bit가 필요할까요?

10이라는 수를 저장하기 위해서는 부호를 표현하는 맨 앞 비트를 포함하여 `01010` 총 5bit가 필요합니다. 

이때, 맨 앞 비트의 0은 양수를 의미하고 1은 음수를 의미합니다.

그렇다면 int형은 4byte(32bit, 1byte=8bit)인데, 어떤 숫자들을 표현할 수 있을까요?

맨 앞 비트는 양수/음수를 표현하기 위한 비트이고, 2의 31승 표현할 수 있습니다.

이는 값으로 치면 `-2,147,483,647`에서 `2,147,483,647` 입니다.

오버플로와 언더플로는 이 범위에 해당하지 않는 값을 저장할 때 발생합니다.

1. 오버플로 : 2,147,483,647 보다 큰 값을 저장할 때 발생
    - 예시)
        - 가상의 데이터 타입 ‘test’가 있습니다.
        - 해당 데이터 타입은 1Byte 크기의 값을 표현할 수 있습니다.
        - 맨 첫 번째 비트는 부호를 표현하기 위한 부호 자리입니다.
        - 해당 데이터 타입을 사용하여 변수를 선언하고 127 + 1를 실행합니다.
        - 127은 `0111 1111` 이고, 1는 `0000 0001` 입니다.
        - 이에, `1111 1111` 가 될 것입니다.
        - 우리의 상식으로는 128를 출력해야 알맞다고 생각하지만, `-127`이 출력됩니다.
        - 부호 비트 때문입니다.
        - 이러한 경우를 오버플로 오류라고 합니다.
    - 코드 예시
        
        ```java
        import java.io.*;
        class Main {
            public static void main(String[] args) {
                // short형 변수 varShort를 선언하고 short형의 최대값으로 초기화
                short varShort = Short.MAX_VALUE;
        			
                //varShort 출력
                System.out.println(varShort); // 32767
        			
                //varShort 변수에 1을 더함
                varShort++;
        			
                //varShort 출력
                System.out.println(varShort); // -32768
            }
        }
        ```
        
2. 언더플로 : -2,147,483,647 보다 작은 값을 저장할 때 발생
    - 예시)
        - 가상의 데이터 타입 ‘test’가 있습니다.
        - 해당 데이터 타입은 1Byte 크기의 값을 표현할 수 있습니다.
        - 맨 첫 번째 비트는 부호를 표현하기 위한 부호 자리입니다.
        - 해당 데이터 타입을 사용하여 변수를 선언하고 -128 + -1를 실행합니다.
        - -128은 `1111 1111` 이고 -1는 `1000 0001` 입니다.
        - 이때, 언더플로 오류가 발생하며 `0111 1111` 로 변경됩니다.
        - 언더플로 오류 발생으로 인해 예상치 못한 값(양수 부호)으로 변경되는 것을 알 수 있습니다.
    - 코드 예시
        
        ```java
        import java.io.*;
        class Main {
            public static void main(String[] args) {
                // short형 변수 varShort를 선언하고 short형의 최소값으로 초기화
                short varShort = Short.MIN_VALUE;
                    
                //varShort 출력
                System.out.println(varShort); // -32768
                    
                //varShort 변수에 1을 차감함
                varShort--;
                    
                //varShort 출력
                System.out.println(varShort); // 32767
        
            }
        }
        ```
        

프로그래머는 오버플로와 언더플로를 막기 위해서 언제나 데이터 타입의 크기를 명확하게 인지하고 적절한 크기의 자료형을 사용하는 데 유의해야 합니다.
