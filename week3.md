# Python 3주차 정규 과제 

📌Python 정규과제는 매주 정해진 분량의 『*파이썬 라이브러리를 활용한 데이터 분석*』 을 읽고 학습하는 것입니다. 이번주는 아래의 **Python_3rd_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 참고 자료를 통해 보완하는 것이 좋습니다.

**교재 실습 예제 파일은 07_Python_Template 레포지토리의 notebooks 폴더에 업로드되어 있습니다.**

**👀(수행 인증샷은 필수입니다.)** 

## Python_3rd_TIL

### 4장 넘파이 기본: 배열과 벡터 연산
#### 1. 다차원 배열 객체 ndarray
#### 2. 난수 생성
#### 3. 유니버설 함수: 배열의 각 원소를 빠르게 처리하는 함수
#### 4. 배열을 이용한 배열 기반 프로그래밍
#### 5. 배열 데이터의 파일 입출력
#### 6. 선형대수
#### 7. 계단 오르내리기 예제
#### 8. 마치며 


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.25~82    | ✅         |
| 2주차 | p.83~129   | ✅         |
| 3주차 | p.131~179  | ✅         |
| 4주차 | p.181~246 | 🍽️         |
| 5주차 | p.247~309 | 🍽️         |
| 6주차 | p.310~379 | 🍽️         |
| 7주차 | p.381~465 | 🍽️         |


<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 학습 내용 정리

## 1. 다차원 배열 객체 ndarray

### 개념정리
numpy는 일반적인 산술 데이터 처리를 위한 기반 라이브러리 제공 
핵심 기능은 ndarray라고 하는 N채월 배열 객체 , 이는 대규모 데이터셋을 담을 수 있는 빠르고 유연한 자료구조 
ndarray의 모든 원소는 같은 자료형이여야 한다. 모든 배열은 각 차원의 크기를 알려주는 shape튜플과 배열에 저장된 자료형을 알려주는 dtype객체를 가짐 .

ndarray 생성 : array 함수 생성하기 . 리스트 길이가 동일한 중첩된 순차 데이터는 다차원 배열로 변환 가능 
명시적으로 지정하지 않는 한 numpy, array는 생성될 떄 적절한 자료형을 추론함. 

자료형은 ndarray가 메모리에 있는 특정 데이터를 해석하는데 필요한 정보를 담고있는 특수 객체 
ndarray의 astype메서드를 사용해 dtype를 다른 형으로 명시적 변환 가능 


### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="775" height="542" alt="image" src="https://github.com/user-attachments/assets/823db0d7-f8e1-4b29-b3d5-03c34a19d7e2" />
<img width="690" height="448" alt="image" src="https://github.com/user-attachments/assets/e6db63bd-9806-4ada-98fe-b3131f7a9006" />



## 2. 난수 생성

### 개념정리

numpy.random모듈은 파이썬 내장 random 모듈을 보강해 다양한 종류의 확률분포로부터 효과적으로 표본값 생성하는데 주로 사용 
파이썬 내장 random모듈은 한번에 하나의 값만 생성 
난수 생성기의 시드값에 따라 정해진 난수를 알고리즘으로 생성하기 때문 

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="767" height="162" alt="image" src="https://github.com/user-attachments/assets/b4b6f70a-864b-45c8-9f71-297149236a27" />
<img width="560" height="125" alt="image" src="https://github.com/user-attachments/assets/11ed2e5c-7623-4c42-b243-b855016c1fa0" />



## 3. 유니버설 함수: 배열의 각 원소를 빠르게 처리하는 함수

### 개념정리

ufunc라고도 부르는 유니버설 함수는 narray함수 안의 데이터 원소별로 연산을 수행하는 함수임
유니버설 함수는 하나 이상의 스칼라 값을 받아 하나 이상의 스칼라 결괏값을 반환하는 간단한 함수를 빠르게 수행하는 벡터화된 래퍼 함수 

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="756" height="397" alt="image" src="https://github.com/user-attachments/assets/65d2c4e1-e721-498f-9072-fc7e43a12f91" />

<img width="767" height="303" alt="image" src="https://github.com/user-attachments/assets/a4a3fa05-dede-491c-9d80-270b204cbbd8" />


## 4. 배열을 이용한 배열 기반 프로그래밍

### 개념정리 ###
넘파이 배열을 사용하면 반복문 작성 없이 간결한 배열 연산을 통해 많은 종류의 데이터 처리 작업 가능 
배열 연산을 사용해서 반복문을 명시적으로 제거하는 기법을 벡터화라고 하는데 일반적으로 벡터화된 베열에 대한 산술 연산은 순수 파이썬 연산에 비해 빠르다 
### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="793" height="307" alt="image" src="https://github.com/user-attachments/assets/d75a46ea-2e33-49ee-844c-f5934e30367e" />

