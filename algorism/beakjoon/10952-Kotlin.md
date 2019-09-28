# 백준 알고리즘 10952번 문제
* 제목 : A + B - 5
* URL : https://www.acmicpc.net/problem/10952  
* 사용언어 : Kotlin

## 문제  
두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.

## 입력
입력은 여러 개의 테스트 케이스로 이루어져 있다.

각 테스트 케이스는 한 줄로 이루어져 있으며, 각 줄에 A와 B가 주어진다. (0 < A, B < 10)

입력의 마지막에는 0 두 개가 들어온다.

## 출력
각 테스트 케이스마다 A+B를 출력한다.

## 풀이
특정 문자(0 0)이 들어오면 종료되도록 처리하는 문제이다.

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    
    while(true) {
        val a = stdIn.nextInt()
        val b = stdIn.nextInt()
        
        if(a == 0 && b == 0) break
        
        println(a + b)
    }
}
```