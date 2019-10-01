# 백준 알고리즘 2941번 문제
* 제목 : 크로아티아 알파벳
* URL : https://www.acmicpc.net/problem/2941  
* 사용언어 : Kotlin

## 문제  
예전에는 운영체제에서 크로아티아 알파벳을 입력할 수가 없었다. 따라서, 다음과 같이 크로아티아 알파벳을 변경해서 입력했다.

|크로아티아 알파벳 | 변경 |
|:---|:----|
|č    | c=  |
|ć    | c-  |
|dž   | dz= |
|đ    | d-  |
|lj   | lj  |
|nj   | nj  |
|š    | s=  |
|ž    | z=  |

예를 들어, ljes=njak은 크로아티아 알파벳 6개(lj, e, š, nj, a, k)로 이루어져 있다. 단어가 주어졌을 때, 몇 개의 크로아티아 알파벳으로 이루어져 있는지 출력한다.

dž는 무조건 하나의 알파벳으로 쓰이고, d와 ž가 분리된 것으로 보지 않는다. lj와 nj도 마찬가지이다. 위 목록에 없는 알파벳은 한 글자씩 센다.

## 입력
첫째 줄에 최대 100글자의 단어가 주어진다. 알파벳 소문자와 '-', '='로만 이루어져 있다.

단어는 크로아티아 알파벳으로 이루어져 있다. 문제 설명의 표에 나와있는 알파벳은 변경된 형태로 입력된다.

## 출력
입력으로 주어진 단어가 몇 개의 크로아티아 알파벳으로 이루어져 있는지 출력한다.

## 풀이
1) 크로아티아 언어를 표현하는 단어를 배열에 저장
2) 입력받은 문자열에서 크로아티아 문자가 있는지 확인한다 (indexOf 사용)
3) 존재한다면 입력받은 문자에서 공백으로 변환 (replaceFirst 사용)
4) 결과값에 1을 더하고 크로아티아 배열의 위치를 0으로 재조정
5) 크로아티아 배열 맨 마지막까지 찾지 못한 경우 반복문 종료
6) 공백울 빈문자열로 변환 (replace)
7) 반복문에서 걸러지지 않은 문자를 결과값에 더함
8) 완료

※ replaceFirst : 찾은 문자열 중 가장 처음 문자열만 변경한다.

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    val inputStr = stdIn.nextLine()
    val croatiaArray: Array<String> = arrayOf("c=", "c-", "dz=", "d-", "lj", "nj", "s=", "z=")

    var variableStr = inputStr
    var result = 0
    var croatiaIdx = 0
    while(true) {
        if(croatiaArray.count() == croatiaIdx) break
        if(variableStr.isEmpty()) break

        if(variableStr.indexOf(croatiaArray[croatiaIdx]) > -1) {
            variableStr = variableStr.replaceFirst(croatiaArray[croatiaIdx], " ")
            croatiaIdx = 0
            result++
        } else {
            croatiaIdx++
        }
    }

    variableStr = variableStr.replace(" ", "")
    result += variableStr.length

    println(result)
}
```