<img width="822" height="512" alt="image" src="https://github.com/user-attachments/assets/1fefd380-03cf-4723-89fe-5f858e213022" />


## 5. 배열 데이터의 파일 입출력

### 개념정리

넘파이는 디스크에서 텍스트나 바이너리 형식의 데이터를 불러오거나 저장할 수 있다. numpy.save와 numpy.load는 배열 데이터를 효과적으로 디스크에 저장하고 불러오는 함수이다 
저장되는 파일 경로가 .npy로 끝나지 않으면 자동적으로 확장자가 추가된다. 

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->
<img width="501" height="116" alt="image" src="https://github.com/user-attachments/assets/cd4d00f1-208a-436b-9c2e-fd8ddec12a99" />

<img width="657" height="313" alt="image" src="https://github.com/user-attachments/assets/47125e10-b9fc-4ddd-86c2-b2b9848f2da7" />



## 6. 선형대수

### 개념정리

행렬의 곱셈, 분할, 행렬식, 정사각행렬 계산같은 선형대수는 배열을 다루는 라이브러리에서 매우 중요한 부분임. 두개의 2차원 배열을 *연산자로 곱하면 행렬 곱셈이 아니라 대응하는 각각의 원소의 곱을 계산한다. 따라서 배열 메서드이자 넘파이 네임스페이스 안의 함수인 dot함수를 이용해 행렬 곱셈을 계산해야한다. 

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="662" height="221" alt="image" src="https://github.com/user-attachments/assets/b0b32ab4-edeb-4ca3-bddb-5d652dcfecbb" />

<img width="757" height="406" alt="image" src="https://github.com/user-attachments/assets/25dcc658-8131-41ef-9709-cc966983f5dd" />


## 7. 계단 오르내리기 예제

### 개념정리

계단 오르내리기 예제는 배열 연산의 활용법을 보여주는 애플리케이션. 계단의 중간에서 같은 확률로 한 계단 올라가거나 내려간다고 가정 


### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="620" height="245" alt="image" src="https://github.com/user-attachments/assets/7b2fb970-e6d8-46c7-9baf-3ec044040314" />




# 2️⃣ 실습 과제

각 문제에 대한 실행 결과가 확인되도록 코드를 작성하고 실행한 뒤, **모든 문제의 실행 화면을 캡처하여 제출하시기 바랍니다.**

**1. 아래 코드를 실행하여 5일간 3개 품목의 판매량 데이터를 생성합니다.**
```python
import numpy as np

# 5일간 3개 품목의 판매량
# 행: 월, 화, 수, 목, 금 / 열: 사과, 배, 포도
sales = np.array([
    [45, 30, 75],  # 월요일
    [50, 60, 15],  # 화요일
    [85, 20, 40],  # 수요일
    [30, 90, 55],  # 목요일
    [70, 45, 80]   # 금요일
])
```

**2. 문제**
```
1. 품목별 총 판매량 계산 및 출력
  - 문제 설명: 각 품목이 5일 동안 총 몇 개 팔렸는지 계산
  - sum() 메서드의 axis 옵션을 활용하여 품목별 합계를 구하세요.
  - print()를 이용해 품목별 총 판매량 리스트를 출력하세요.

2. 특정 기간 및 품목 추출
  - 문제 설명: 수요일부터 금요일까지(3~5행), 첫 번째와 두 번째 품목(사과, 배)의 판매량만 따로 보기 
  - 배열 슬라이싱을 사용하여 해당 데이터를 추출하세요.
  - print()를 이용해 추출된 3x2 배열을 출력하세요.

3. 목표 미달 판매량 조정
  - 문제 설명: 하루 판매량이 40개 미만인 경우, 값을 0으로 표시하고, 40개 이상인 경우는 기존 값을 유지
  - np.where() 함수를 사용하여 40 미만은 0, 40 이상은 원래 값을 가지는 새로운 배열을 만드세요.
  - print()를 이용해 수정된 배열을 출력하세요.
```

<img width="593" height="351" alt="image" src="https://github.com/user-attachments/assets/91b7dabd-0a22-48f6-91a4-2ed04b8e163c" />

<img width="665" height="438" alt="image" src="https://github.com/user-attachments/assets/873d3d25-df00-41fe-93e0-0b71543d36f2" />



### 🎉 수고하셨습니다.






