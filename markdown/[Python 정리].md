R[Python 정리]
=============

# 1. Python

1.1. Python이란
---------------
1991년 네덜란드의 귀도 반 로섬(Guido van Rossum)이 개발해 공개한 것이 시초가 됐습니다. 2000년에 버전 2가 공개된 후에 주목받게 돼 하나으 프로그래밍 언어로서 인식되기 시작했습니다. 윈도우, 맥 OS X, 리눅스 등 다양한 OS에서 동작하며 많은 곳에서 사용되고 있습니다.

1. 훌륭한 가독성
2. 풍부한 라이브러리 > 무수히 많은 라이브러리가 인터넷상에 공개돼 있다. > 웹 프로그래밍, 배치파일, 응용프로그램, 계산, 기계학습 등 다양한 곳에 활용
3. 객체지향 언어 > 소프트웨어를 설계하고 개발할 때 조작 순서보다는 조작 대상에 중점을 두어 만드는 방법

---

# 2. 문법

### 2.1. 변수, 문자열

1. 변수

 - '변수'란 데이터를 일시적으로 기억해두는 메모리 안의 영역을 말한다.

    ```
    [변수] = [데이터]
    ```

   - 데이터 값이 변경될 수 있으면 **변수**
   -	데이터 값이 변경될 수 없ㅇ면 **상수**
<br/>

