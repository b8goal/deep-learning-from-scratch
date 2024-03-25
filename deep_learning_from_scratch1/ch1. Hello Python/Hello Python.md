##### 날짜 : 2024-03-15 19:03
##### 주제 : #Python
---
# Memo :
>[!note]

## Python?
- Open Source로 자유롭게 이용 가능하다.
- 자체의 뛰어난 성능에 numpy와 SciPy 같은 수치 계과 통계 처리를 다루는 탁월한 library가 더해져 **data science** 분야에서 널리 쓰인다.

### ✔️ Python 활용하기
#### 1. 산술 연산
```python
print(1-2)
print(4 * 5)
print(7 / 5)
print(3 ** 2) # 거듭제곱

output
-1
20
1.4
9
```

#### 2. 자료형
자료형 : 데이터의 성질을 나타내는 것
ex) 정수, 실수, 문자열 등
python에서는 type() 함수로 특정 데이터의 자료형을 알아볼 수 있음.
##### 자료형(Data Type)의 종류
![](https://i.imgur.com/Zcd5E4z.png)


```python
print(type(-1))
print(type(3.141592))
print(type(3 + 4j))
print(type(True), type(False))
print(type("hello"))
print(type([1,2,3,4,5]))
print(type((5, 4, 3, 2, 1)))
print(type({"apple","banana"}))
print(type({"key" : "value"}))

output
<class 'int'>
<class 'float'>
<class 'complex'>
<class 'bool'> <class 'bool'>
<class 'str'>
<class 'list'>
<class 'tuple'>
<class 'set'>
<class 'dict'>
```
#### 3. 변수
Python은 동적 언어로 변수의 자료형을 상황에 맞게 자동으로 결정한다.
```python
x = 10
print(x)

x = 100
print(x)

y = 3.14
print(x * y)

print(type(x * y))

output
10
100
314.0
<class 'float'>
```
#### 4. 리스트
index와 slicing 기법을 통해 원하는 원소에 접근할 수 있다.
```python
a = [1,2,3,4,5]
print("a =", a)
print("len(a) =", len(a)) # length of list

print("a[0] =", a[0])
print("a[4] =", a[4])
a[4] = 99

# slicing
print("a[0:2] =", a[0:2]) # index 0 to 1 (not include 2th)
print("a[1:]  =", a[1:])  # index 1 to last
print("a[:3]  =", a[:3])  # index first to 2 (not include 3th)
print("a[:-1] =", a[:-1]) # index first to last-1 
print("a[:-2] =", a[:-2]) # index first to last-2 

output
a = [1, 2, 3, 4, 5]
len(a) = 5
a[0] = 1
a[4] = 5
a[0:2] = [1, 2]
a[1:]  = [2, 3, 4, 99]
a[:3]  = [1, 2, 3]
a[:-1] = [1, 2, 3, 4]
a[:-2] = [1, 2, 3]
```
#### 5. 딕셔너리
딕셔너리는 key와 value를 한쌍으로 저장한다.
```python
profile = {'height':180}
print("profile['height'] =", profile['height'])

profile['weight'] = 78
print(profile)

output
profile['height'] = 180
{'height': 180, 'weight': 78}
```
#### 6. bool
bool이라는 자료형은 True(참)와 False(거짓)이라는 두 값 중 하나를 취한다.
and, or, not 연산자를 사용할 수 있음.
```python
hungry = True
sleepy = False
print((type(hungry), type(sleepy)))

print("not hungry =", not hungry)
print("not sleepy =", not sleepy)
print("hungry and sleepy =", hungry and sleepy)
print("hungry or sleepy  =", hungry or sleepy)

output
(<class 'bool'>, <class 'bool'>)
not hungry = False
not sleepy = True
hungry and sleepy = False
hungry or sleepy  = True
```
#### 7. if 문
조건에 따른 처리는 if/else문 사용
```python
hungry = True
sleepy = False

if hungry:
    print("I'm hungry")
elif sleepy:
    print("I'm sleepy")
else:
    print("I'm neither hungry nor sleepy")

output
I'm hungry
```
#### 8. for 문
```python
a = [1,2,3,4,5,6,7,8,9]

for _ in a:
  print(_)

output
1
2
3
4
5
6
7
8
9
```
#### 9. 함수
특정 기능을 수행하는 일련의 명령들을 묶어 하나의 함수로 정의
```python
def check_state(hungry, sleepy):
    if hungry and sleepy:
        return "I'm both hungry and sleepy"
    elif hungry:
        return "I'm hungry"
    elif sleepy:
        return "I'm sleepy"
    else:
        return "I'm neither hungry nor sleepy"

# 함수 호출
print(check_state(False, False))
print(check_state(True, False))
print(check_state(False, True))
print(check_state(True, True))

output
I'm neither hungry nor sleepy
I'm hungry
I'm sleepy
I'm both hungry and sleepy
```
#### 10. 클래스
개발자가 직접 클래스를 정의하면 독자적인 자료형을 만들 수 있다.
클래스에는 그 클래스만의 전용 함수(메서드)와 속성을 정의할 수 있다.

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def greet(self):
        return f"Hello, my name is {self.name} and I am {self.age} years old."

# 클래스 인스턴스 생성
person1 = Person("John", 30)
person2 = Person("Jane", 25)

# 메서드 호출
print(person1.greet())
print(person2.greet())

print(type(person1))

output
Hello, my name is John and I am 30 years old.
Hello, my name is Jane and I am 25 years old.
<class '__main__.Person'>
```
`__init__` 이라는 메서드는 클래스를 초기화하는 방법을 정의한다.
이 메서드를 constructor 라고 하며, 클래스의 인스턴스가 만들어질 때 한번만 불린다.

파이썬에서는 메서드의 첫 번째 인수로 자신(자신의 인스턴스)를 나타내는 self를 명시적으로 쓰는게 특징이다.

#### 11. Numpy
numpy는 파이썬에서 수치 연산을 수행하기 위한 외부 라이브러리이다. 
다차원 배열 객체와 이러한 배열을 처리하기 위한 다양한 함수와 연산을 제공하여 데이터 분석 및 수치 계산 작업을 효율적으로 수행할 수 있게 도와준다.
```python
import numpy as np
```

위와 같이 import 문을 통해 라이브러리를 가져와야 한다.
이때, np 라는 이름으로 가져옴으로써 앞으로 numpy method들을 np를 통해 참조할 수 있다.

```python
x = np.array([1.0, 2.0, 3.0])
print(x)
print(type(x))

output
[1. 2. 3.]
<class 'numpy.ndarray'>
```

```python
x = np.array([1, 2, 3])
y = np.array([2, 4, 6])

print(x+y)
print(x-y)
print(x*y)
print(x/y)

print(x / 2.0)

output
[3 6 9]
[-1 -2 -3]
[ 2  8 18]
[0.5 0.5 0.5]
[0.5 1.  1.5]
```


### 주요 특징

1. **다차원 배열**: `numpy`는 `ndarray`라는 다차원 배열 객체를 제공한다. 이 배열은 동일한 타입의 데이터를 저장하며, 빠른 연산을 위해 최적화되어 있다.
   ```python
   import numpy as np 
   arr = np.array([1, 2, 3, 4, 5])
   ```
2. 브로드캐스팅: 다른 형상을 가진 배열 간의 연산을 가능하게 해주는 기능이다.
    ```python
    arr1 = np.array([[1, 2], [3, 4]]) 
    arr2 = np.array([1, 2]) 
    result = arr1 + arr2
    ```
3. 유니버설 함수: 배열의 각 요소에 대한 연산을 빠르게 수행하는 함수이다.
    ```python
    arr = np.array([1, 2, 3, 4, 5]) result = np.sqrt(arr)
    ```
4. 선형 대수 연산, 통계 관련 함수: numpy는 선형 대수 연산, 통계 관련 함수도 제공한다.
    ```python
    arr = np.array([[1, 2], [3, 4]])
    transpose = np.transpose(arr)
    ```
5. 효율적인 메모리 사용: C나 Fortran과 같은 언어로 작성된 numpy는 내부적으로 효율적인 메모리 사용을 위해 설계되었다.

#### 12. Matplotlab
matplotlab은 파이썬에서 데이터를 시각화하기 위한 라이브러리다. 
다양한 그래프와 차트를 생성하고, 복잡한 데이터를 직관적으로 이해할 수 있는 형태로 표현하는 데 사용된된다.

### 주요 특징

#### 1. **다양한 종류의 그래프 지원**
`matplotlib`은 선 그래프, 막대 그래프, 히스토그램, 산점도 등 다양한 종류의 그래프를 그릴 수 있다.
```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [1, 4, 9, 16, 25]

plt.plot(x, y)
plt.show()

```
![](https://i.imgur.com/GKnOCRW.png)

#### 2. **고급 시각화 기능**
레이블, 범례, 타이틀 등 그래프의 다양한 요소를 커스터마이징할 수 있다.
```python
plt.plot(x, y)
plt.title("Sample Plot")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")
plt.grid(True)
plt.show()
```
![](https://i.imgur.com/q8PnvGB.png)

#### 3. **다중 서브플롯**
하나의 그래프 영역에 여러 개의 서브플롯을 그릴 수 있다.
```python
plt.subplot(1, 2, 1)
plt.plot(x, y, 'r--')

plt.subplot(1, 2, 2)
plt.plot(y, x, 'g*-')

plt.show()
```
![](https://i.imgur.com/KH6bl1N.png)

#### 4. **저장 및 내보내기**
그래프를 이미지 파일로 저장하거나 다른 포맷으로 내보낼 수 있다.
```python
plt.savefig('sample_plot.png', dpi=300)
```

## Summary
>[!summary]

python에 대해 간략하게 알아보았다.
data type, 문법, 라이브러리에 대해 공부함.
# Reference
---
### 출처(참고문헌)
- https://velog.io/@kyj93790/%EB%B0%91%EB%B0%94%EB%8B%A5%EB%B6%80%ED%84%B0-%EC%8B%9C%EC%9E%91%ED%95%98%EB%8A%94-%EB%94%A5%EB%9F%AC%EB%8B%9D-1.-%ED%97%AC%EB%A1%9C-%ED%8C%8C%EC%9D%B4%EC%8D%AC
### 연결문서
- 