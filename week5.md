# Python 5주차 정규 과제 

📌Python 정규과제는 매주 정해진 분량의 『*파이썬 라이브러리를 활용한 데이터 분석*』 을 읽고 학습하는 것입니다. 이번주는 아래의 **Python_5th_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 참고 자료를 통해 보완하는 것이 좋습니다.

**교재 실습 예제 파일은 07_Python_Template 레포지토리의 notebooks 폴더에 업로드되어 있습니다.**

**아나콘다 환경에서는 많은 패키지가 기본적으로 포함되어 있어 별도의 설치 없이 사용할 수 있지만, 환경에 따라 conda install이나 pip install이 필요할 수 있습니다.**

**👀(수행 인증샷은 필수입니다.)** 

## Python_5th_TIL

### 6장 데이터 로딩과 저장, 파일 형식
#### 1. 텍스트 파일에서 데이터를 읽고 쓰는 법
#### 2. 이진 데이터 형식
#### 3. 웹 API와 함께 사용하기
#### 4. 데이터베이스와 함께 사용하기
#### 5. 마치며
### 7장 데이터 정제 및 준비
#### 1. 누락된 데이터 처리하기
#### 2. 데이터 변형 


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.25~82    | ✅         |
| 2주차 | p.83~129   | ✅         |
| 3주차 | p.131~179  | ✅         |
| 4주차 | p.181~246 | ✅         |
| 5주차 | p.247~309 | ✅         |
| 6주차 | p.310~379 | 🍽️         |
| 7주차 | p.381~465 | 🍽️         |


<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 학습 내용 정리

## 1. 텍스트 파일에서 데이터를 읽고 쓰는 법

### 개념정리

판다스는 표 형식의 자료를 dataframe객체로 읽어오는 몇 가지 기능을 제공한다 
파일을 읽어오는 몇 가지 옵션이 존재. 판다스가 자동으로 열 이름을 생성하도록 하거나 직접 열 이름 저장 가능 
가끔 고정된 구분자 없이 공백이나 
다른 패턴으로 필드를 구분해놓은 경우가 있음 
파싱 함수는 파일 형식에서 발생할 수 있는 매우 다양한 예외를 잘 처리할 수 있도록 많은 추가 인수를 가짐 
예를 들어 skiprows를 이용해 행들을 건너뛸 수 있음. 

판다스는 누락된 값을 NaN으로 출력한다 

pandas.read_csv에는 다양한 기본 NA 값 표현 목록이 있지만 keep_default_na 옵션으로 
비활성화할 수 있다.

매우 큰 파일을 처리할 때 인수를 제대로 설정했는지 알아보기 위해 파일의 일부분만 읽기 가능 

파일을 여러 고작으로 나눠 읽고 싶다면 chunksize 옵션으로 행 개수 설정 가능 

읽어오기와 마찬가지로 데이터를 구분자로 구분한 형식으로 내보내는 것도 가능 

csv 파일은 다양한 형태로 존재할 수 있고 다양한 구분자, 문자열을 둘러싸는 방법, 개행 문자 같은 것들은 csv. dialect를 상속받아 새로운 클래스에서 정의해서 새결 가능 

JSON은 웹 브라우저와 다른 애플리케이션이 HTTP 요청으로 데이터를 보낼 때 널리 사용하는 표준파일 형식 중 하나 

파이썬에서는 또한 HTML과 XML 형식의 데이터를 읽고 쓸 수 있는 라이브러리가 무척 많음 

판다스에는 앞서 소개한 라이브러리를 사용해 자동으로 HTML파일을 파싱해 dataframe으로 변환하는 내장 함수 pandas.read_html존재 
### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="475" height="232" alt="image" src="https://github.com/user-attachments/assets/10948c29-dd07-465d-b214-e730cc3a50e2" />

<img width="943" height="251" alt="image" src="https://github.com/user-attachments/assets/6d47916a-730d-4217-a1c4-c273fac7b008" />


## 2. 이진 데이터 형식

### 개념정리

데이터를 이진 형식으로 저장하는 가장 간단한 방법은 파이썬 내장 pickle 모듈 이용하는 것 

pickle 파일은 파이썬에서만 읽을 수 있고 pickle을 통해 파일로 저장된 객체는 파이썬 내장 pickle 모듈로 직접 부러오거나 pandas.read_pickle 함수를 이용해 불러올 수 있음 

판다스는 pandas.excelfile클래스나 pandas.read_excel 함수를 통해 엑셀 2003 이후 버전으로 저장된 표 형식 데이터를 읽을 수 있다. 

HDF5는 대량의 과학 계산용 배열 데이터를 저장하기 위해 고안된 훌륭한 파일 포맷이다. C 라 
이브러리로도 존재하며 자바, 줄리 매트랩, 파이썬 같은 다양한 언어에서도 사용할 수 있 
는 인터페이스를 제공한다. 

HDFStore는 "fixed"와 "table" 두 가지 저장스키마를 지원한다

