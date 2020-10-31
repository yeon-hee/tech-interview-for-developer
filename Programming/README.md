## Java


📖 Contents

- [JVM 에 대해서, GC 의 원리](#jvm-%EC%97%90-%EB%8C%80%ED%95%B4%EC%84%9C-gc-%EC%9D%98-%EC%9B%90%EB%A6%AC)
  - [Collection](#collection)
  - [Annotation](#annotation)
      - [Reference](#reference)
  - [Generic](#generic)
  - [final keyword](#final-keyword)
  - [Overriding vs Overloading](#overriding-vs-overloading)
  - [Access Modifier](#access-modifier)
  - [Wrapper class](#wrapper-class)
    - [AutoBoxing](#autoboxing)
  - [Multi-Thread 환경에서의 개발](#multi-thread-%ED%99%98%EA%B2%BD%EC%97%90%EC%84%9C%EC%9D%98-%EA%B0%9C%EB%B0%9C)
    - [동기화(Synchronized)](#%EB%8F%99%EA%B8%B0%ED%99%94synchronized)

<br>

## JVM 에 대해서, GC 의 원리

Java Virtual Machine 의 줄임말 이며 Java Byte Code를 OS에 맞게 해석 해주는 역할을 한다. Java compiler는 .java 파일을 .class 라는 Java byte code로 변환 시켜 준다. Byte Code 는 기계어가 아니기 때문에 OS에서 바로 실행되지 않는다. 이때 JVM은 OS가 ByteCode를 이해할 수 있도록 해석 해준다. Byte Code는 JVM 위에서 OS상관없이 실행된다. 이런 점이 Java의 가장 큰 장점이라고 할수 있다. OS에 종속적이지 않고 Java 파일 하나만 만들면 어느 디바이스든 JVM 위에서 실행 할 수 있다.

* [Java Virtual Machine 에 대해서](http://asfirstalways.tistory.com/158)
* [Garbage Collection 에 대해서](http://asfirstalways.tistory.com/159)

</br>

## Collection

Java Collection 에는 `List`, `Map`, `Set` 인터페이스를 기준으로 여러 구현체가 존재한다. 이에 더해 `Stack`과 `Queue` 인터페이스도 존재한다. 왜 이러한 Collection 을 사용하는 것일까? 그 이유는 다수의 Data 를 다루는데 표준화된 클래스들을 제공해주기 때문에 DataStructure 를 직접 구현하지 않고 편하게 사용할 수 있기 때문이다. 또한 배열과 다르게 객체를 보관하기 위한 공간을 미리 정하지 않아도 되므로, 상황에 따라 객체의 수를 동적으로 정할 수 있다. 이는 프로그램의 공간적인 효율성 또한 높여준다.

* List  
  `List` 인터페이스를 직접 `@Override`를 통해 사용자가 정의하여 사용할 수도 있으며, 대표적인 구현체로는 `ArrayList`가 존재한다. 이는 기존에 있었던 `Vector`를 개선한 것이다. 이외에도 `LinkedList` 등의 구현체가 있다.

* Map  
  대표적인 구현체로 `HashMap`이 존재한다. key-value 의 구조로 이루어져 있으며 key 를 기준으로 중복된 값을 저장하지 않으며 순서를 보장하지 않는다.
  
* Set  
  대표적인 구현체로 `HashSet`이 존재한다. `value`에 대해서 중복된 값을 저장하지 않는다. 사실 Set 자료구조는 Map 의 key-value 구조에서 key 대신에 value 가 들어가 value 를 key 로 하는 자료구조일 뿐이다. 마찬가지로 순서를 보장하지 않는다.
  
* Stack 과 Queue  
  `Stack` 객체는 직접 `new` 키워드로 사용할 수 있으며, `Queue` 인터페이스는 JDK 1.5 부터 `LinkedList`에 `new` 키워드를 적용하여 사용할 수 있다. 자세한 부분은 DataStructure 부분의 설명을 참고하면 된다.
  
</br>

## Annotation

어노테이션이란 본래 주석이란 뜻으로, 인터페이스를 기반으로 한 문법이다. 주석과는 그 역할이 다르지만 주석처럼 코드에 달아 클래스에 특별한 의미를 부여하거나 기능을 주입할 수 있다. 또 해석되는 시점을 정할 수도 있다.

</br>

## Generic

제네릭은 자바에서 안정성을 맡고 있다고 할 수 있다. 다양한 타입의 객체들을 다루는 메서드나 컬렉션 클래스에서 사용하는 것으로, 컴파일 과정에서 타입체크를 해주는 기능이다. 객체의 타입을 컴파일 시에 체크하기 때문에 객체의 타입 안전성을 높이고 형변환의 번거로움을 줄여준다. 자연스럽게 코드도 더 간결해진다. 예를 들면, Collection에 특정 객체만 추가될 수 있도록, 또는 특정한 클래스의 특징을 갖고 있는 경우에만 추가될 수 있도록 하는 것이 제네릭이다. 이로 인한 장점은 collection 내부에서 들어온 값이 내가 원하는 값인지 별도의 로직처리를 구현할 필요가 없어진다. 또한 api를 설계하는데 있어서 보다 명확한 의사전달이 가능해진다. 

</br>

## final keyword

* final class
  다른 클래스에서 상속하지 못한다.
  
* final method
  다른 메소드에서 오버라이딩하지 못한다.
  
추가적으로 혼동할 수 있는 두 가지를 추가해봤다.

* finally  
  `try-catch` or `try-catch-resource` 구문을 사용할 때, 정상적으로 작업을 한 경우와 에러가 발생했을 경우를 포함하여 마무리 해줘야하는 작업이 존재하는 경우에 해당하는 코드를 작성해주는 코드 블록이다.
  
</br>

## Overriding vs Overloading

* 오버라이딩(Overriding)
  상위 클래스에 존재하는 메소드를 하위 클래스에서 필요에 맞게 재정의하는 것을 의미한다.
* 오버로딩(Overloading)
  상위 클래스의 메소드와 이름, return값은 돌일하지만, 매개변수만 다른 메소드를 만드는 것을 의미한다. 다양한 상황에서 메소드가 호출될 수 있도록 한다. 

#### 참고 - 상속)

**참조 타입** Teacher = **인스턴스** Student();
- 멤버 변수의 경우, 참조 타입에 따라 참조하는 멤버 변수가 달라진다.
- 메소드의 경우, 참조 타입과 무관하게 인스턴스 변수를 참조한다.

</br>

## Access Modifier

변수 또는 메소드의 접근 범위를 설정해주기 위해서 사용하는 Java 의 예약어를 의미하며 총 네 가지 종류가 존재한다.

* public 
  어떤 클래스에서라도 접근이 가능ㅎ다ㅏ.
  
* protected
  클래스가 정의되어 있는 해당 패키지 내 그리고 해당 클래스를 상속받은 외부 패키지의 클래스에서 접근이 가능하다. 
  
* (default)
  클래스가 정의되어 있는 해당 패키지 내에서만 접근이 가능하도록 접근 범위를 제한한다. 
  
* private
  정의된 해당 클래스에서만 접근이 가능하도록 접근 범위를 제한한다.
  
</br>

## Wrapper class

기본 자료형(Primitive data type)에 대한 클래스 표현을 Wrapper class 라고 한다. `Integer`, `Float`, `Boolean` 등이 Wrapper class 의 예이다. int를 Integer 라는 객체로 감싸서 저장해야 하는 이유가 있을까? 일단 컬렉션에서 제네릭을 사용하기 위해서는 Wrapper class를 사용해줘야 한다. 하지만 이러한 상황을 제외하고 일반적인 상황에서 Wrapper class를 사용해야 하는 이유는 객체지향적인 프로그래밍을 위한 프로그래밍이 아니고서야 없다. 일단 해당 값을 비교할 때, Primitive data type인 경우에는 `==`로 바로 비교해줄 수 있다. 하지만 Wrapper class인 경우네에는 `.intValue()` 메소드를 통해 해당 Wrapper class 의 값을 가져와 비교해줘야 한다.

### AutoBoxing

```java
List<Integer> lists = new ArrayList<>();
lists.add(1);
```

`Integer`라는 Wrapper class로 설정한 collection에 데이터를 add할 때 Integer 객체로 감싸서 넣지 않는다. 자바 내부에서 `AutoBoxing`해주기 때문이다.

</br>

## Multi-Thread 환경에서의 개발

개발을 시작하는 입장에서 멀티 스레드를 고려한 프로그램을 작성할 일이 별로 없고 실제로 부딪히기 힘든 문제이기 때문에 많은 입문자들이 잘 모르고 있는 부분 중 하나라고 생각한다. 하지만 이 부분은 정말 중요하며 고려하지 않았을 경우 엄청난 버그를 양산할 수 있기 때문에 정말 중요하다.

### 동기화(Synchronized)

필드에 Collection 이 불가피하게 필요할 때는 어떠한 방법을 사용할까? Java 에서는 `synchronized` 키워드를 사용하여 스레드 간 race condition 을 통제한다. 이 키워드를 기반으로 구현된 Collection 들도 많이 존재한다. `List`를 대신하여 `Vector`를 사용할 수 있고, `Map`을 대신하여 `HashTable`을 사용할 수 있다. 하지만 이 Collection 들은 제공하는 API 가 적고 성능도 좋지 않다.



