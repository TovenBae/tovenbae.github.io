---
title: "Python 학습하기"
date: 2021-06-16 16:37:28 -0400
categories: Python
---

# Python 학습하기

#### 참고사이트
- (문과생도 할수 있는 파이썬 독학 방법)[https://brunch.co.kr/@jfrences/69]
- (생활코딩 : Python * Ruby)[https://opentutorials.org/course/1750]
- (점프 투 파이선)[https://wikidocs.net/book/1]

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

### 튜플 자료형
- 튜플(Tuple)은 리스트와 거의 비슷하며 다른 점은 다음과 같음
    . 리스트는 []로 둘러싸지만 튜플은 ()로 둘러쌈
    . 리스트는 그 값의 생성, 삭제, 수정은  가능하지만 튜플은 불가함.
```
    t1 = ()
    t2 = (1,)
    t5 - ('a', ''b', ('ab', 'cd'))
```

### 딕셔너리 자료형
- Key, Value 구조형 
```
{Key1:Value1, key2:Value2, Key3:Value3, ...}
```

### 집합 자료형
- 집합(set)은 파이썬 2.3부터 지원
- 특징
    . 중복을 허용하지 않음.
    . 순서가 없다.
- 교집합, 합집합, 차집합 구할때 유용함.
- 값 추가 : add
- 값 여러개 추가 : update
- 특정 값 제거 : remove
### 불 자료형
- 참/거짓 자료형
     

### 변수
- 메모리 주소 확인 : id(변수)
- 리스트 복사 : 
    . [:] 사용
    . copy 모듈 사용 : 
    ```
        from copy import copy
        copy(a)
    ```
### 반복
```
for i in range(1, 11):
    statement
```    
- 1 -> 10까지 looping

## 프로그램 입출력
### 파일을 쓰기 모드로 열어 출력값 기록
```
# writedata.py
f = open("c:/data/test.txt", 'w')
for i in range(1, 11) :
    data = "%d 줄입니다. \n" % i
    f.write(data)
f.close()

f = open("c:/data/test.txt", 'r')
line = f.readlin()
print(line)
f = open()
```

## 파이썬 날개달기
### 클래스
 ```
class Calculator:
    def __init__(self) :
        self.result = 0

    def add(self, num) :
        self.result += num
        return self.result

cal1 = Calculator()
cal2 = Calculator()

print(cal1.add(3))
print(cal1.add(4))
print(cal2.add(2))
print(cal2.add(7))
 ```

 
> 객체와 인스턴스의 차이
>
> 클래스로 만든 객체를 인스턴스라고도 한다. 그렇다면 객체와 인스턴스의 차이는 무엇일까? 이렇게 생각해 보자. a = Cookie() 이렇게 만든 a는 객체이다. 그리고 a 객체는 Cookie의 인스턴스이다.
> 즉 인스턴스라는 말은 특정 객체(a)가 어떤 클래스(Cookie)의 객체인지를 관계 위주로 설명할때 사용한다. "a는 인스턴스"보다는 "a는 객체"라는 표현이 어울리며 "a는 Cookie의 객체"보다는 "a는 Cookie의 인스턴스"라는 표현이 훨씬 잘 어울린다.

#### 생성자(Constructor)
- __init()

#### 클래스의 상속
- class 클래스 이름(상속할 클래스 이름)

#### 메소드 오버라이딩
- 클래스 변수는 클래스이름.클래서변수로 사용 : print(Family.lastname)
- 클래스 변수는 클래스로 만든 모든 객체에 공유된다.

### 모듈
- 모듈이란 함수나 변수 또는 클래스를 모아 놓은 파일
- 모듈 불러오기 : from 모듈이름 import 모듈함수
- if __name__ == "__main__"
> __name__ 변수란
>
> 파이썬의 __name__ 변수는 파있너이 내부적으로 사용하는 특별한 변수 이름이다. 만약 c:\doti>python mod1.py 처럼 직접 mod1.py 파일을 실행할 경우 
> mod1.py의 __name 변수에는 __main__ 값이 저장된다. 하지만 파이썬 셸이나 다른 파이썬 모듈에서 mod1을 import 할 경우에는 mod1.py의 __name__ 변수에는 mod1.py의 모듈 이름 값 mod1이 저장된다.

### 패키지

### 라이버러리
- sys
- pickle
- os
- shutil
- glob
- tempfile
- time
- calendar
- random
- webbrowser
