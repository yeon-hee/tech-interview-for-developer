### Programming

📖 Contents

- [Java](#Java)




#### Java

JVM 이란?
Java Virtual Machine 의 줄임말 이며 Java Byte Code를 OS에 맞게 해석 해주는 역할을 한다. Java compiler는 .java 파일을 .class 라는 Java byte code로 변환 시켜 준다. Byte Code 는 기계어가 아니기 때문에 OS에서 바로 실행되지 않는다. 이때 JVM은 OS가 ByteCode를 이해할 수 있도록 해석 해준다. Byte Code는 JVM 위에서 OS상관없이 실행된다. 이런 점이 Java의 가장 큰 장점이라고 할수 있다. OS에 종속적이지 않고 Java 파일 하나만 만들면 어느 디바이스든 JVM 위에서 실행 할 수 있다.


#### 상속

**참조 타입** Teacher = **인스턴스** Student();
- <u>멤버 변수</u>의 경우, 참조 타입에 따라 참조하는 멤버 변수가 달라진다.
- 메소드의 경우, 참조 타입과 무관하게 인스턴스 변수를 참조한다.
