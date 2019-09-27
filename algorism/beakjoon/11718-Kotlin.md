# 백준 알고리즘 11718번 문제
* URL : https://www.acmicpc.net/problem/11718  
* 사용언어 : Kotlin

## 문제  
입력 받은 대로 출력하는 프로그램을 작성하시오.

## 입력
입력이 주어진다. 입력은 최대 100줄로 이루어져 있고, 알파벳 소문자, 대문자, 공백, 숫자로만 이루어져 있다. 각 줄은 100글자를 넘지 않으며, 빈 줄은 주어지지 않는다. 또, 각 줄은 공백으로 시작하지 않고, 공백으로 끝나지 않는다.

## 풀이
hasNextLine라인 사용
- hasNextLine : 다음 라인이 존재하면 true, 그 외 false
- hasNext : 토큰(hasNext 메서드에 아무런 인자를 주지 않으면 공백이 토큰인듯?)이 존재하면 true, 아니면 false

## 코드
```kotlin
import java.util.Scanner

fun main(args: Array<String>): Unit {
    val stdIn = Scanner(System.`in`)

    while(stdIn.hasNextLine()) {
        println(stdIn.nextLine())
    }
}
```