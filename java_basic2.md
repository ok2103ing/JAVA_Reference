<h1>조건문
1.if문
<br>
<h5>
```java
if(조건식){
	//조건식이 true일 때 수행될 문장들을 적는다
}
또는
if(조건식)문장;  //수행될 문장이 단 하나일 경우 블럭{} 대신 문장을 사용할 수 있다.

if(조건식){
	//true
}else{
	//false
}

if(조건식) 문장;
else 문장;

if(조건식1){
	//조건식1의 연산결과가 true 일때 수행될 문장을 적는다
}else if(조건식2){
	//조건식2의 연산결과가 true 일때 수행될 문장을 적는다
}else if(조건식3){
	//조건식 3의 연산결과가 true 일때 수행될 문장을 적는다
}else{
	마지막에는 보통 else 블록으로 끝나며, else 블럭은 생략가능함
    위의 어느조건식도 만족하지 않을 때 수행될 문장들을 적는다.
}
```
<h5>

```java
package chapter1;

public class FlowEx3 {

	public static void main(String[] args) {
		int score = 45;
		char grade = ' ';
		
		if(score >= 90){
			grade = 'A';
		}else if(score >= 80){
			grade = 'B';
		}else{
			grade = 'C';
		}
		System.out.println("당신의 학점은"+grade+"입니다.");
	}

}
결과
당신의 학점은C입니다.
```
삼항식 표현
```java
package chapter1;

public class FlowEx4 {

	public static void main(String[] args) {
		int score = 45;
		char grade = ' ';
		grade = (score >= 90) ? 'A' : ((score >= 80) ? 'B' : 'C');
		System.out.println("당신의 학점은 " + grade + "입니다");
	}
}
결과
당신의 학점은 C입니다
```

<h2>중첩 if문
<h5>
```java
if(조건식1){
	if(조건식2){
    	조건식 1 과 조건식2 가 모두 true일떄 수행
    }else{
    	조건식1 이 true 이고 조건식2가 false 일때 수행됨
    }
}else{
	조건식1이 false일떄 수행됨
}
```