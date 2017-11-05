#메소드(method)

**메소드 란 코드를 재사용할 수 있게 해준다.**

###메소드의 형식
![](https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/516/1834.gif)

이것이 메소드다. 이클립스 에서 처음 프로젝트를 생성하고 클래스 를 생성할때(옵션 에 따라 다르지만) 자동으로 생기는게 바로 main 이라고 하는 것이 메소드인것이다.

이번 파트 에서는  핑크색으로 강조된 부부만 신경쓰자

###메소드 의 정의 와 호출

```java
public class MethodDemo1 {
    public static void numbering() {
        int i = 0;
        while (i < 10) {
            System.out.println(i);
            i++;
        }
    }
 
    public static void main(String[] args) {
        numbering();
    }
}

결과
0
1
2
3
4
5
6
7
8
9
```

아래 그림을 보며 이해하자

![](https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/516/1835.gif)

위 의 그림에서는 numbering이라는 이름의 메소드를 정의하고 있다.
이 메소드는 main이라는 이름의 메소드 안에서 호출되고있다.

위의 코드는 아래의 코드와 정확하게 동일한 의미를 갖는다.

![](https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/516/1836.gif)

핑크색으로 표시한 부분의 코드를 numbering이라는 이름의 메소드로 묶어서 외부로 분리한 것이다. 그리고 메소드 numbering의 로직이 필요할 때 numbering();이라고하면 메소드 numbering의 로직이 실행된다.

위의 메소드 가 없엇다면 0부터 9까지 5번을 출력해야한다면

동일한 소스가 5번이나 붙여넣기 를 해야 될것이다.
코드가 매우 길어지고 더러워진다.
<hr>



###입력(input) 과 출력(output)

예를들어 스마트폰 도 사용자의 의해 반응을 한다.
사용자가 스마트폰 키보드 를 터치하면 터치한 문자들을 출력해준다.

###매개변수 와 인자

메소드의 입력 값은 매개변수(parameter)를 통해서 이루어진다.
필요에 따라서 0부터 4까지 출력하고 싶거나 0부터 8까지 출력하고 싶다면 어떻게 해야 할까?
입력 값에 따라서 다른 출력 값을 갖도록 메소드를 정의하면 된다.

```java
public class MethodDemo4 {
    public static void numbering(int limit) {
        int i = 0;
        while (i < limit) {
            System.out.println(i);
            i++;
        }
    }
 
    public static void main(String[] args) {
        numbering(5);
    }
}
```

결과는 0부터 4까지 출력한다.
값에 따라서 다른 결과가 출력된다. 입력을 통해서 메소드의 동작을 제어하고있다. 

아래 그림을 참고
![](https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/516/1838.gif)

메소드 numbering의 괄호 안에 위치한 숫자 5는 이 메소드가 호출될 때 limit이라는 변수의 값이 된다. 이 값은 메소드 numbering의 중괄호 안에서만 사용할 수 있다.

위의 코드는 아래와 같다.
```java
public static void numbering() {
    int limit = 5;
    int i = 0;
    while (i < limit) {
        System.out.println(i);
        i++;
    }
}
```

여기서 limit이라는 변수는 메소드 numbering의 정의 부에 있는 로직들에게 5라는 값을 전달하고 있다. 호출에서 입력한 값을 로직으로 매개 한다는 의미에서 이러한 변수를 **매개변수**라고 부른다. 영어로는 **parameter**다. 그리고 메소드를 호출할 때 전달된 값인 5를 '인자' 영어로는 **argument**라고 한다. 관습적으로는 매개변수와 인자를 구분하지 않고 부르는 경우도 많다.

###복수의 인자(argument)

메소드로 여러개의 입력값을 전달하고 싶다면?
위의 예제를 개선해서 출력할 숫자의 시작 값 과 마지막 값을 입력값으로 전달하는 예제

```java
public class MethodDemo5 {
 
    public static void numbering(int init, int limit) {
        int i = init;
        while (i < limit) {
            System.out.println(i);
            i++;
        }
    }
 
    public static void main(String[] args) {
        numbering(1, 5);
    }
 
}
결과
1
2
3
4
```

위와 같이 입력 값을 복수로 받고 싶다면 콤마 뒤에 매개변수를 정의해주면 된다. 또 이 메소스를 호출할 때는 매개변수의 순서대로 인자를 배치하면 된다.

### 반환값이 있는 메소드

```java
public class MethodDemo6 {
    public static String numbering(int init, int limit) {
        int i = init;
        // 만들어지는 숫자들을 output이라는 변수에 담기 위해서 변수에 빈 값을 주었다.
        String output = "";
        while (i < limit) {
            // 숫자를 화면에 출력하는 대신 변수 output에 담았다.
            output += i;
            i++;
        }
        // 중요!!! output에 담겨 있는 문자열을 메소드 외부로 반환하려면 아래와 같이 return 키워드 뒤에 반환하려는 값을
        // 배치하면 된다.
        return output;
    }
 
    public static void main(String[] args) {
        // 메소드 numbering이 리턴한 값이 변수 result에 담긴다.
        String result = numbering(1, 5);
        // 변수 result의 값을 화면에 출력한다.
        System.out.println(result);
    }
}
```
메소드 내에서 사용한 return은 return 뒤에 따라오는 값을 메소드의 결과로 반환한다. 동시에 메소드를 종료시킨다. 한가지 잊지 말아야 할 점은 return을 통해서 반환할 값의 데이터 형식을 메소드의 이름 옆에 명시해주어야 한다는 것이다.

