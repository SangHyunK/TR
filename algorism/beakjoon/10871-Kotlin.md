# 백준 알고리즘 10871번 문제
* 제목 : X보다 작은 수
* URL : https://www.acmicpc.net/problem/10871  
* 사용언어 : Kotlin

## 문제  
정수 N개로 이루어진 수열 A와 정수 X가 주어진다. 이때, A에서 X보다 작은 수를 모두 출력하는 프로그램을 작성하시오.

## 입력
첫째 줄에 N과 X가 주어진다. (1 ≤ N, X ≤ 10,000)

둘째 줄에 수열 A를 이루는 정수 N개가 주어진다. 주어지는 정수는 모두 1보다 크거나 같고, 10,000보다 작거나 같은 정수이다.

## 출력
X보다 작은 수를 입력받은 순서대로 공백으로 구분해 출력한다. X보다 작은 수는 적어도 하나 존재한다.

## 풀이
입력 데이터를 받아오는 부분은 Scanner 객체를 사용했습니다.

result 변수는 String이 아닌 StringBuilder을 사용했는데, result는 반복문 안에서 계속해서 값이 변하기 때문에 StringBuilder을 사용하는 것이 효율이 더 좋습니다.

※ String 객체는 불변객체이기 때문에 값이 변하면 새로운 객체를 내부적으로 생성하는 작업을 진행 함

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val n = Integer.parseInt(stdIn.next())
    val x = Integer.parseInt(stdIn.nextLine().trim())
    val a = stdIn.nextLine().split(" ")
    val result = StringBuilder("")

    for(idx in 0 until n) {
        if(x > Integer.parseInt(a[idx])) {
            result.append(a[idx] + " ")
        }
    }

    result.trim()

    print(result)
}
```