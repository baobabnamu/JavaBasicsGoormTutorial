## 11 데이터 입출력

### 키보드 데이터 입력 받기 (1)

`콘솔` 은 대표적인 CLI 개발 환경으로, 글자를 이용한 입출력 환경을 뜻합니다.

위 예제들에서 사용해왔던 `print()`, `println()` 함수는 출력 함수입니다.

이번에는 입력 함수들을 가지고 있는 `Scanner` 클래스에 대해서 알아보도록 하겠습니다.

아래와 같이 `Scanner` 클래스는 객체로 생성하여 사용할 수 있습니다.

- `nextInt()` / `nextDouble()` 같은 함수로 입력을 받을 수 있습니다.
- `next자료형()` 함수가 실행되는 동안 자바 프로그램은 더 이상 진행되지 않습니다.

```java
import java.io.*;
import java.util.Scanner;	// Scanner 사용시 명시 필수!

class Main {
	public static void main(String[] args) {
		int iVal;
		double dVal;		
		
		Scanner scanner = new Scanner(System.in);
		
		System.out.print("정수를 입력해주세요 : ");
		iVal = scanner.nextInt();				
		System.out.println("입력 정수 : " + iVal);
		
		System.out.print("실수를 입력해주세요 : ");
		dVal = scanner.nextDouble();				
		System.out.println("입력 실수 : " + dVal);
	}
}
```

### 키보드 데이터 입력 받기 (2)

데이터 입력을 받을 때는 `Scanner` 클래스 뿐만 아니라 `BufferedReader` 라는 클래스도 종종 사용합니다.

Scanner 달리 별도의 라이브러리를 import 할 필요는 없습니다. 

다만, 반드시 `throws` 문을 사용해야 합니다.

```java
import java.io.*;

class Main {
    public static void main(String[] args) throws Exception {
        
    	String sVal;
    	
		// BufferedReader 초기화
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        
        System.out.print("문자열을 입력해주세요 : ");
        sVal = br.readLine();
        System.out.println("입력 문자열 : " + sVal);
        br.close();
    }
}
```

`BufferedReader br = new BufferedReader(new InputStreamReader(System.in));`

- BufferedReader 클래스의 br 이라는 객체 변수를 선언한다.
- `new` 키워드를 통해 객체 변수가 동작할 수 있도록 `BufferedReader` 클래스 크기만큼 메모리 공간을 만들어준다.
- 이때 `BufferedReader` 클래스의 생성자 함수를 실행한다.
- 두 번째 `new` 키워드를 통해 `BufferedReader` 의 생성자 함수에 필요한 인자인 `InputStreamReader` 클래스 크기만큼 메모리 공간을 만들어준다.
- `InputStreamReader` 클래스의 생성자 함수의 인자로 `System.in` 를 사용한다.

`sVal = br.readLine();`

- `readLine()` 은 입력되는 줄 전체를 `string` 형태로 반환해주는 메소드입니다.

`br.close();`

- BufferedReader 객체를 다 사용했다면 close() 를 통해 반드시 종료해 줘야 합니다.

### 데이터를 파일로 출력하기

출력한 데이터를 자바프로그램이 종료된 이후에도 사용하고 싶은 경우, 파일로 `Export` 해야 합니다.

파일 형태로 데이터를 출력하는 방법에 대해서 알아봅니다.

```java
import java.io.*;

class Main {
    public static void main(String[] args) throws Exception {
        
    	BufferedWriter bw = new BufferedWriter(new FileWriter(new File("data/test.txt")));
    	
    	String str = "Hello Goorm Java Class!";
    	bw.write(str);
    	
    	bw.close();
    }
}
```

`BufferedWriter bw = new BufferedWriter(new FileWriter(new File("data/test.txt")));`

- `BufferedWriter` 는 컴퓨터가 데이터를 출력할 때 사용하는 클래스입니다.
- `FileWriter` 는 컴퓨터가 파일에 데이터를 작성할 때 사용하는 클래스입니다.
- `File` 클래스는 사용할 파일 주소의 경로를 파라미터로 입력받아 해당 파일의 정보를 가지고 있는 클래스입니다.

`bw.write(str);`

- 코드가 실제로 데이터를 작성할 때 사용되는 함수입니다.

bw.close();

- `BufferedWriter` 클래스도 사용이 종료되면 반드시 `close()` 함수를 호출해야 합니다.
- 만약, `close()` 함수를 호출하지 않을 경우 데이터가 정상적으로 저장되지 않을 수 있습니다.

### 데이터를 파일에서 입력받기

이번에는 저장한 파일에서 데이터를 입력 받아오는 방법에 대해서 알아보도록 하겠습니다.

`BufferedReader` 클래스를 사용하되, 매개변수를 `FileReader`와 `File` 클래스를 사용합니다.

```java
import java.io.*;

class Main {
	public static void main(String[] args) throws Exception {
		BufferedReader br = new BufferedReader(new FileReader(new File("data/test.txt")));
		
		String str;
		str = br.readLine();		
		
		br.close();
	}		
}
```

`BufferedReader br = new BufferedReader(new FileReader(new File("data/test.txt")));`

- `BuffereReader` 클래스는 컴퓨터가 데이터를 입력받을 때 사용하는 클래스입니다.
- `FileReader` 클래스는 컴퓨터가 파일의 데이터를 읽어올 때 사용하는 클래스입니다.
- `File` 클래스는 사용할 파일 주소의 경로를 파라미터로 입력받아 해당 파일의 정보를 가지고 있는 클래스입니다.

`str = br.readLine();`

- 파일의 전체를 입력 받습니다.

`br.close();`

- 이전 강의에서 언급했던 것처럼 반드시 `close()` 함수를 사용해야 합니다.

### String 활용하기

### String → Primitive Data Type Casting

```java
import java.io.*;

class Main {
    public static void main(String[] args) {
        
    	String szVal = "3.1";
      double dVal = Double.valueOf(szVal); // szVal 스트링의 값을 불러와 Double 형으로 명시적 형변환
        
      szVal = "41";
      int iVal = Integer.valueOf(szVal); // szVal 스트링의 값을 불러와 int 형으로 명시적 형변환

			szVal = 'C';
			char cVal = szVal.charAt(0); // szVal 첫 번째 char 값을 불러와서 cVal에 저장
    }
}
```

### String 간 비교 함수 - `equals(비교문자열)`

```java
import java.io.*;

class Main {
    public static void main(String[] args) {
        
    	String szVal = "Goorm";
			if(szVal.equals("Gooorm") == true) { // 동일한지 비교하는 함수, boolean 반환
				System.out.println("SAME!!");
			} else {
				System.out.println("Different!!");
			}
    }
}
```

### String 길이 함수 - `length()`

```java
import java.io.*;

class Main {
    public static void main(String[] args) {
        
    	String szVal = "Goorm";
    	int length = szVal.length();
    	System.out.println("Length = " + length);
    	
    	for(int j = 0 ; j < szVal.length() ; j++) { // szVal 객체 변수의 길이 반환
    		System.out.println(szVal.charAt(j));
    	}
    	
    }
}
```

### 문자열 자르기 함수 - `split()`

```java
import java.io.*;

class Main {
    public static void main(String[] args) {
        
    	String szVal = "Goorm/Java/Class";
    	String [] strArr;
    	
    	strArr = szVal.split("/"); // '/'를 구분자로 배열에 저장 -> Goorm Java Class 순으로 저장됨
    	for(int j = 0 ; j < strArr.length ; j++) {
    		System.out.println(strArr[j]);
    	}
    }
}
```
