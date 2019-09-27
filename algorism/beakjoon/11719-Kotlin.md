# 백준 알고리즘 11719번 문제
* 제목 : 그대로 출력하기2
* URL : https://www.acmicpc.net/problem/11719  
* 사용언어 : Kotlin

## 문제  
입력 받은 대로 출력하는 프로그램을 작성하시오.

## 입력
입력이 주어진다. 입력은 최대 100줄로 이루어져 있고, 알파벳 소문자, 대문자, 공백, 숫자로만 이루어져 있다. 각 줄은 100글자를 넘지 않으며, 빈 줄이 주어질 수도 있고, 각 줄의 앞 뒤에 공백이 있을 수도 있다.

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