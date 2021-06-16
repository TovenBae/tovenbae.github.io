---
title: "Pytho 학습하기"
date: 2021-06-16 16:37:28 -0400
categories: Python
---

# Python 학습하기

#### 참고사이트
(문과생도 할수 있는 파이썬 독학 방법)[https://brunch.co.kr/@jfrences/69]
(생활코딩 : Python * Ruby)[https://opentutorials.org/course/1750]
(점프 투 파이선)[https://wikidocs.net/book/1]

## 생활코딩을 활용한 학습
동영상으로 구성되어 있어 플젝 상황에서는 학습이 어려움

## 점프 투 파이선을 활용한 학습
### 설치

### 파이썬 둘러보기
- 파이썬은 대소문자를 구별한다. print를 PRINT로 쓰면 정의되지 않았다는 오류 메시지가 나온다.
- print문 앞의 '...'은 아직 문장이 끝나지 않았음을 의미한다.

## 파이썬 프로그래밍의 기초, 자료형
### 숫자형
- 제곱 : **
- 나눗셈 몫 : //
- 나눗셈 나머지 : %

### 문자열
- 문자열에 작은 따옴표(') 포함시키기 : food = "Python's favorite is perl", 반대로도 무방함
- 백슬래시(\)를 사용해서 ', "를 포함시키기  => foot = "\"Python is very easy.\" he says"
- 줄바꾸기 : \n => multiline = "Life is too short \n You need python"
- 문자열 더하기 : +
- 문자열 길이 구하기 : len(a)
- 문자열 인덱싱 : a[3]
- 파이썬은 0부터 숫자를 센다
- 문자열 슬라이싱 : a[0:4]
- 문자열 포맷팅 :  "I eat %d apples. so I was sick for %s days " % (3, day) => I eat 3 apples. so I was sick for 10 days
- 문자열 포맷 코드 : 
    . %s : 문자열
    . %c : 1개 문자열
    . %d : 정수
    . %f : 부동소수
    . %o : 8진수
    . %x : 16진수
    . %% : Literal
- 정렬
    . 왼쪽정렬 : "{0:<10}"}.format("hi")
    . 오른쪽정렬 : "{0:>10}"}.format("hi")
    . 가운데정렬 : "{0:^10}"}.format("hi")
    . 공백채우기 : "{0:=^10}"}.format("hi")
- 소수점 표현하기
    ```
        >>> y = 3.142134
        >>> "{0:0.4f}".format(y)
        '3.1421'
        >>>
    ```
- 문자 개수 세기 : a.count('b')
- 위치 찾기 : find
- 위치 알려주기2 : index
- 문자열 삽입 : join => ",".join('abcd')
- 대소문자로 바꾸기 : upper, lower
- 공백 지우기 : rstrip, strip
- 문자열 바꾸기 : replace
- 문자열 나누기 : split


### 리스트
- 리스트명 = [요소1, 요소2, 요소3 ...]
- 리스트 연산
```
    >>> a = [1,2,3]
    >>> b = [4,5,6]
    >>> a+b
    [1, 2, 3, 4, 5, 6]
    >>>
```
- 리스트 길이 구하기 : len()
- 리스트 요소 삭제 : del a[1], remove()
- 리스트 요소 추가 : append()
- 리스트 정렬 : sort()
- 리스트 뒤집기 : reverse()
- 위치 반환 : index
- 요소 삽입 : insert
- 요소 꺼집어내기 : pop()
- 리스트 확장 : extend()



