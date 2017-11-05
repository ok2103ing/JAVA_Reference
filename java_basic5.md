<h1>배열(Array)</h1>

**배열 이란 연관된 데이터를 모아서 관리하기 위해서 사용하는 데이터 타입이다.**

**변수가 하나의 데이터를 저장하기 위한 것이라면 배열은 여러 개의 데이터를 저장하기 위한 것이라고 할 수 있다**

<h3>배열의 생성</h3>

```java
public class DefineDemo {
 
    public static void main(String[] args) {
 
        String[] classGroup = { "최진혁", "최유빈", "한이람", "이고잉" };
 
    }
 
}
```
**String[] classGroup에서 classGroup은 배열이 담길 변수의 이름이다.
String[]은 classGroup에 담을 배열에 담길 데이터의 타입이 문자열의 배열이라는 의미이다.**

**배열을 선언할 때는 데이터 타입 뒤에 []를 붙여야 한다.
[]가 없다면 classGroup는 배열이 아니라 문자열 데이터 타입을 갖는 변수가 된다. 
배열에 소속될 데이터들은 중괄호 안에 위치한다. 그리고 각각의 데이터들은 쉼표(,)로 구분된다.**

<h3>배열에 담겨있는 데이터를 꺼내오는 방법</h3>

```java
public class GetDemo {
 
    public static void main(String[] args) {
        String[] classGroup = { "최진혁", "최유빈", "한이람", "이고잉" };
        System.out.println(classGroup[0]);
        System.out.println(classGroup[1]);
        System.out.println(classGroup[2]);
        System.out.println(classGroup[3]);
 
    }
 
}

결과
최진혁
최유빈
한이람
이고잉
```

<h3>배열에 담겨 있는 값의 수를 알아내는 방법</h3>

```java
public class LengthDemo {
 
    public static void main(String[] args) {
        String[] classGroup = new String[4];
        classGroup[0] = "최진혁";
        System.out.println(classGroup.length);
        classGroup[1] = "최유빈";
        System.out.println(classGroup.length);
        classGroup[2] = "한이람";
        System.out.println(classGroup.length);
        classGroup[3] = "이고잉";
        System.out.println(classGroup.length);
 
    }
    
결과
4
4
4
4
```

.length 는 배열에 실제 담긴 데이터의 숫자를 의미하는 것이 아니라 배열을 생성할 때 지정한 배열의 크기를 의미한다.

![](https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/516/1841.gif)

위 그림처럼 배열에 담긴 각각의 데이터를 **원소(element)**라고 한다.
classGroup[1]은 최유빈이다. 여기서 [1]은 원소 최유빈을 식별하는 식별자이다. 이러한 식별자를 **인덱스(index)**라고 부른다. 이 **인덱스는 중복되면 안 되기 때문에** 데이터를 입력할 때 **자동으로 1씩 증가**되면서 만들어진다. 이 배열이 담을 수 있는 원소의 개수를 **length**라고 한다.  
위의 그림에 따르면 classGroup의 길이는 4가 된다. **length는 배열에 담긴 원소의 숫자가 아니라 배열을 선언할 때 지정한 배열이 담을 수 있는 값의 크기를 의미한다.**


<h3>배열의 사용</h3>

학교 비유를 통한 배열의 사용

1.1반 학생들을 번호순으로 정렬해서 줄을 세운다.
2.상담받은 학생의 숫자를 기록한다.
3.대기중인 학생과 상담을 한다.
4.상담받은 학생의 수를 1 증가시킨다.
5.총원보다 상담받은 학생의 수가 작다면 3번 절차로 돌아간다.
총원과 상담받은 학생의 수가 같다면 상담을 종료하고 업무를 계속한다.

자바코드 적용

```java
public class ArrayLoopDemo {
 
    public static void main(String[] args) {
 
        String[] members = { "최진혁", "최유빈", "한이람" };
        for (int i = 0; i < members.length; i++) {
            String member = members[i];
            System.out.println(member + "이 상담을 받았습니다");
        }
 
    }
 
}

결과
최진혁이 상담을 받았습니다
최유빈이 상담을 받았습니다
한이람이 상담을 받았습니다
```
<br>
**배열을 사용할때 향상된 for문(JDK 5이상 부터 사용가능)**

```java
public class ForeachDemo {
 
    public static void main(String[] args) {
        String[] members = { "최진혁", "최유빈", "한이람" };
        for (String e : members) {
            System.out.println(e + "이 상담을 받았습니다");
        }
    }
 
}
```

for(String e : members)

위의 구문은 배열 members의 값을 변수 e에 담아서 중괄호 구간 안으로 전달해준다. 반복문의 종료조건이나 종료조건을 위해서 기준값을 증가시키는 등의 반복적인 작업을 내부적으로 감춘 것이라고 할 수 있다.

<h3>배열을 사용할 때 흔히 발생하는 오류</h3>

```java
String[] members = { "최진혁", "최유빈", "한이람" };
System.out.println(members[3]);     

Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 3
    at ot_array.ExceptionDemo.main(ExceptionDemo.java:7)
```

ArrayIndexOutOfBoundsException은 존재하지 않는 인덱스를 사용하려고 했을 때 발생한다. 배열 members는 인덱스가 2까지 존재하는데 3을 사용했기 때문에 발생한 오류이다.

**배열은 무조건 0부터 시작한다**
