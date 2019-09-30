# 백준 알고리즘 1924번 문제
* 제목 : 2007년
* URL : https://www.acmicpc.net/problem/1924  
* 사용언어 : Kotlin

## 문제  
오늘은 2007년 1월 1일 월요일이다. 그렇다면 2007년 x월 y일은 무슨 요일일까? 이를 알아내는 프로그램을 작성하시오.

## 입력
첫째 줄에 빈 칸을 사이에 두고 x(1≤x≤12)와 y(1≤y≤31)이 주어진다. 참고로 2007년에는 1, 3, 5, 7, 8, 10, 12월은 31일까지, 4, 6, 9, 11월은 30일까지, 2월은 28일까지 있다.

## 출력
첫째 줄에 x월 y일이 무슨 요일인지에 따라 SUN, MON, TUE, WED, THU, FRI, SAT중 하나를 출력한다.

## 풀이
'달'을 '일'로 변환해서 문제를 풀었다. 모든 달을 가지고 있는 배열을 만든 뒤 31일까지 가진 달, 30일까지 가진 달 배열을 만들고 입력 받은 달을 기준으로 이전 달의 일 수를 모두 더한 뒤 입력 받은 일을 더했다.

ex) 5월 3일 = 31 + 28 + 31 + 30 + 3 = 123

그 더한 숫자를 나눈 나머지 값은 0~6까지 나오게 되는데 when 문을 이용해 출력을 했다.

ex) 123 % 7 = 4 = 목요일(THU)

## 개선해야 할 점
이 문제는 도움을 받아 풀었는데... 초반에 달을 일로 바꾼다는 발상을 전혀 하지 못했다. 다양한 케이스를 접해보며 이런 문제를 풀어봐야겠다.

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val month = stdIn.nextInt()
    val day = stdIn.nextInt()

    val monthGroup: Array<Int> = arrayOf(1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12)
    val monthGroup1: Array<Int> = arrayOf(1, 3, 5, 7, 8, 10, 12) // 31일까지 존재
    val monthGroup2: Array<Int> = arrayOf(4, 6, 9, 11) // 30일까지 존재

    var result = 0

    for(m: Int in 0 until month) {
        if(monthGroup[m] < month) {
            result += when {
                monthGroup1.contains(monthGroup[m]) -> 31
                monthGroup2.contains(monthGroup[m]) -> 30
                else -> 28
            }
        } else if(monthGroup[m] == month) {
            result += day
        }
    }

    when(result % 7) {
        0 -> println("SUN")
        1 -> println("MON")
        2 -> println("TUE")
        3 -> println("WED")
        4 -> println("THU")
        5 -> println("FRI")
        6 -> println("SAT")
    }
}
```