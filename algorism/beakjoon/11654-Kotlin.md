# 백준 알고리즘 11654번 문제
* 제목 : 아스키 코드
* URL : https://www.acmicpc.net/problem/11654  
* 사용언어 : Kotlin

## 문제  
알파벳 소문자, 대문자, 숫자 0-9중 하나가 주어졌을 때, 주어진 글자의 아스키 코드값을 출력하는 프로그램을 작성하시오.

## 입력
알파벳 소문자, 대문자, 숫자 0-9 중 하나가 첫째 줄에 주어진다.

## 출력
입력으로 주어진 글자의 아스키 코드 값을 출력한다.

## 풀이
형변환에 대해 잘 이해하고 있는가를 묻는 문제였던 것 같다.

입력값을 Char 형태로 변환 한 후 Int로 변환하면 아스키 값이 나온다.

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val ascii = stdIn.next()

    print(ascii[0].toInt())
}
```