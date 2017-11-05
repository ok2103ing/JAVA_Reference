<h1>반복문</h1>

<h3>while</h3>

```java
	while(조건){
    	//반복 실행 영역
    }
```

<h3>do ~ while</h3>
```java
	do{
    	한번 실행되는 구문
    }while(조건문)
    {
    	조건을 성립할때까지 반복
    }
```

<h3>for</h3>

```java
	for(초기화; 종료조건; 반복실행){
    	//반복 실행 영역
    }
```

<h3>반복문의 제어</h3>
반복작업을 중간에 중단시키고 싶은경우

```java
for (int i = 0; i < 10; i++) {
   if (i == 5)
   break;
   System.out.println("Coding Everybody " + i);
}
// i 가 5일때 break 문이 실행되면서 반복문이 종료됨
```
실행을 즉시 중단하면서 반복은 지속하게 하고싶은경우
```java
for (int i = 0; i < 10; i++) {
    if (i == 5)
    continue;
    System.out.println("Coding Everybody " + i);
}
// i 가 5일때 로직을 실행하지않고 그 이후 반복과정을 진행함
```

```java
Coding Everybody 0
Coding Everybody 1
Coding Everybody 2
Coding Everybody 3
Coding Everybody 4
Coding Everybody 6
Coding Everybody 7
Coding Everybody 8
Coding Everybody 9
```

<h3>반복문의 중첩</h3>
```java
for (int i = 0; i < 10; i++) {
    for (int j = 0; j < 10; j++) {
    	System.out.println(i + "" + j);
    }
}
```