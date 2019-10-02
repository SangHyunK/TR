# 백준 알고리즘 2440번 문제
* 제목 : 별찍기 - 3
* URL : https://www.acmicpc.net/problem/2440  
* 사용언어 : Kotlin

## 문제  
첫째 줄에는 별 N개, 둘째 줄에는 별 N-1개, ..., N번째 줄에는 별 1개를 찍는 문제

## 입력
첫째 줄에 N(1 ≤ N ≤ 100)이 주어진다.

## 출력
첫째 줄부터 N번째 줄까지 차례대로 별을 출력한다.

## 풀이
두 번째 for문 횟수를 점점 줄어들게 해주면 된다.

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val inputNumber = stdIn.nextInt()

    for(i in 0 until inputNumber) {
        for(j in i until inputNumber) {
            print("*")
        }
        println()
    }
}
```