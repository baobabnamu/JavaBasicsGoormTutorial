## 14 다형성

### 다형성이란?

다형성은 **객체가 다양하게 표현될 수 있다는 개념**입니다.

클래스의 관점에서는 부모의 클래스를 활용하여 자식의 클래스를 제어할 수 있다는 뜻입니다.

결국 자식 클래스는 부모 클래스의 멤버를 상속 받기 때문입니다.

### 상속과 다형성

다형성은 위에서 언급했던 것처럼 객체를 다양하게 표현할 수 있습니다.’

그 예로 아래 코드를 들 수 있습니다.

`Cat` 클래스는 `Lion` 클래스는 같은 부모 클래스를 가지지만 서로 다른 메소드를 가지고 있습니다.

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
