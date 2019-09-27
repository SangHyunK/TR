# 백준 알고리즘 1000번 문제
* URL : https://www.acmicpc.net/problem/1000  
* 사용언어 : Kotlin

## 문제  
두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.

## 풀이
Java의 Scanner객체를 import 하여 사용했습니다.  
Java와 크게 다른 것은 없지만 코틀린에서 in은 예약어이기 때문에 \`in\`으로 작성해야 합니다.  

## 코드
```kotlin
import java.util.Scanner

fun main(args: Array<String>): Unit {
    val stdIn: Scanner = Scanner(System.`in`)
    val a = stdIn.nextInt()
    val b = stdIn.nextInt()
    
    print(a + b)
}
```