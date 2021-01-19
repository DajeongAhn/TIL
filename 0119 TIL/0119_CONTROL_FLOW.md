

# Control Statement : 제어문

- 위에서 아래로 순차적으로 명령을 수행하는 프로그램 작성이 아닌 특정 상황에 따라 코드를 선택적으로 실행(분기)하거나 동일한 코드를 계속해서 실행해야하려면...

  => 코드 실행의 순차적인 흐름을 제어**(Control Flow)**할 필요

- 순차적인 코드의 흐름을 제어하는 것 => 제어문

- 크게 **조건문**과 **반복문**으로 나뉨

- 제어문을 통해 순서도(Flow Chart)를 코드로 표현 가능

```
a = 5
if a > 5:
	print('5 초과')
else:
	print('5 이하')
print(a)
```



# Conditional Statement : 조건문

## 1. if 조건문

if 문 => 반드시 **참/거짓을 판단**할 수 있는 조건과 함께 사용!

### 1-1 활용

- **문법**

```python
if <expression>:
    <코드 블럭>
else:
    <코드 블럭>
```

- <expression>은 보통 참/거짓에 대한 조건식
- 조건이 참인 경우 => `:` 이후 문장 수행
- 조건이 거짓인 경우 => `else:` 이후 문장 수행
- 여러 개의 `elif` 부 있을 수 있고, `else`는 선택적
- **예시**

```python
if a > 0:
    print('양수이다.')
else:
    print('음수이다.')
```

### 1-2 주의사항

- 들여쓰기에 유의해야!

  => 파이썬에서는 코드 블록을 자바나 C언어의 { }와 달리 **들여쓰기**로 판단하기 때문

- [PEP 8]에서 권장하는 **4spaces** 사용

### 1-3 크리스마스 판독기
조건문을 통해 사용자가 입력한 날짜가 크리스마스인지 확인

---

**[입력 예시]**

12/25

**[출력 예시]**

크리스마스입니다.

```python
is_christmas = input('날짜를 입력해주세요 ex)12/24 : ')
print(is_christmas)
# 아래에 코드를 작성하라

print(is_christmas)
if is_christmas == '12/25':
	print('크리스마스입니다.')
else:
	print('크리스마스가 아닙니다.')
```

### 1-4 홀/짝 판독기

조건문을 통해 변수 num의 값과 홀/짝 여부 출력

---

**[입력 예시]**

3

**[출력 예시]**

홀수입니다.

~~~python
num = int(input('숫자를 입력하세요 : '))
# 아래에 코드를 작성하세요

if num % 2 == 1:
    print('홀수입니다.')
else:
    print('짝수입니다.')
~~~



## 2. elif 복수 조건

2개 이상의 조건 => **elif <조건>:** 을 활용

### 2-1 복수 조건문 연습

조건문을 통해 변수 score에 따른 평점을 출력

90점 이상 :  A  

80점 이상 : B  

70점 이상 : C  

60점 이상 : D  

60점 미만 : F

---

**[입력 예시]**

85

**[출력 예시]**

B

```python
score = int(input('점수를 입력하세요 : '))
# 아래에 코드를 작성하세요

if score >= 90:
    print('A')
elif score >= 80:
    print('B')
elif score >= 70:
    print('C')
elif score >= 60:
    print('D')
else:
    print('F')
```

****** 순서에 유의해야 함! (순차적 수행)

## 3. Nested Conditional Statement : 중첩 조건문

조건문은 다른 조건문에 중첩 가능

### 3-1 활용

위 복수 조건문 2개 코드를 활용하여 95점 이상이면, "참 잘했어요"도 함께 출력

---
**[출력 예시]**

A

참 잘했어요.

~~~python
if score >= 90:
    print('A')
    if score >= 95:
        print('참 잘했어요')
elif score >= 80:
    print('B')
elif score >= 70:
    print('C')
elif score >= 60:
    print('D')
else:
    print('F')
~~~



## 4. Conditional Expression : 조건 표현식

일반적으로 조건에 따라 값을 정할 때 활용하며 **삼항 연산자(Ternary Operator)**라고도 불림

---

**활용법**

 =>    true_value if <조건식> else false_value

### 4-1 조건 표현식 작성

다음의 코드와 동일한 조건 표현식 작성

```python
num = 2
if num % 2:
    result = '홀수다.'
else:
    result = '짝수다.'
print(result)
```
---

**[출력 예시]**

```
짝수입니다.
```

### 4-2 조건 표현식과 동일한 if 문 작성

다음의 코드와 동일한 if문 작성

```python
num = -5
value = num if num >= 0 else 0
print(value)
```
---
**[출력 예시]**

0

