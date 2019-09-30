# 백준 알고리즘 1546번 문제
* 제목 : 평균
* URL : https://www.acmicpc.net/problem/1546  
* 사용언어 : Kotlin

## 문제  
세준이는 기말고사를 망쳤다. 세준이는 점수를 조작해서 집에 가져가기로 했다. 일단 세준이는 자기 점수 중에 최댓값을 골랐다. 이 값을 M이라고 한다. 그리고 나서 모든 점수를 점수/M*100으로 고쳤다.

예를 들어, 세준이의 최고점이 70이고, 수학점수가 50이었으면 수학점수는 50/70*100이 되어 71.43점이 된다.

세준이의 성적을 위의 방법대로 새로 계산했을 때, 새로운 평균을 구하는 프로그램을 작성하시오.

## 입력
첫째 줄에 시험 본 과목의 개수 N이 주어진다. 이 값은 1000보다 작거나 같다. 둘째 줄에 세준이의 현재 성적이 주어진다. 이 값은 100보다 작거나 같은 음이 아닌 정수이고, 적어도 하나의 값은 0보다 크다.

## 출력
첫째 줄에 새로운 평균을 출력한다. 정답과의 절대/상대 오차는 10-2까지 허용한다.

## 풀이
Scanner 객체를 사용 해 첫 줄에는 과목의 수를 받았고, 두 번째줄에는 반복문을 활용, 과목 수 만큼 스페이스를 기준으로 StringBuilder 객체에 데이터를 받았습니다. 

StringBuilder 객체를 공백을 기준으로 배열로 나누었고, 그 다음으로 최고 값을 구했습니다. (최고값을 기준으로 모두 나눠야 하기 때문에)

마지막으로 구해진 최고 값으로 모든 점수를 [주어진값]/[최고값] * 100 형태로 만든 뒤 평균을 구했습니다.


## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val subjectCnt = stdIn.nextLine().toInt()

    var scores = StringBuilder("")
    for(subject: Int in 0 until subjectCnt) {
        scores.append(stdIn.nextInt())
        scores.append(" ")
    }

    val scoresArray = scores.trim().split(" ")
    var scoreMax = scoresArray[0].toInt()

    for(score: Int in 1 until scoresArray.count()) {
        if(scoreMax < scoresArray[score].toInt()) {
            scoreMax = scoresArray[score].toInt()
        }
    }

    var result = 0.0
    for(score: Int in 0 until scoresArray.count()) {
        result += (scoresArray[score]).toDouble() / scoreMax * 100
    }

    println(result / subjectCnt)
}
```