# 1 Python : 들어가며

- Python 3.8 버전에 해당
- 파이썬에서 제공하는 스타일 가이드 [`PEP-8`](https://www.python.org/dev/peps/pep-0008/) 내용 반영

# 2 Syntax : 문법

## 1. Comment : 주석

- 한 줄 주석 `#`

- 여러 줄 주석 

  - 한 줄마다 #을 사용하여 표현

  - `"""` 이나 `'''`(여러 줄 문자열, multiline string)으로 표현 가능 

  ​        (주로 함수/클래스 설명(docstring)할 때 활용)

## 2. Code Line

- 파이썬 코드 : '1줄에 1문장'이 원칙
- 문장(statement) : 파이썬이 실행 가능(executable)한 최소한의 코드 단위
- 파이썬에서는 `;` 작성하지 않음
- 한 줄로 표기할 때 : `;` 작성하여 표기 가능



# 3 Variable : 변수

### 1. Assignment Operator : 할당 연산자 (=)

- 변수는 `=`을 통하여 할당
- 해당 데이터 타입 확인 :  **type()** 활용
- 해당 값의 메모리 주소 확인 : **id()** 활용



# 4 데이터 타입

- **숫자**(Number) 타입
- **문자**(String) 타입
- **참/거짓**(Boolean) 타입

## 1. Number : 숫자

### 1-1 ingteger

- 모든 정수 => **int**로 표현

- 보통 프로그래밍 언어 및 파이썬 2.x에서의 long은 OS 기준 32/64비트이나, python 3.x에서 long은 없어짐.

- 파이썬 3.x에서는 모두 int로 통합

- 2진수 : `0b` / 8진수 : `0o` / 16진수: `0x` 로도 표현 가능

  

**파이썬에서 표현 가능한 가장 큰 수**

- 파이썬에서 가장 큰 숫자 활용을 위해 sys 모듈을 불러옴
- 파이썬은 기존 C 계열 프로그래밍 언어와 다르게 정수 자료형(int)에서 오버플로우 없음

> **오버플로우(overflow)**

- 데이터 타입 별 사용 가능한 메모리의 크기 제한됨

- 표현할 수 있는 수의 범위 넘어가는 연산하면 기대했던 값이 출력되지 않는 현상

  = 메모리가 넘쳐 흐르는 현상

> **임의 정밀도 산술(arbitrary-precision arithmetic)**

- 사용 가능한 메모리 양이 정해진 기존 방식과 달리 현재 가용 메모리를 모두 수 표현에 끌어 쓸 수 있는 형태
- 특정 값을 나타낼 때 4바이트가 부족하다면 5바이트, 더 부족하면 그 이상 사용할 수 있게 유동적 운용

### 1-2  Float

- 부동소수점. 실수. floating point number

- 실수는 float로 표현

- 실수를 컴퓨터가 표현하는 과정에서 부동소수점을 사용, 항상 같은 값으로 일치되지 않음 

  = floating point rounding error

- 컴퓨터가 2진수(비트)를 통해 숫자 표현하는 과정에서 생기는 오류 

- 대부분의 경우 중요하지 않지만, 값이 같은지 비교하는 과정에서 문제 발생 가능

## 2. String : 문자

### 2-1 활용

- 문자열은 Single quotes(`'`) or Double quotes(`"`) 활용하여 표현 가능
  - 작은따옴표: '"큰" 따옴표를 담을 수 있다'
  - 큰따옴표: "'작은' 따옴표를 담을 수 있다"
  - 삼중 따옴표: '''세 개의 작은따옴표'''`, `"""세 개의 큰따옴표"""

- 단, 문자열 묶을 때 동일한 문장부호 활용해야 함 
- `PEP-8`에서는 하나의 문장부호 선택하여 유지하도록 함
- **Pick a rule and Stick to it**

### 2-2 Complex 

복소수 (complex number)

각각 실수로 표현되는 실수부와 허수부를 가짐. 복소수 허수부는 `j`로 표현

### 2-3 Escape Sequence

문자열 활용 시 특수문자 or 조작 위해 사용하는 것으로 `\` 활용하여 구분

<img src="INTRO.assets/5.png" style="zoom:50%;" />

### 2-4 String Interpolation

- **%-formatting**

  **%d** : 정수 /  **%f** : 실수 / **%s** : 문자열

- **str.format()**

- **f-strings** : 파이썬 3.6 이후 버전에서 지원

## 3. Boolean : 참/거짓

True와 False로 이뤄짐

비교/논리 연산 수행 등에 활용

다음은 False로 변환됨 => 0, 0.0, (), [], {}, '', None 

### 3-1 None 타입

''값이 없음''을 표현

## 4. Typecasting : 형변환

Type conversion (Typecasting)

파이썬에서 데이터타입은 서로 변환 가능

* 암시적 형변환 VS 명시적 형변환

### 4-1 암시적 형변환

사용자가 의도하지 않아도 파이썬 내부에서 자동으로 형변환 하는 경우로, 아래의 상황에서만 가능

- bool
- Numbers (int, float, complex)

### 4-2 명시적 형변환 

위 상황을 제외하고는 모두 명시적으로 형변환해야 함

- str => int : 형식에 맞는 숫자만 가능
- int => str : 모두 가능

암시적으로 형변환되는 모든 경우에도 명시적으로 형변환 가능

- **int()** : str, float => int로 변환

- **float()** : str, int => float로 변환

- **str()** : int, float, list, tuple, dictionary => 문자열로 변환

  

# 5 Operator : 연산자

- 산술 연산자
- 비교 연산자
- 논리 연산자
- 복합 연산자
- 기타 연산자

## 1. 산술 연산자

기본적인 사칙연산 가능

<img src="INTRO.assets/4.png" style="zoom:50%;" />

- 나눗셈 (`/`) 은 항상 float를 돌려줌
- 정수 나눗셈 으로 정수 결과를 얻으려면 `//` 연산자 사용

## 2. 비교 연산자

수학에서 배운 연산자와 동일하게 값 비교 가능

<img src="INTRO.assets/3.png" style="zoom:50%;" />

## 3. 논리 연산자

<img src="INTRO.assets/2.png" style="zoom:50%;" />

- `&` `|`은 파이썬에서 비트 연산자
- 파이썬에서 and는 a가 거짓이면 a를, 참이면 b를 리턴
- 파이썬에서 or은 a가 참이면 a를, 거짓이면 b를 리턴

### 3-1 단축평가

- 첫 번째 값이 확실할 때, 두 번째 값은 확인 X
- 조건문에서 뒷부분 판단하지 않아도 됨 => 속도 향상

- **and **는 둘 다 True일 경우만 True => 첫번째 값이 True라도 두번째 값을 확인해야 함 => 'b' 반환
- **or** 는 하나만 True라도 True => True 만나면 해당 값 바로 반환

## 4. 복합 연산자

복합 연산자는 연산과 대입이 함께 이뤄짐

반복문을 통해서 개수 카운트 등을 할 때 가장 많이 활용

<img src="INTRO.assets/1-1610983851940.png" style="zoom:50%;" />

## 5. 기타

### 5-1 Concatenation

숫자가 아닌 자료형은 `+` 연산자를 통해 합칠 수 있음

### 5-2 Containment Test

**in** 연산자로 특정 요소가 속해있는지 여부 확인 가능

### 5-3 Identity

**is**연산자로 동일한 object인지 확인 가능 (**OOP 파트에서 다시!)

### 5-4 Indexing/Slicing

**[]**로 값에 접근, **[:]**로 리스트 슬라이싱 (**Container 파트에서 다시!)

## 6. 우선순위 - 연산자

**`()`을 통한 grouping** !! (최우선)

=> Slicing

=> Indexing

=> 제곱연산자 `**`

=> 단항연산자 `+`, `-` (음수/양수 부호)

=> 산술연산자 `*`, `/`, `%`

=>산술연산자 `+`, `-`

=> 비교연산자, `in`, `is`

=> `not`

=>`and`

=>`or`

### 6-1 Expression : 표현식 & Statement : 문장

### - 표현식

표현식 => **evaluate** => 값

- 하나의 값(value)으로 환원(reduce) 가능한 문장
- 식별자, 값(literal), 연산자 로 구성
- 표현식 만드는 문법은 일반적 중위표기 수식의 규칙과 유사

### - 문장

파이썬이 실행 가능한 최소한의 코드 단위 

**a syntatic unit of programming**

### 6-2 문장/표현식의 관계

- 문장 안에 표현식이 있음 (문장 > 표현식)



# 6 정리

## 1. 변수와 데이터 타입

> **radius** (변수명, 식별자) = **10** (데이터)

> area  = radius *(연산자, operator) radius ** 2

> is_number = type**(area)** : 데이터 타입(str)

> result = 'Area: ' + **str(area)**  : 형변환(typecasting)

> is_smaller = **area < 100** : 표현식(expression)

> **greeting = 'Bye' + '!' * 3***  : 문장(statement)



# Container : 컨테이너

- 여러 개의 값을 저장할 수 있는 것

- 시퀀스(Sequence)형 : 순서 있는 데이터
- 비 시퀀스(Non-sequence)형: 순서 없는 데이터



# 1 시퀀스형

- 시퀀스는 데이터가 순서대로 나열된 형식

- 순서대로 나열 = ''정렬되었다(sorted)' 의 의미는 아님

## 1. 특징

- 순서를 가짐

- **특정 위치의 데이터 가리킬 수 있음**

## 2. 종류

파이썬의 기본적 시퀀스 타입

- 리스트(list)
- 튜플(tuple)
- 레인지(range)
- *문자형(string)*
- *바이너리(binary)* 

## 3. list

**[value1, value2, value3]**

대괄호 [] 와 list()로 만들 수 있으며 값에 대한 접근은 list[i]로 함

## 4. tuple

**(value1, value2)**

리스트와 유사하나, ()로 묶어 표현

**수정 불가능**(immutable) & only readable

파이썬 내부에서 다양한 용도로 활용 > 직접 사용

## 5. range()

숫자의 시퀀스 나타내기 위해 사용

기본형 : range(n)

=> 0부터 n-1까지 값 가짐

범위 지정 : range(n, m)

=> n부터 m-1까지 값 가짐

범위 및 스텝 지정 : range(n, m, s)

=> n부터 m-1까지 +s만큼 증가

## 6. 시퀀스에서의 연산자&함수

x **in** s  : containment test

x **not in** s  : containment test

s1 **+** s2  : concatenation

s `*` n  : n번만큼 반복해 더하기

**s[i]** : indexing

**s[i:j]** : slicing

**s[i:j:k]**  : k간격으로 slicing

**len(s)**  : 길이

**min(s)**  : 최솟값

**max(s)**  : 최댓값

**s.count(x)** :  x의 개수

# 2 비 시퀀스형

## 1. set

순서 없는 자료구조

- 수학에서의 집합과 동일하게 처리
- 중괄호{}로 만듦
- 순서 x 중복된 값 x
- 빈 집합 만들려면 => set() 사용해야 함 ({}로 사용 불가)

**{value1, value2, value3}**

- set을 사용하면 list의 중복된 값 쉽게 제거 가능

## 2. dictionary

key와 value가 쌍으로 이루어진 **궁극의 자료구조**

**{Key1:Value1, Key2:Value2, Key3:Value3, ...}**

- {}로 만들거나 dict()로 만들 수 있음

- key는 변경 불가능(immutable)한 데이터만 가능

  (변경 불가능 : str, int, float, bool, tuple, range)

- value는 list, dictionary를 포함, 모든 것 가능

## 3. 컨테이너형 형변환

파이썬에서 컨테이너는 서로 변환 가능

<img src="INTRO_CONTAINER.assets/6.png" style="zoom:50%;" />

## 4. 변경 가능 VS 변경 불가능 데이터

**mutable**  VS **immutable**

데이터는 크게 변경 가능한 것/불가능한 것으로 분류, 파이썬은 각각을 다르게 다룸

### 4-1 변경 불가능한 데이터

- literal

  숫자(Number) / 글자(String) / 참/거짓(Bool)

- range()

- tuple()

- frozenset()

### 4-2 변경 가능한 데이터

- list
- dict
- set



### 오늘은 Jupyter notebook을 사용해 보았다.

> 해당 내용은 차후 정리해 보아야!
