# 백준 알고리즘 1605번 문제
* 제목 : 한수
* URL : https://www.acmicpc.net/problem/1605  
* 사용언어 : Kotlin

## 문제  
어떤 양의 정수 X의 자리수가 등차수열을 이룬다면, 그 수를 한수라고 한다. 등차수열은 연속된 두 개의 수의 차이가 일정한 수열을 말한다. N이 주어졌을 때, 1보다 크거나 같고, N보다 작거나 같은 한수의 개수를 출력하는 프로그램을 작성하시오. 

## 입력
첫째 줄에 1,000보다 작거나 같은 자연수 N이 주어진다.

## 출력
첫째 줄에 1보다 크거나 같고, N보다 작거나 같은 한수의 개수를 출력한다.

## 풀이
1) 100보다 작은 수의 경우 모두 등차수열이므로 입력 값 그 자체를 출력한다. (기저사례)
2) 100보다 큰 수의 경우 이어서 진행
3) 입력받은 수 까지 반복문을 실행한다
4) 1000은 한수가 아니므로 조건에서 제외
5) 100 ~ 999 사이의 수에서 한수를 구하고, 한수의 개수를 결과값에 더한다
6) 마지막에 99를 더한 뒤 종료

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val number = stdIn.nextInt()

    if(number <= 99) {
        print(number)
        return
    }

    val startNumber = 100
    var result = 0
    for(n in startNumber .. number) {
        val numberStr = n.toString()

        if(n != 1000) {
            if(numberStr[0].toString().toInt() - numberStr[1].toString().toInt()
                == numberStr[1].toString().toInt() - numberStr[2].toString().toInt()) {
                result++
            }
        }
    }

    result += 99

    println(result)
}
```