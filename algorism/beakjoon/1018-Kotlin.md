# 백준 알고리즘 1018번 문제
* 제목 : 체스판 다시 칠하기
* URL : https://www.acmicpc.net/problem/1018  
* 사용언어 : Kotlin

## 문제  
지민이는 자신의 저택에서 MN개의 단위 정사각형으로 나누어져 있는 M * N 크기의 보드를 찾았다. 어떤 정사각형은 검은색으로 칠해져 있고, 나머지는 흰색으로 칠해져 있다. 지민이는 이 보드를 잘라서 8 * 8 크기의 체스판으로 만들려고 한다.

체스판은 검은색과 흰색이 번갈아서 칠해져 있어야 한다. 구체적으로, 각 칸이 검은색과 흰색 중 하나로 색칠되어 있고, 변을 공유하는 두 개의 사각형은 다른 색으로 칠해져 있어야 한다. 따라서 이 정의를 따르면 체스판을 색칠하는 경우는 두 가지뿐이다. 하나는 맨 왼쪽 위 칸이 흰색인 경우, 하나는 검은색인 경우이다.

보드가 체스판처럼 칠해져 있다는 보장이 없어서, 지민이는 8 * 8 크기의 체스판으로 잘라낸 후에 몇 개의 정사각형을 다시 칠해야겠다고 생각했다. 당연히 8 * 8 크기는 아무데서나 골라도 된다. 지민이가 다시 칠해야 하는 정사각형의 최소 개수를 구하는 프로그램을 작성하시오.

## 입력
첫째 줄에 N과 M이 주어진다. N과 M은 8보다 크거나 같고, 50보다 작거나 같은 자연수이다. 둘째 줄부터 N개의 줄에는 보드의 각 행의 상태가 주어진다. B는 검은색이며, W는 흰색이다.

## 출력
첫째 줄에 지민이가 다시 칠해야 하는 정사각형 개수의 최솟값을 출력한다.

## 풀이
브루트 포스(완전탐색) 알고리즘으로 푸는 문제이다. 모든 경우의 수를 하나하나씩 대입하므로 자원만 충분하다면 정확도는 100%!

2개의 함수를 만들었다
- inputBoard : 입력받은 라인 수 만큼 보드 데이터를 입력받는 함수
- minFillBoard : 보드, 시작라인, 시작칸을 입력받고 8 * 8 보드로 만든 뒤 최소로 칠하는 횟수를 구한다.

result는 최종적으로 출력하는 변수인데, 초기값이 64인 이유는 8 * 8 보드판에서 나올 수 있는 최악의 값이 64이기 때문이다. 최솟값을 구하는 문제이므로 64로 지정 후 아래 반복문의 결과에 따라 값을 바뀌게 해주었다

[main 함수의 while문]  
8 * 8 보드판을 만들 기준점을 구하는 while문이다 (바깥쪽 라인, 안쪽 칸)

예를 들어, line이 13, space가 10이 들어왔을 경우 보드 8 * 8이 구성될 수 있는 부분은 아래와 같다.
- 라인 : 0 ~ 8, 1 ~ 9, 2 ~ 10, 3 ~ 11, 4 ~ 12
- 칸 : 0 ~ 8, 1 ~ 9

[minFillBoard 함수]  
파라미터로 board, 시작라인, 시작칸을 입력 받는다.  
체스판은 WBWBWB 처럼 규칙성있게 색이 칠해져있다. 이 패턴을 아래 공식으로 나타낸다. 
* (line + space) % 2 == 0  

해당 공식을 이용하여 (line + space) 짝수칸이 블랙일 경우, 짝수칸이 화이트일 경우에 대한 경우의 수를 모두 구한다.

그 후 짝수칸이 블랙 일 때 칠한 횟수와 화이트 일 때 칠한 횟수를 비교하여 작은수를 리턴해준다.  

만들어질 수 있는 모든 8 * 8 보드의 최솟값을 계속 비교하여 최종적으로 나온 최솟값을 출력해주면 끝!

## 후기
내가 아직 완전탐색 문제에 대해서 많이 약하다고 느끼게 된 문제였다. (이 문제를 풀려고 2일을 고생했다 -_-)  
규칙을 찾고 풀어야 하는데 무턱대고 코딩하니 정말 삽질을 많이 했다...  
다음 문제부터는 규칙을 찾아보고 푸는 연습을 많이 해야지..

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val line = stdIn.nextInt()
    val space = stdIn.nextInt()
    val board = inputBoard(stdIn, line)
    var result = 64
    
    var lineFirst = 0
    while(lineFirst < line) {
        if(lineFirst + 8 > line) break

        var spaceFirst = 0
        while(spaceFirst < space) {
            if(spaceFirst + 8 > space) break

            val checkBoard = minFillBoard(board, lineFirst, spaceFirst)
            result = if(result > checkBoard) checkBoard else result

            spaceFirst++
        }

        lineFirst++
    }

    println(result)
}

fun inputBoard(stdIn: Scanner, line: Int): String {
    var first = 0
    var board = StringBuilder("")
    while(first < line) {
        board.append(stdIn.next())
        board.append("\n")
        first++
    }

    return board.trim().toString()
}

fun minFillBoard(board:String, line: Int, space: Int): Int {
    val board = board.split("\n")

    var black = 0
    var white = 0

    var lineFirst = line
    while(lineFirst < line + 8) {

        var spaceFirst = space
        while(spaceFirst < space + 8) {

            if(board[lineFirst][spaceFirst] == 'B') {
                if((lineFirst + spaceFirst) % 2 == 0) white++ else black++
            } else {
                if((lineFirst + spaceFirst) % 2 == 0) black++ else white++
            }
            spaceFirst++
        }
        lineFirst++
    }

    return if(black > white) white else black
}
```