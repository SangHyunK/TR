# 백준 알고리즘 2739번 문제
* 제목 : 구구단
* URL : https://www.acmicpc.net/problem/2739  
* 사용언어 : Kotlin

## 문제  
N을 입력받은 뒤, 구구단 N단을 출력하는 프로그램을 작성하시오. 출력 형식에 맞춰서 출력하면 된다.

## 입력
첫째 줄에 N이 주어진다. N은 1보다 크거나 같고, 9보다 작거나 같다.

## 출력
출력형식과 같게 N * 1부터 N * 9까지 출력한다.
```
2 * 1 = 2
2 * 2 = 4
2 * 3 = 6
...
2 * 9 = 18
```

## 풀이
Kotlin은 C에서 사용하는 일반적인 for문은 존재하지 않는다.
for-each문과 비슷한 형태이다
```
for(변수명: 타입 in 범위)
```

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val number = stdIn.nextInt()
    
    for(dan: Int in 1..9) {
        println("$number * $dan = ${number * dan}")
    }
}
```