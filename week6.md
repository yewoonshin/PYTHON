# Python 6주차 정규 과제 

📌Python 정규과제는 매주 정해진 분량의 『*파이썬 라이브러리를 활용한 데이터 분석*』 을 읽고 학습하는 것입니다. 이번주는 아래의 **Python_6th_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 참고 자료를 통해 보완하는 것이 좋습니다.

**교재 실습 예제 파일은 07_Python_Template 레포지토리의 notebooks 폴더에 업로드되어 있습니다.**

**👀(수행 인증샷은 필수입니다.)** 

## Python_6th_TIL

### 7장 데이터 정제 및 준비 
#### 3. 확장 데이터 유형
#### 4. 문자열 다루기 
#### 5. 범주형 데이터
#### 6. 마치며
### 8장 데이터 준비하기: 조인, 병합, 변형
#### 1. 계층적 색인
#### 2. 데이터 합치기 
#### 3. 재구성과 피벗
#### 4. 마치며 


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.25~82    | ✅         |
| 2주차 | p.83~129   | ✅         |
| 3주차 | p.131~179  | ✅         |
| 4주차 | p.181~246 | ✅         |
| 5주차 | p.247~309 | ✅         |
| 6주차 | p.310~379 | ✅         |
| 7주차 | p.381~465 | 🍽️         |


<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 학습 내용 정리

## 1. 확장 데이터 유형

### 개념정리

판다스는 넘파이에서 기본적으로 지원하지 않는 자료형이더라도 사용할 수 있도록 하는 확장형 시스템을 개발함 
pd.Int64Dtype() 대신에 "エnt64”로 줄여서 사용할수도 있다. 대소문자를 구분하지 않으면 
넘파이 기반의 비확장형으로 처리된다
- 판다스에는 넘파이 객체 배열을 사용하지 않는 문자열 데이터를 위한 특수한 확장형이 존재한 
다(별도로 설치해야 하는 pyarrow 라이브러리가 필요하다)
- Series의 astype 메서드에 확장형을 인수로 전달하면 데이터 정제 과정에서 손쉽게 변환을 
수행할 수 있다

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="377" height="212" alt="image" src="https://github.com/user-attachments/assets/a51029c7-4936-43b9-9a21-de1684ec0c2d" />
<img width="807" height="441" alt="image" src="https://github.com/user-attachments/assets/fcecc878-cbba-4942-8adf-3e479cf41c43" />



## 2. 문자열 다루기 

### 개념정리

대부분의 텍스트 연산은 문자열 객체의 내장 메서드를통해 간단하게 처리할 수 있다. 더 
복잡한 패턴 매칭이나 텍스트 조작에는 정규 표현식이 필요하다. 판다스는 배열 데이터 전체에 
쉽게 정규 표현식을 적용하고 누락된 데이터를 편리하게 처리하는 기능을 제공한다
1. 내장 문자열 객체 메서드
-문자열을 다루는 대부분의 애플리케이션은 내장 문자열 메서드만으로도 충분하다. 예를 들어 
쉼표로 구분된 문자열은 split 메서드를 이용해서 분리한다

- 일치하는 부분 문자열substring의 위치를 찾는 메서드도 있다 index나 find를 사용할 수도 있지 
만 파이썬의 in 예약어를 사용하면 더 쉽게 찾을 수 있다.

2. 정규 표현식
정규 표현식은 텍스트에서 문자열 패턴을 찾는 유연한 방법을 제공
▶️흔히 regex라 부르는 단일 표현식은 정규 표현식 언어로 구성된 문자열

re 모듈 함수는 패턴 매칭, 치환, 분리 세 가지로 나눌 수 있다. 물론 이 세 가지는 모두 서로 
연관되어 있으며 정규 표현식은 텍스트 내에 존재하는 패턴을 표현하고 이를 여러 가지 다양한 
목적으로 사용할 수 있다. 


match와 search는 findall 메서드와 밀접하게 관련된다. findall은 문자열에서 일치하 
는 모든 부분 문자열을 찾지만 search 메서드는 패턴과 일치하는 첫 번째 항목을 반환한다. 
match 메서드는 이보다 더 엄격해서 문자열의 시작 부분에서 일치하는 것만 찾는다. 
### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="271" height="76" alt="image" src="https://github.com/user-attachments/assets/10b1dced-1c14-42bf-abf6-4b8700e0e4e1" />

<img width="397" height="202" alt="image" src="https://github.com/user-attachments/assets/d13ad44b-4f83-401e-8b43-f0df10ef7871" />


## 3. 범주형 데이터

### 개념정리

정수 표현을 범주형 또는 딕셔너리형 표기법이라고 한다. 별개의 값을 담은 배열 
은 범주형, 딕셔너리형 또는 단계별 데이터라고 부른다.

판다스에는 정수 기반의 범주형 데이터를 표현하는 특수한 데이터 유형인 Categorical 확장 
형이 있다. 

범주형으로 변경하는 경우 명시적으로 지정하지 않는 한 특정 순서를 보장하지 않는다. 따라서 
범주형 배열은 입력 데이터의 순서에 따라 순서가 다를 수 있다. f rom_codes를 사용하거나 다 
른 범주형 데이터 생성자를 이용하면 순서를 지정할 수 있다

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->
<img width="877" height="690" alt="image" src="https://github.com/user-attachments/assets/d646aa97-8bc2-4d48-b008-db46795c3e4d" />

<img width="936" height="492" alt="image" src="https://github.com/user-attachments/assets/b70b36ba-6a54-436c-86d5-c289b5b3f6b9" />


## 4. 계층적 색인 

### 개념정리