![](https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/516/1839.gif)

위 의 메소드는 반환값이 있는 메소드 이다. 반환 값이 없다면
아래 메소드 와 같이 void 를 적어준다

![](https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/516/1840.gif)

이 메소드가 출력한 값을 화면에 출력하는 것이 아니라 파일에 기록하고 싶다면 어떻게 해야 할까? 또는 이메일로 보내고 싶다면 어떻게 해야 할까? 

3개의 메소드를 만들고 용도에 따라서 코드를 재작성하는 것도 좋은 방법이다. 하지만 더 좋은 방법은 숫자를 출력하고, 숫자를 파일에 기록하고, 숫자로 이메일을 보내는 작업으로부터 숫자를 계산하는 로직을 분리하는 것이다. numbering은 자신이 어떻게 사용될지 모른다. 누구든지 numbering이라는 메소드를 호출할 때 초기값과 마지막 값을 입력하면 numbering은 숫자를 문자열의 형태로 반환하면 되는 것이다. 코드를 보자.

```java
import java.io.*; // 무시
 
public class MethodDemo7 {
    public static String numbering(int init, int limit) {
        int i = init;
        String output = "";
        while (i < limit) {
            output += i;
            i++;
        }
        return output;
    }
 
    public static void main(String[] args) {
        String result = numbering(1, 5);
        System.out.println(result);
        try { // 무시
            // 다음 행은 out.txt 라는 파일에 numbering이라는 메소드가 반환한 값을 저장합니다.
            BufferedWriter out = new BufferedWriter(new FileWriter("out.txt"));
            out.write(result);
            out.close();
        } catch (IOException e) {
        } // 무시
    }
}
```

코드에서 무시라고 표시된 부분은 지금 단계에서는 이해하기 어려운 것이다. 무시하자. 중요한 것은 numbering이라는 메소드로부터 화면에 출력이라는 구체적인 행위를 제거하고 대신에 처리 결과를 반환하고 있다는 사실이다.

return의 특성에 대해서 조금 더 알아보자. return은 값을 반환하는 동작을 한다. 그런데 이것은 return에 대한 반쪽짜리 설명이다. return은 메소드를 중단시키는 역할도 한다. 코드를 보자. (실행)

```java
public class ReturnDemo {
    public static int one() {
        return 1;
        return 2;
        return 3;
    }
 
    public static void main(String[] args) {
        System.out.println(one());
    }
}
```
위의 코드는 컴파일조차 되지 않는다. 왜냐하면, return 은 메소드를 종료시키는 역할을 하므로 return이 처음 등장한 이후의 구문은 실행되지 않기 때문이다.

하지만 아래의 예제는 문제가 전혀 없다.
```java
public class ReturnDemo2 {
    public static String num(int i) {
        if(i==0){
            return "zero";
        } else if(i==1){
            return "one";
        } else if(i==2){
            return "two";
        }
        return "none";
    }
 
    public static void main(String[] args) {
        System.out.println(num(1));
    }
}
```
return이 여러 번 등장하지만 return이 중복적으로 실행될 가능성이 없기 때문이다. return "none";를 제거하면 컴파일이 되지 않을 것이다.

###복수의 리턴

메소드는 여러 개의 입력 값을 가질 수 있다. 그렇다면 여러 개의 값을 출력하고 싶다면? 
 자바는 문법적으로 그런 기능을 제공하지 않는다. 하나의 변수에 여러개의 값을 담아서 출력하면 된다.
 
```java
public class ReturnDemo3 {
    public static String getMember1() {
        return "최진혁";
    }
 
    public static String getMember2() {
        return "최유빈";
    }
 
    public static String getMember3() {
        return "한이람";
    }
 
    public static void main(String[] args) {
        System.out.println(getMember1());
        System.out.println(getMember2());
        System.out.println(getMember3());
    }
}
```

하나의 메소드는 하나의 값만을 반환할 수 있기 때문에 위와 같이 각각의 회원정보를 반환하는 메소드를 만들었다. 무언가 비정상적이지 않은가? 이번엔 배열을 이용한 아래의 코드를 보자. 맴버를 담고 있는 배열을 반환하고 있다. 간단하지 않은가? 메소드 getMembers가 리턴한 배열을 members 변수에 담았다. 이 변수를 이용해서 여러 개의 데이터를 처리 할 수 있게 된다. (실행)

```java
public class ReturnDemo4 {
 
    public static String[] getMembers() {
        String[] members = { "최진혁", "최유빈", "한이람" };
        return members;
    }
 
    public static void main(String[] args) {
        String[] members = getMembers();
    }
 
}
```