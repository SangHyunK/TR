# 백준 알고리즘 4344번 문제
* 제목 : 평균은 넘겠지
* URL : https://www.acmicpc.net/problem/4344  
* 사용언어 : Kotlin

## 문제  
대학생 새내기들의 90%는 자신이 반에서 평균은 넘는다고 생각한다. 당신은 그들에게 슬픈 진실을 알려줘야 한다.

## 입력
첫째 줄에는 테스트 케이스의 개수 C가 주어진다.

둘째 줄부터 각 테스트 케이스마다 학생의 수 N(1 ≤ N ≤ 1000, N은 정수)이 첫 수로 주어지고, 이어서 N명의 점수가 주어진다. 점수는 0보다 크거나 같고, 100보다 작거나 같은 정수이다.

## 출력
각 케이스마다 한 줄씩 평균을 넘는 학생들의 비율을 반올림하여 소수점 셋째 자리까지 출력한다.

## 풀이
Scanner로 데이터를 입력받았다. 

2번째 줄부터는 nextLine으로 데이터를 받아 공백을 기준으로 split를 하여 배열로 만들었다.

nextLine으로 받은 입력 중 0번째 배열은 학생 수 이고, 그 다음 n번째 배열은 학생 점수이다.

학생들 점수로 평균을 낸 뒤, 평균보다 높은 점수를 맞은 학생의 수를 카운트한다.

마지막으로 출력! (출력 시 String.format 사용함)

String.format("%.3f", 수) : 소수 점 3째 자리까지 표기하며 뒷 자리는 반올림 처리

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val cases = stdIn.nextLine().toInt()

    for(case: Int in 0 until cases) {
        val caseLine = stdIn.nextLine()

        val caseArray = caseLine.trim().split(" ")
        val students = caseArray[0].toInt()

        var sum = 0
        for(student: Int in 1 until caseArray.count()) {
            sum += caseArray[student].toInt()
        }

        val avg = sum.toDouble() / students

        var highScoreCnt = 0
        for(student: Int in 1 until caseArray.count()) {
            if(avg < caseArray[student].toInt()) {
                highScoreCnt++
            }
        }
        println(String.format("%.3f", highScoreCnt.toDouble() / students * 100) + "%")
    }
}
```