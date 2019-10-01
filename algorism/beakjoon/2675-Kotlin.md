# 백준 알고리즘 2675번 문제
* 제목 : 문자열 반복
* URL : https://www.acmicpc.net/problem/2675  
* 사용언어 : Kotlin

## 문제  
문자열 S를 입력받은 후에, 각 문자를 R번 반복해 새 문자열 P를 만든 후 출력하는 프로그램을 작성하시오. 즉, 첫 번째 문자를 R번 반복하고, 두 번째 문자를 R번 반복하는 식으로 P를 만들면 된다. S에는 QR Code "alphanumeric" 문자만 들어있다.

QR Code "alphanumeric" 문자는 0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ\$%*+-./: 이다.

## 입력
첫째 줄에 테스트 케이스의 개수 T(1 ≤ T ≤ 1,000)가 주어진다. 각 테스트 케이스는 반복 횟수 R(1 ≤ R ≤ 8), 문자열 S가 공백으로 구분되어 주어진다. S의 길이는 적어도 1이며, 20글자를 넘지 않는다. 

## 출력
각 테스트 케이스에 대해 P를 출력한다.

## 풀이
case 만큼 반복문을 돌게했고 그 안에서 입력받은 문자열을 문자단위로 쪼개어 반복횟수만큼 출력시켰다.

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val cases = stdIn.nextLine().toInt()

    for(case in 0 until cases) {
        val iteratorCount = stdIn.nextInt()
        val text = stdIn.next()
        val result = StringBuilder("")

        for(t in text) {
            for(count: Int in 0 until iteratorCount) {
                result.append(t)
            }
        }

        println(result)
    }
}
```