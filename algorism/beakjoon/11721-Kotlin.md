# 백준 알고리즘 11721번 문제
* 제목 : 열 개씩 끊어 출력하기
* URL : https://www.acmicpc.net/problem/11721  
* 사용언어 : Kotlin

## 문제  
알파벳 소문자와 대문자로만 이루어진 길이가 N인 단어가 주어진다.

한 줄에 10글자씩 끊어서 출력하는 프로그램을 작성하시오.

## 입력
첫째 줄에 단어가 주어진다. 단어는 알파벳 소문자와 대문자로만 이루어져 있으며, 길이는 100을 넘지 않는다. 길이가 0인 단어는 주어지지 않는다.

## 출력
입력으로 주어진 단어를 열 개씩 끊어서 한 줄에 하나씩 출력한다. 단어의 길이가 10의 배수가 아닌 경우에는 마지막 줄에는 10개 미만의 글자만 출력할 수도 있다.

## 풀이
result : 모든 처리결과를 담아 출력하는 변수

String은 배열처럼 다루는 것이 가능하기 때문에, 인덱스가 0이 아니면서 10으로 나눠지는 부분에서만 개행처리를 해주었다

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val text = stdIn.next()
    var result = ""

    for(index: Int in text.indices) {
        if(index != 0 && index % 10 == 0) {
            result += "\n" + text[index]
        } else {
            result += text[index]
        }
    }

    print(result)
}
```