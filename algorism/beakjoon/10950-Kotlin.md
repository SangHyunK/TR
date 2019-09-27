# 백준 알고리즘 10950번 문제
* 제목 : A + B - 3
* URL : https://www.acmicpc.net/problem/10950  
* 사용언어 : Kotlin

## 문제  
두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.

## 입력
첫째 줄에 테스트 케이스의 개수 T가 주어진다.

각 테스트 케이스는 한 줄로 이루어져 있으며, 각 줄에 A와 B가 주어진다. (0 < A, B < 10)

## 출력
각 테스트 케이스마다 A+B를 출력한다.

## 풀이
맨 첫 줄에 테스트 케이스 숫자를 받고 반복문을 실행.  
안 쪽에서 a + b 연산을 테스트 케이스 수만큼 실행한다.

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val cases = stdIn.nextInt()
    
    for(case: Int in 0 until cases) {
        val a = stdIn.nextInt()
        val b = stdIn.nextInt()
        
        println(a + b)
    }
}
```