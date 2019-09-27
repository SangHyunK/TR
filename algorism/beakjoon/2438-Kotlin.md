# 백준 알고리즘 2438번 문제
* 제목 : 별찍기 - 1
* URL : https://www.acmicpc.net/problem/2438  
* 사용언어 : Kotlin

## 문제  
첫째 줄에는 별 1개, 둘째 줄에는 별 2개, N번째 줄에는 별 N개를 찍는 문제

## 입력
첫째 줄에 N(1 ≤ N ≤ 100)이 주어진다.

## 출력
첫째 줄부터 N번째 줄까지 차례대로 별을 출력한다.

## 참고
a until b : a 부터 b까지 (b제외)  
a .. b : a 부터 b까지 (b포함)

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val n = stdIn.nextInt()

    for(line: Int in 0 until n) {
        for(star: Int in 0..line) {
            print("*")
        }
        println()
    }
}
```