계층적인 색인은 판다스의 중요한 기능이며 축에 대해 둘 이상의 색인 단계를 
지정할 수 있도록 한다.  차원 수가 높은（고차원） 데이터를 낮은 차원 
의 형식으로 다룰 수 있게 해주는 기능이다.


계층적 색인에서 계층의 순서를 바꾸거나 특정 계층에 따라 데이터를 정렬해야 하는 경우가 있 
다. swaplevel은 넘겨받은 두 개의 계층 번호나 이름이 뒤바뀐 새로운 객체를 반환한다（하지 
만 데이터는 변경되지 않는다）

DataFrame과 Series의 많은 기술 통계와 요약 통계는 level 옵션을 갖는다. 이는 어떤 하나 
의 축에 대해 합을 구하고 싶은 단계를 지정하는 옵션이다. 앞서 살펴본 DataFrame에서 행이 
나 열의 합을 계층별로 구할 수 있다
### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="922" height="650" alt="image" src="https://github.com/user-attachments/assets/1a3d37cd-94f6-48d5-924c-ccba025ad357" />
<img width="905" height="431" alt="image" src="https://github.com/user-attachments/assets/80978ebb-d94a-445b-86c2-81bf5f347225" />



## 5. 데이터 합치기 

### 개념정리

판다스 객체에 저장된 데이터를 합치는 방법은 여러 가지다.
, pandas.merge： 하나 이상의 키를 기준으로 DataFrame의 행을 연결한다. SQL이나 다른 관계형 데이 
터베이스의 조인연산과 유사하다.
• pandas.concat： 하나의 축을 따라 객체를 이어 붙인다
・ combine_first ； 두 객체를 겹쳐서 한 객체에서 누락된 데이터를 다른 객체에 있는 값으로 채운다

병합（머지merge）나 조인 연산은 관계형 데이터베이스의 핵심 연산이며 하나 이상의 키를 사용 
해 데이터 집합의 행을 합친다. 판다스에서는 pandas.merge 함수를 이용해서 이런 알고리듬 
을 데이터에 적용한다.

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="887" height="477" alt="image" src="https://github.com/user-attachments/assets/9518d20e-21ba-408b-86c2-7d82c9a6d71e" />
<img width="897" height="406" alt="image" src="https://github.com/user-attachments/assets/6244a616-a3c1-41d4-8c77-3c0ca70fbbd0" />



## 6. 재구성과 피벗 

### 개념정리

표 형식의 데이터를 재배치하는 다양한 기본 연산을 재구성 또는 피벗 연산이라고 부름 
계층적 색인은 다음과 같이 DataFrame의 데이터를 재배치하는 일관된 방법을 제공한다.
・ stack: 데이터의 열을행으로피벗（또는회전）한다
• unstack: 행을열로피벗한다 

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="942" height="237" alt="image" src="https://github.com/user-attachments/assets/7f9a9bfa-883b-4617-b986-88c81aca0cf9" />

<img width="915" height="362" alt="image" src="https://github.com/user-attachments/assets/b1169933-8a91-43f9-ac97-d44a8698dc5c" />


# 2️⃣ 실습 과제

각 문제에 대한 실행 결과가 확인되도록 코드를 작성하고 실행한 뒤, **모든 문제의 실행 화면을 캡처하여 제출하시기 바랍니다.**

**1. 아래 코드를 실행하여 분석에 필요한 기초 데이터를 생성합니다.**
```python
import pandas as pd
import numpy as np

# 1. 고객 기본 정보
customers = pd.DataFrame({
    "customer_id": [101, 102, 103, 101, 104, 105],
    "name": ["Kim", "Lee", "Park", "Kim", "Choi", "Jung"],
    "age": [23, 35, 45, 23, 18, 55],
    "email": ["kim@gmail.com", "lee@naver.com", "park@gmail.com", "kim@gmail.com", "choi@naver.com", "jung@gmail.com"]
})

# 2. 구매 이력 정보
purchases = pd.DataFrame({
    "customer_id": [101, 102, 103, 106],
    "product": ["iPhone", "iPad", "MacBook", "Watch"],
    "amount": [1500, 800, 2500, 500]
})
```

**2. 문제**
```
1. 중복 고객 제거 및 연령대 그룹화
  - 문제 설명: 고객의 연령대 나누기 
  - drop_duplicates()를 사용하여 customer_id 기준 중복을 제거하세요.
  - pd.cut()을 사용하여 나이(age)를 10대(10-19), 20대(20-29), 30대 이상(30-100)으로 나누고 age_group 열을 만드세요.
  - print()를 이용해 정제된 고객 데이터프레임을 출력하세요.

2. 이메일 도메인 추출
  - 문제 설명: 고객들의 이메일 도메인(gmail, naver 등) 정보만 추출 
  - str.split()과 str.get()을 사용하여 이메일 주소에서 @ 뒷부분의 도메인만 추출하여 domain 열을 만드세요.
  - print()를 이용해 도메인이 추가된 결과를 출력하세요.

3. 고객 정보와 구매 이력 병합
  - 문제 설명: 고객 정보와 구매 이력을 하나로 합치기 
  - pd.merge()를 사용하여 customers와 purchases를 customer_id 기준으로 합치세요.
  - 이때 구매 이력이 없는 고객 정보도 모두 유지되도록 외부 조인(Outer Join) 방식을 사용하세요.
  - print()를 이용해 병합된 최종 데이터프레임을 출력하세요.
```

<img width="927" height="772" alt="image" src="https://github.com/user-attachments/assets/788cc201-78bb-4c6c-8615-e4832d44fc66" />




### 🎉 수고하셨습니다.







