<h1> 자바프로그램의 실행과정
<br>
<h5> java 어플리케이션을 실행시켰을때 내부적인 진행순서는 아래와 같다
1. 프로그램의 실행에 필요한 클래스(*.class)를 로드한다.
2. 클래스파일을 검사한다(파일형식, 악성코드 체크)
3. 지정된 클래스 에서 main(String[] args)를 호출한다.

main 메서드의 첫 줄부터 코드가 실행되기 시작하여 마지막 코드까지 모두 실행되면 프로그램이 종료되고
프로그램에서 사용했던 자원들은 모두 반환된다.

<h1> 주석(Comment)
<br>
<h5>주석의 종류는 범위주석 과 한줄 주석이 있다.
범위 주석은 '/\* 와 \*/' 사이의 내용을 주석으로 간주한다
한줄 주석은 // 라인 끝까지의 내용을 주석으로 간주된다

<h1> 변수(Variable)
<h5>변수는 단 하나의 값을 저장할 수 있는 공간이다.

변수의 선언
변수를 사용하기 위해서는 먼저 변수를 선언해야한다.
변수가 선언되면 메모리에 변수의 타입에 알맞은 크기의 저장공간이 확보되어, 값을 저장할 준비가 되는 것.
변수의 이름은 의미에 맞게 정해주는게 좋다
```java
변수타입 변수이름;
int number; //정수형 변수 number를 선언한다.
```

변수를 선언하였다면 변수를 사용하기전에 적절한 값을 저장해주는 것이 필요하다. 이것을 변수의 초기화 라고 한다.

```java
//정수형 변수 number를 선언하고 변수의 값을 10으로 초기화한다.
int number = 10;
//위 문장은 아래의 두 문장과 동일하다.
int number;
number = 10;

int a;
int b;
int x = 10;
int y = 10;

이것과 아래와 같이 간결하게 활용할수있다.
int a, b;
int x= 10, y= 10;
```

변수의 명명규칙
1. 대소문자가 구분되며 길이에 제한이 없다.
2. 예약어를 사용해서는 안된다.
3. 숫자로 시작해서는 안된다.
4. 특수문자는 _ 와 $ 만을 허용한다.

자바 개발자에게 권장하는 규칙
1. 클래스 이름의 첫 글자는 항상 대문자로 한다.
2. 여러 단어로 이루어진 이름은 단어의 첫 글자를 대문자로 한다.
3. 상수의 이름은 모두 대문자로 한다. 여러 단어로 이루어진 경우 _ 로 구분한다.

변수의 타입
모든 변수에는 타입 또는 형 이 있으며, 변수의 타입 따라 저장할 수 있는 값의 종류와 범위가 달라진다.
변수를 선언할 때 저장하고자 하는 값을 고려하여 가장 알맞은 타입을 선택하면 된다.

변수의 타입은 크게 기본형 과 참조형 2가지로 나눌 수 있는데, 기본형 변수는 실제 값을 저장하는 반면,
참조형 변수는 어떤 값이 저장되어 있는 주소를 값으로 갖는다.
참조형 변수 간의 연산을 할수 없으므로 실제 연산에 사용되는 것은 모두 기본형 변수이다.

```java
기본형(Primitive type)
boolean, char, byte, short, int , long, float, double

참조형(Reference type)
8개의 기본형을 제외한 나머지 타입, 객체의 주소를 저장한다.
```
참조형 변수를 선언할 때는 변수의 타입으로 클래스의 이름을 사용하므로 클래스의 이름이 변수의 타입이 된다.
새로운 클래스를 작성한다는 것은 새로운 참조형을 추가하는 셈이다.