```python
num = int(input())

if num >= 0:
    print(num)
else:
    print(0)
```



# Loop Statement : 반복문

**while** &  **for**

## 1. while 반복문

조건식이 참(True)인 경우 반복적으로 코드 실행

### 1-1 활용

- **문법**

```python
while <조건식>:
    <코드 블럭>
```

- 예시

```python
while True:
    print('조건식이 참일 때까지')
    print('계속 반복')
```

### 1-2 주의

- 조건식 뒤에 콜론(:) 반드시 필요
- 이후 실행될 코드 블럭 => **4spaces** 들여쓰기
- **반드시 종료조건 설정해야!**

```python
a = 0
while a < 5:
	print(a)
	a += 1
print('끝')
```



### 1-3 while문 작성
사용자가 "안녕"이라고 입력할 때까지 인사하는 코드 작성

```

```



### 1-4 Summation : 합

(1~사용자가 입력한 양의 정수까지)의 **총합** 구하는 코드 작성

---
**[입력 예시]**

10

**[출력 예시]**

55

### 1-5 한자리씩 출력

사용자로부터 숫자 입력 받은 양의 정수의 각 자리 수를 1의 자리부터 차례대로 출력하는 코드 작성


---
**[입력 예시]**

185

**[출력 예시]**

5

8

1

## 2. for문

시퀀스(string, tuple, list, range)나 다른 순회가능한 객체(iterable)의 요소들을 순회

---

### 2-1 활용
- **문법**

```python
for <임시변수> in <순회가능한데이터(iterable)>:
    <코드 블럭>
```

- **예시**

```python
for menu in ['김밥', '햄버거', '피자', '라면']:
    print(menu)
```

### 2-2 for문 작성
for문 활용 => 사용자가 입력한 문자를 한글자씩 출력

---
**[입력 예시]**

```
문자를 입력하세요 : 메롱!
```

**[출력 예시]**

```
메
롱
!
```

###  2-3 for문과 if문 작성

반복문과 조건문만 활용하여 1~30까지 숫자 중 홀수만 출력

---

**[출력 예시]**

```
1
3
5
...
27
29
```

### 2-4 list 순회에서 index의 활용

#### range(리스트의 길이)
range()와 순회할 list의 길이 활용하여 index 조작 가능

#### * enumerate()
- index와 값을 함께 활용 가능

- enumerate()를 활용하면, 추가적인 변수 활용 가능

- enumerate()는 [내장 함수](https://docs.python.org/ko/3.6/library/functions.html) 중 하나, 다음과 같이 구성

- enumerate(iterable, start=0)

  : 열거 객체를 돌려준다. iterable은 시퀀스, 이터레이터 또는 이터레이션을 지원하는 다른 객체여야 한다. enumerate( )에 의해 반환된 이터레이터의 -next-( ) 메서드는 카운트(기본값 0을 갖는 start부터)와 iterable을 이터레이션 해서 얻어지는 값을 포함하는 튜플을 돌려준다.

  
## 3. break, continue, for-else : 반복제어

### 3-1 break

반복문을 종료 => for문 or while문에서 빠져나감

### 3-2 break 활용

조건문, 반복문, break 활용 => 리스트에서 쌀이 나올 때 for문 멈추는 코드 작성

---

**[출력 예시]**

보리

보리

쌀

잡았다!

### 3-3 continue

continue 이후의 코드 수행하지 않고 **다음 요소부터 계속**하여 반복 수행

### 3-4 continue문 작성

나이가 입력된 리스트가 있을 때 => 조건문, 반복문, continue 활용 => 20살 이상일때만 "성인입니다"라는 출력을 하는 코드 작성

**[출력 예시]**

23 살은 성인입니다.

30 살은 성인입니다.

25 살은 성인입니다.

31 살은 성인입니다.

### 3-5 else

반복문을 끝까지 실행한 이후에 실행됨
- 반복에서 리스트의 소진 (for문의 경우) 또는 조건이 거짓이 되어서 (while문의 경우) 종료할 때 실행됨

- 그러나 반복문이 **break문으로 종료될 때**는 실행되지 않는다.

  ( break를 통해 중간에 종료되지 않은 경우만 실행)

### 3-6 for-else 활용

조건문, 반복문, break, else 활용 => 아래 코드와 동일한 코드 작성

<numbers 리스트에 4가 있을 경우 `True`를 출력, 없을 경우 `False`를 출력>

---

**[출력 예시]**

`False`

### 3-7 pass
아무것도 하지 않음. 문법적으로 문장이 필요하지만 프로그램이 딱히 할 일 없을 때 자리 채우는 용도로 사용

**pass **와 **continue** 차이