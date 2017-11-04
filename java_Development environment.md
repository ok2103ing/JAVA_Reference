<h1> 자바 개발환경 구축

1.JDK 설치

JDK 설치사이트
<H3>http://www.oracle.com/technetwork/java/javase/downloads/index.html

![](http://www.oracle.com/ocom/groups/public/@otn/documents/digitalasset/1612441.gif)
JDK 설치사이트 에서 위 모양아이콘을 클릭
자신의 윈도우 버전에 맞는걸 다운로드 한다
다운로드 받은 jdk-8u131-windows-x64 을 실행시켜 C 드라이브 에 설치한다

1.1 JDK 환경변수 등록
아래 사이트 참고
http://enow.co.kr/220518309363

2.편집기 설치
대표적으로 이클립스,에디트플러스 가 있다
이클립스 를 설치한다
https://www.eclipse.org/downloads/eclipse-packages/
자신의 윈도우 버전에 맞는걸 다운로드 한다.

3.자바 컴파일 해보기

```
package chapter1;
public class helloworld {
	public static void main(String[] args) {
		System.out.println("hello, world."); //화면에 글자를 출력한다
	}
}
```
컴파일 후 실행
```
hello, world.
```

위 예제는 화면에 hello, world. 를 출력하는 간단한 프로그램이다.
이 예제를 통해서 글자를 출력하려면 어떻게 해야하는지 쉽게 알수 있다.
위 예제가 올바르게 실행이 되면 앞으로 컴파일을할때 문제없이 컴파일이 될것이다
<br>
<h5> 이클립스 에서 java 파일을 실행시키면 바로 실행되는게 아니고
사용자에 의해서 코드가 작성된 후 
java컴파일러가 컴파일 후 helloworld.class 파일을 생성하고 helloworld.exe 실행 파일 생성한다
<br>

※클래스 를 생성할때에는 클래스명 과 파일명이 일치해야한다.