2. 문자열

 - '여러 개의 문자가 이어져서 열을 이룬 것'`
    ```
    hello1 = "Hello, Python"
    hello2 = 'Hello, Python'
    ```

- format() : 문자열을 동적으로 만드는 방법
    ```
    "{키1} {키2} ...".format(키0 = 값0, 키1 = 값1, ...)
    ```
<br/>

### 2.2. 제어구문


 **제어구문** 이란 **어떤 조건**에 의해 프로그램의 흐름을 바꾸는 기능

1.	조건문

  -	if와 else는 조건이 참인지 거짓인지 확인하는 Python의 선언문
    ```
	if (조건):
	    (실행내용)
	elif (다른조건):
	    (실행내용)
	else:
	    (실행내용)
    ```

	  * 예시
	    ```
	    num = 58
	    if num % 2 ==0:
	        print("짝수입니다.")
	    else:
	        print("홀수입니다.")
	    ```
<br/>

2. 반복문
    * while
	  -	조건식이 참(True)인 한 블럭 내 구문을 계속 반복.
	    ```
	    while (조건):
	        (실행내용)
	    ```

    * for
      - iterable한 객체: 객체의 첫 번째 요소부터 마지막 요소까지 순환 가능한 객체
      - sequence 또는 iterator나 generator
        ```
        for (루프변수) in (반복가능한 객체) :
            (실행내용)
        ```
<br/>

3. 컴프리헨션
  * 하나 이상의 iterator로부터 파이썬의 자료구조를 만드는 콤팩트한 방법
  * 비교적 간편한 구문으로 조건문과 반복문을 결합할 수 있도록 해줌
  * 파니써닉한 방법
    * 리스트 컴프리헨션
      ```
      [표현식 for 항목 in 순회 가능한 객체]
      ```
      * 예시
        ```
        list1 = []
        for i in range(10):
            if i % 2 == 0
            list1.append(i)
        -----------------------
        list2 = [x for x in range(10) if i % 2 == 0]
        ```
<br/>

### 2.3. 리스트 & 튜플
1. 리스트
    * 순서를 갖는 다양한 객체들의 시퀀스
    * 변경 가능한 객체
    * [] or liste()로 생성
      ```
      a = [1, [2, 3], {4:0}, 5.0, '6', ('7')]
      ```
    * 매서드
      * len() : 리스트 요소의 개수를 조사
        ```
        a = [1, 2, 3, 4, 5, 6]
        len(a)
        ----------------------
        6
        ```
      * append(x) : x를 리스트의 마지막에 추가
      * insert(i, x) : 인덱스 i번에 x를 추가
      * sort() : 오름차순으로 정렬
<br/>

2. 튜플
    * 상수 리스트
    * 변경이 불가능한 객체
    * () or tuple()로 생성
    * 리스트보다 더 적은 메모리를 사용
<br/>

3. Packing & Unpacking
  * 패킹(Packing)
    * 여러 항목을 리스트나 튜플에 넣는 것
  * 언패킹(Unpacking)
    * 리스트나 튜플에 있는 항목을 변수들로 풀어헤쳐 담는 것
      ```
      info = 'James', 'male', 27
      name, gender, age = info
      name, gender, age = 'James', 'male', 27
      ```
<br/>

### 2.4. 딕셔너리(Dictionary)
* 키(key)와 값(value) 형태로 짝지어 담은 사전(Dictionary) 자료형
* 순서를 보장하지 않음
* 변경 가능한 객체
* {} 또는 dict()로 생성
```
변수 = {'key1' : 값1, 'key2' : 값2, 'key3' : 값3, ...}
```
* 딕셔너리형 key, value 열거하는 법

  방법  |  설명
  ------|-------
  dict.key()  |  키 목록을 얻는다
  dict.value()  |  값 목록을 얻는다
  list(dict.key())  |  키 목록을 리스트형으로 얻는다
  list(dict.value())  |  값 목록을 리스트형으로 얻는다
---------------------------------------------------------

# 3. 함수
### 3.1. 함수
  * 반복되는 부분이 있을 경우, 한 뭉치(**여러 구문을 묶은 단위**)로 묶어서 입력값(**인자**)을 주었을 때 결과값(**반환**)을 돌려줌
  * 프로그램의 흐름을 **일목요연**하게 볼 수 있음
  * **재사용**이 가능
  * 작업
    * 정의(define)
    * 호출(call)

<br/>

  * 표현식
    ```
    def [함수 이름] ( [매개변수], ... , [*위치 인자], [**키워드 인자] ) :
        [실행 내용]
        return [반환]
    ```
    * 예시
      ```
      def mask_security_number(security_number):
          hide = "****"
          if len(security_number) == 14:
              number = security_number[:10] + hide
          else:
              number = security_number[:9] + hide

          return number

      print(mask_security_number("880720-1234567"))
      ----------------------------------------------
      880720-123****
      ```
<br/>

  * 구성요소
    * 순서 : 1)인자, 2)위치인자, 3) 키워드인
    * **위치인자(Positional arguments)**
      * 함수의 매개변수를 튜플로 묶기위해 * 를 사용
      * 인자 이름을 지정하지 않고 차례대로 나열
      ```
      def print_args(***args**):
          print('Positional argument:', args)
      print_args(1, 2, 'as', {'a,':1, 'b':2},[1, 2])
      ```
    * **키워드인자(Keyword arguments)**
      * 함수의 매개변수를 딕셔너리로 묶기위해 두 개의 * 를 사용
      * 인자 이름을 지정하고 차례대로 나열
      ```
      def print_kargs(****kwargs**):
          print('Keyword arguments:', kwargs)
      print_kargs(animal='cat', fruit='apple')
      ```
----------------------------------------------------------------

# 4. 예외처리
* 관련 에러가 발생할 때 실행되는 코드인 **예외**를 사용
* 모든 잠재적인 에러를 발지하기 위해 적절한 **예외처리**가 필요
  ```
  try:
      [에러가 날 수 있는 코드]
  except:
      [에러 처리 코드]
  else:
      [try 성공시 진행]
  finally:
      [무조건 실행되는 구문]
  ```
-----------------------------------
# 5. 객체
### 5.1. 객체
  * 데이터와 데ㅣ터에 관련되는 동작(정차, 방법, 기능)을 모두 포함할 수 있는 개념적 존재
  * 클래스를 실체화 한 것이며, instance 라고 함
  * 데이터(변수, attribute)와 코드(함수, method)를 모두 포함
<br/>
### 5.2. 클래스
  * 파이썬은 모든 자료형이 객체
  * 객체는 자료형(type)으로부터 만듬
  * 클래스는 새로운 객체 자료형을 정의하는 자료형

#### 5.2.1. 클래스 생성
  ```
  class 클래스이름:
      def 매서드1(self):
          코드
  ```
  ```
  class Person:
      def greeting(self):
          print('Hello')

      def hello(self):
          self.greeting()    # self.메서드() 형식으로 클래스 안의 메서드를 호출

  james = Person()
  james.hello()
  -------------------
  Hello
  ```
#### 5.2.2. 속성


--------------------------------------------------
# 6. Decorator