참조변수를 선언하는 방법
```java
클래스이름 변수명; // 타입이 클래스 이름인 것들은 모두 참조변수이다.
Date today;

참조변수는  null 또는 객체의 주소를 값으로 갖으며 참조변수의 초기화는 다음과 같다
Date today = null;
또는
Date today = new Date();
```
객체를 생성하는 연산자 new의 연산결과는 생성된 객체의 주소이다. 
이 주소가 대입연산자 = 에 의해서 참조변수 today에 저장되는것.
이제 참조변수 today를 통해서 생성된 객체를 사용할 수 있게 된다.

기본형의 종류 와 크기
![](http://www.javachobo.com/images/p2_2.gif)

8가지의 기본형 과 저장 가능한 값의 범위
![](http://www.javachobo.com/images/p2_3.gif)

특수문자를 표현하는방법
![](http://www.javachobo.com/images/p2_6.gif)

논리형타입 사용
```java
boolean power = true;
```
논리형에는 boolean 한가지 밖에 없다. boolean 형 변수에는 true , false 중 하나를 저장할수있다.
기본값은 false 이다.

문자형 타입 사용
```java
char firstLetter = 'A';

또는

char firstLetter = '\u0041'; // 16진수 41은 10진수로 65
```
문자형 은 유니코드 문자체계를 사용하기 때문에 크기가 2byte이다

문자형을 숫자형으로 바꿀수있다.

```java
package chapter1;

public class CharToCode {

	public static void main(String[] args) {
		char ch = 'A';
		int code = (int)ch;	//ch에 저장된 값을 int형으로 변환하여 저장한다.
		System.out.println(ch);
		System.out.println(code);

	}
}

결과
A
65
```
숫자형을 문자형으로 바꿀수있다.
```java
package chapter1;

public class CodeToChar {

	public static void main(String[] args) {
		int code = 65;
		char ch = (char)code;
		
		System.out.println(code);
		System.out.println(ch);

	}

}
결과
65
A
```

문자열 출력
```java
package chapter1;

public class SpecialChar {

	public static void main(String[] args) {
		char single = '\'';
		String dblQuote = "\"Hello\"";
		String root = "c:\\";	
		System.out.println(single);
		System.out.println(dblQuote);
		System.out.println(root);
	}
}
결과
'
"Hello"
c:\
```
String 은 클래스 이므로 String name = new String("java"); 와 같이 연사자 new를 사용해야 하지만
위와같이 표현도 가능하다.
그리고 덧셈 연산자를 이용하여 문자열을 결합할수있다.

정수형
정수형에는 모두 4개의 자료형이 있으므로 저장할 수 이쓴ㄴ 값의 범위가 서로 다르다. 크기순으로 나열하면 아래와 같다.
byte < short < int < long
<br>

실수형
실수형에는 float 와 double 두 가지가 있으며 실수를 저장하는 데 사용된다.
보다 정밀도를 요구하는 계산에서는 double를 사용해야한다.
float형 리터럴 에는 접미사 f가 사용되고, dobule은 d가 사용된다 d는 생략가능하다

<h1>형변환(Casting)
<h5>형변환이란 변수 또는 리터럴의 타입을 다른 타입으로 변환하는것이다.
형변환 을 사용할수있는 때는 다른 타입 의 연산을 할떄 사용된다.

자동형변환
![](https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/516/1822.gif)

수동형변환
![](https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/516/1823.gif)

형변환 방법
```java
int score = (int)85.4; //double형 값을 int형으로 변환하여 score에 85가 저장된다
byte b = (byte)score; // score에 저장된 값을 byte형으로 변환하여 byte에 저장된다.
여기서 사용된 ()은 형변환 연산자 라고 불린다.
```

```java
package chapter1;

public class CastingEx1 {

	public static void main(String[] args) {
		double d = 100.0;
		int i = 100;
		int result = i + (int)d;
		
		System.out.println("d="+d);
		System.out.println("i="+i);
		System.out.println("result="+result);
	}

}
결과
d=100.0 <- 형변환 후에도 피연산자에는 아무런 변화가 없다.
i=100
result=200
```
<br>
