### Programming
<br>


📖 Contents

- [Java](#Java)
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
    - [Field member](#field-member)
    - [동기화(Synchronized)](#%EB%8F%99%EA%B8%B0%ED%99%94synchronized)
    - [ThreadLocal](#threadlocal)
      - [Personal Recommendation](#personal-recommendation)

<br>


#### Java

JVM 이란?
Java Virtual Machine 의 줄임말 이며 Java Byte Code를 OS에 맞게 해석 해주는 역할을 한다. Java compiler는 .java 파일을 .class 라는 Java byte code로 변환 시켜 준다. Byte Code 는 기계어가 아니기 때문에 OS에서 바로 실행되지 않는다. 이때 JVM은 OS가 ByteCode를 이해할 수 있도록 해석 해준다. Byte Code는 JVM 위에서 OS상관없이 실행된다. 이런 점이 Java의 가장 큰 장점이라고 할수 있다. OS에 종속적이지 않고 Java 파일 하나만 만들면 어느 디바이스든 JVM 위에서 실행 할 수 있다.


#### 상속

**참조 타입** Teacher = **인스턴스** Student();
- 멤버 변수의 경우, 참조 타입에 따라 참조하는 멤버 변수가 달라진다.
- 메소드의 경우, 참조 타입과 무관하게 인스턴스 변수를 참조한다.
