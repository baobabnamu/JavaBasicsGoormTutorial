## 13 상속

### 상속, 부모클래스와 자식클래스

어떤 클래스의 멤버들을 물려주는 것을 **상속** 이라고 합니다.

이때, 물려주는 클래스가 **부모 클래스,** 물려받는 클래스가 ************************자식 클래스************************라고 합니다.

```java
public class Main {

	public static void main(String[] args) {
		Parent p = new Parent();
		Child c = new Child();
		
		p.print();
		c.print();
	}

}

// Parent 클래스 정의
class Parent {
		
	public int iInt;
	
	public void print() {
		System.out.println("Parent Class");
	}
}

// Child 클래스 정의
class Child extends Parent{

}
```

자식 클래스는 `extends` 키워드를 통해 부모 클래스를 상속 받습니다.

자식 클래스는 부모 클래스의 `private` 멤버를 제외한 나머지 멤버들을 물려받습니다.

자식 클래스는 상속 받은 이후에도 다른 멤버를 추가로 가질 수 있습니다.

자식 클래스의 객체가 생성될 때, 부모 클래스의 객체의 생성자 함수가 먼저 호출된 후에 자식 클래스의 생성자 함수가 호출 됩니다.

부모 클래스로부터 상속 받은 모든 멤버들은 접근제한자 `protected` 가 적용되어 있어 자식 클래스 및 부모 클래스 외에 다른 클래스에서는 접근할 수 없습니다.

### 오버라이딩

`오버라이딩(Overriding)` 이란 부모 클래스의 메소드를 재정의하는 것을 말합니다.

`오버로딩(Overloading)`과 다른 점은 매개변수의 타입, 개수까지 동일하다는 것입니다.


```java
public class Main {

	public static void main(String[] args) {
		Parent p = new Parent();
		Child c = new Child();
		
		p.print();
		c.print();
	}

}

// 부모 클래스 정의
class Parent {
		
	public int iInt;
	
	public void print() {
		System.out.println("Parent Class");
	}
}

// 자식 클래스 정의
class Child extends Parent{

	public void print() {
		System.out.println("Child Class");
	}
}
```

### 추상화 & 추상클래스

`추상화`는 상속에서만 사용할 수 있는 개념입니다.

`abstract` 키워드를 통해 추상화 클래스를 정의할 수 있습니다.

추상화 클래스 안에는 추상화 메소드가 존재합니다.

이렇게 별도로, 추상화 클래스를 만드는 이유는 `오버라이딩(Overriding)`을 위해서 입니다.

동물이라는 큰 공통 관심사로 묶고, 이를 관리할 수 있기 때문입니다.

그리고, **추상화 클래스를 상속 받은 자식 클래스가 메소드를 오버라이딩 하지 않으면 자식 클래스들도 추상화 클래스로써 동작합니다.**

동물 밑에 개과 밑에 늑대와 허스키 등이 있는 것처럼 추상 클래스를 상속받은 추상 클래스를 상속받은 클래스가 나올 수도 있는 것입니다.

`super` 키워드는 부모 클래스를 지칭하는 문구입니다.

`super(멤버변수)` 형태로 멤버 변수에 접근하여 사용합니다.

```java
public class Main {
	public static void main(String[] args) {
		
		//Animal animal = new Animal("동물"); 불가능합니다.
		
		Lion lion = new Lion("사자");
		lion.Growl();
		
		Cat cat = new Cat("고양이");
		cat.Growl();
	}
}

abstract class Animal {
	
	String Name;
	
	public Animal(String name) {
		Name = name;
	}
	
	abstract public void Growl(); 
}

class Lion extends Animal {

	public Lion(String name) {
		super(name);
	}

	public void Growl() {		
		System.out.println("어흥");
	}
}

class Cat extends Animal {
	public Cat(String name) {
		super(name);
	}
	
	public void Growl() {		
		System.out.println("야옹");
	}
}
```

### 인터페이스

자바 언어는 다른 프로그래밍 언어와 다르게 다중 상속을 제한하고 있습니다.

`extends` 뒤에 상속받을 수 있는 클래스가 하나라는 뜻입니다.

이럴 때 `interface` 기능을 사용하여 다중 상속을 구현할 수 있습니다.

`interface` 는 추상화 클래스보다 좀 더 추상화된 클래스라고 할 수 있습니다.

아래는 `interface` 의 기본적인 구조입니다. 

```java
interface Example {
	public static final int iVariable;
	// int iVariable만 써도 동일함.
	
	abstract public void method();
	// void method()만 써도 동일함.
}
```

구조 자체는 클래스와 상당히 유사합니다.

하지만, `class` 대신 `interface` 라는 키워드를 사용하며 멤버 변수는 `public static final` 형태만 사용할 수 있고, 메소드는 `abstract public` 형태만 사용할 수 있습니다.

**즉 알맹이는 하나도 없이 뼈대만 세워진 클래스**라는 것을 알 수 있습니다.

`interface` 를 상속 받을 때는 반드시 `extends` 가 아닌 `implements` 로 상속받아야 합니다.

```java
public class Main {
	public static void main(String[] args) {
		MP3Player_Ver1 mp3_ver1 = new MP3Player_Ver1();
		mp3_ver1.Play();
		mp3_ver1.Stop();
		//mp3_ver2.Next(); 불가능 합니다.
		//mp3_ver2.Prev(); 불가능 합니다.
		
		MP3Player_Ver2 mp3_ver2 = new MP3Player_Ver2();
		mp3_ver2.Play();
		mp3_ver2.Stop();
		mp3_ver2.Next();
		mp3_ver2.Prev();
	}
}

class MP3Player_Ver1 implements PlayFunction, StopFunction {
	public void Play() {
		System.out.println("Play_Ver1!");
	}

	public void Stop() {
		System.out.println("Stop_Ver1!");
	}
}

class MP3Player_Ver2 implements PlayFunction, StopFunction, NextFunction, PrevFunction {
	public void Play() {
		System.out.println("Play_Ver2!");
	}

	public void Stop() {
		System.out.println("Stop!_Ver2");
	}
	
	public void Next() {
		System.out.println("Next!_Ver2");
	}
	
	public void Prev() {
		System.out.println("Prev!_Ver2");
	}
}

interface PlayFunction {
	abstract public void Play();
}

interface StopFunction {
	abstract public void Stop();	
}

interface NextFunction {
	abstract public void Next();
}

interface PrevFunction {
	abstract public void Prev();
}
```
