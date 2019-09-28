# 백준 알고리즘 9498번 문제
* 제목 : 시험 성적
* URL : https://www.acmicpc.net/problem/9498  
* 사용언어 : Kotlin

## 문제  
시험 점수를 입력받아 90 ~ 100점은 A, 80 ~ 89점은 B, 70 ~ 79점은 C, 60 ~ 69점은 D, 나머지 점수는 F를 출력하는 프로그램을 작성하시오.

## 입력
첫째 줄에 시험 점수가 주어진다. 시험 점수는 0보다 크거나 같고, 100보다 작거나 같은 정수이다.

## 출력
시험 성적을 출력한다.

## 풀이
Int 타입은 나눴을 때 정수부만 남는 성질을 이용한 방법 (kotlin의 when구문 사용)

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val score = stdIn.nextInt()
    
    when(score / 10) {
        6 -> println("D")
        7 -> println("C")
        8 -> println("B")
        9, 10 -> println("A")
        else -> println("F")
    }
}
```