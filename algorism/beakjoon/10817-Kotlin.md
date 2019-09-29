# 백준 알고리즘 10817번 문제
* 제목 : 세 수
* URL : https://www.acmicpc.net/problem/10817  
* 사용언어 : Kotlin

## 문제  
세 정수 A, B, C가 주어진다. 이때, 두 번째로 큰 정수를 출력하는 프로그램을 작성하시오. 

## 입력
첫째 줄에 세 정수 A, B, C가 공백으로 구분되어 주어진다. (1 ≤ A, B, C ≤ 100)

## 출력
두 번째로 큰 정수를 출력한다.

## 풀이
최대값, 최소값을 구한 뒤 입력받은 세 정수 - min - max 값을 해주면 중간값이 나오게 된다.

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val a = stdIn.nextInt()
    val b = stdIn.nextInt()
    val c = stdIn.nextInt()

    var max = a
    if(max < b) max = b
    if(max < c) max = c

    var min = a
    if(min > b) min = b
    if(min > c) min = c

    print(a + b + c - max - min)
}
```