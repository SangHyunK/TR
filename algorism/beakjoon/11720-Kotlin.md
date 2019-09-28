# 백준 알고리즘 11720번 문제
* 제목 : A + B - 5
* URL : https://www.acmicpc.net/problem/11720  
* 사용언어 : Kotlin

## 문제  
N개의 숫자가 공백 없이 쓰여있다. 이 숫자를 모두 합해서 출력하는 프로그램을 작성하시오.

## 입력
첫째 줄에 숫자의 개수 N (1 ≤ N ≤ 100)이 주어진다. 둘째 줄에 숫자 N개가 공백없이 주어진다.

## 출력
입력으로 주어진 숫자 N개의 합을 출력한다.

## 풀이
둘째 줄을 모두 String 타입으로 받는다. String은 배열형태로 꺼내는 것이 가능하기 때문에 한 개씩 꺼내면서 꺼낸 데이터를 Int로 변환 및 res 변수에 값을 더하는 작업을 반복했다.

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val count = stdIn.nextInt()
    var res = 0;

    val number = stdIn.next()

    for(index: Int in 0 until count) {
        res += Integer.parseInt(number[index].toString())
    }

    print(res)
}
```