put은 명시적인 store['obj2，] = frame 메서드지만 저장 형식을 지정하는 등의 다른 옵션 
을 제공한다.
### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="902" height="421" alt="image" src="https://github.com/user-attachments/assets/5e6d9ce2-c0e0-4ded-b6fa-74315df7342f" />
<img width="833" height="416" alt="image" src="https://github.com/user-attachments/assets/3f1b8596-568c-4786-afe3-638f42190564" />



## 3. 웹 API와 함께 사용하기

### 개념정리

데이터 피드를 JSON이나 여타 다른 형식으로 얻을 수 있는 공개 API를 제공하는 웹사이트 
가 많다. 

data의 각 항목은 댓글을 제외한 깃허브 이슈 페이지에서 찾을 수 있는 모든 데이터를 담고 있 
다. 이 data 를 pandas. Data Frame 으로 바로 전딜해 관심이 있는 필드만 따로 추출할 수 있다.
### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="812" height="302" alt="image" src="https://github.com/user-attachments/assets/b51250f7-decb-4c95-86a8-c25fa6269e34" />


## 4. 데이터베이스와 함께 사용하기

### 개념정리

 비즈니스 관점에서 대부분의 데이터가 텍스트 파일이나 엑셀 파일로 저장되기보다 SQL 
기반의 관계형 데이터베이스(SQL 서버, PostgreSQL, MySQL)를 많이 사용하고 있다

대부분의 파이썬 SQL 드라이버는 테이블에서 select 쿼리를 수행하면 튜플 리스트를 반환한다

반환된 튜플 리스트를 DataFrame 생성자에 바로 전달해도 되지만, cursor의 description 
속성에 있는 열 이름을 지정해야 한다. 

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="831" height="713" alt="image" src="https://github.com/user-attachments/assets/b9562dd4-963a-4987-8060-31b0cf18f608" />
<img width="1457" height="107" alt="image" src="https://github.com/user-attachments/assets/b7a150ef-ee20-4aa2-bff8-9f6c11b02ee0" />



## 5. 누락된 데이터 처리하기

### 개념정리

 float64 dtype을 가지는 데이터의 경우 판다스는 실숫값인 NaN으로 
누락된 데이터를 표시한다

isna 메서드는 값이 null인 경우 True를 가지는 불리언 Series를 반환한

분석 애 플리케이션에서 NA 데이터는 데이터가 존재하지 않거나, 존재하더라도 데이터를 수집하는 과 
정 등에서 검출되지 않았음을 의미한다. 
. pandas.isna 같은 함수에서는 여러 번거로운 과정을 추상화해두었다. 
### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="818" height="258" alt="image" src="https://github.com/user-attachments/assets/7d4802dd-f8fb-48ef-ae58-d4eb657cd139" />

<img width="912" height="207" alt="image" src="https://github.com/user-attachments/assets/af623630-d60d-4759-aea5-ae6f24a61a6c" />


## 6. 데이터 변형 

### 개념정리

DataFrame의 duplicated 메서드는 각 행이 중복인지 아닌지를 알려주는 불리언 Series 객 
체를 반환한다
duplicated와 drop-duplicates는 기본적으로 처음 발견된 값을 유지한다. keep="last" 
옵션을 넘기면 마지막으로 발견된 값을 반환한다.
fiUna 메서드로 누락된 값을 채우는 작업은 일반적인 값 치환 작업이라고 볼 수 있다. 한 객체 안에서 값의 부분집합을 변경하는 데 map 메서드를 사용했지만, replace 메 
서드는 동일한 작업을 더 간단하고 유연한 방식으로 제공한다. 

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->



<img width="718" height="378" alt="image" src="https://github.com/user-attachments/assets/0c89c555-1910-4a6b-98c8-1a2f8c809570" />
<img width="381" height="225" alt="image" src="https://github.com/user-attachments/assets/4fb4dd3a-e2ee-4abf-9265-ab401a41be80" />


# 2️⃣ 실습 과제

각 문제에 대한 실행 결과가 확인되도록 코드를 작성하고 실행한 뒤, **모든 문제의 실행 화면을 캡처하여 제출하시기 바랍니다.**

**1. 아래 코드를 실행하여 텍스트와 데이터를 선언합니다.**
```python
import pandas as pd
import json
import requests

# 1. 테스트용 CSV 내용 (메모리 내 시뮬레이션용)
csv_data = "id,name,score,note\n1,Kim,85,NA\n2,Lee,NULL,Good\n3,Park,90,None"
with open("test_data.csv", "w") as f:
    f.write(csv_data)

# 2. 테스트용 JSON 문자열
json_obj = """
{
    "company": "DataService",
    "employees": [
        {"name": "Alice", "age": 30, "dept": "IT"},
        {"name": "Bob", "age": 25, "dept": "HR"}
    ]
}
"""
```

**2. 문제**
```
1. CSV 파일 읽기 및 결측치 지정
  - 문제 설명: 제공받은 test_data.csv 파일을 읽어오기(단, 데이터의 특성에 맞게 옵션 설정)
  - read_csv()를 사용하여 파일을 읽으세요.
  - 이때 NA, NULL, None이라는 문자열을 모두 **결측치(NaN)**로 인식하도록 na_values 옵션을 설정하세요.
  - print()를 이용해 읽어온 DataFrame을 출력하세요.

2. JSON 데이터 변환 및 특정 데이터 추출
  - 문제 설명: 문자열 형태의 JSON 데이터를 파싱하여 직원 명단만 추출
  - json.loads()를 사용하여 json_obj 문자열을 파이썬 객체로 변환하세요.
  - 변환된 객체에서 employees 리스트만 추출하여 DataFrame으로 만드세요.
  - print()를 이용해 생성된 직원 명단 DataFrame을 출력하세요.

3. 웹 API 데이터 가져오기
  - 문제 설명: 판다스 깃허브 저장소의 이슈(Issues) 데이터를 가져와 상위 항목 확인
  - requests.get()을 사용하여 https://api.github.com/repos/pandas-dev/pandas/issues URL의 데이터를 가져오세요.
  - 응답받은 JSON 데이터를 DataFrame으로 변환하세요.
  - print()를 이용해 데이터의 상단 5행(head)을 출력하세요.
```

<img width="1831" height="496" alt="image" src="https://github.com/user-attachments/assets/5a5d0232-85de-4e61-9759-de26722960e7" />




### 🎉 수고하셨습니다.






