<h1>데이터 분석 입문 기초 명령어 </h1>

```py
import matplotlib.pyplot as plt #맷플롯라이브러리 꺼내오기 + 별칭 지정
import csv #csv 파일 읽기
import numpy as np #넘파이 꺼내오기 + 별칭 지정

f = open('자료','r') #자료 불러오기 읽기 전용
data = (csv.reader(f)) #데이터라는 변수에 csv 파일 지정
header = next(data) #csv 파일의 첫번째 행 넘기기
```
<h1>Numpy 명령어</h1>
변수 = np.array(리스트 범위, dtype = 자료형) = 자료형 변경
변수 = np.sum(리스트 (연산부호) 리스트)
np.sqrt(x) = x의 제곱근

<h1>matplotlib.pyplot 명령어</h1>

```py
plt.plot(y값) = 선그래프 표시
    bar(x값, y값) = 바그래프 표시
    barh(x값, y값) = 가로로 바 그래프 표시
    pie(data, label, ,autopct, color, startangle) = 파이 그래프

# pie 그래프 >> label = [], autopct = '%.2f%%', colors= [] 형식이며, 리스트는 새로 리스트를 만들어서 값을 넣어줘야함
# 바 그래프의 가로 표현 시 리스트에 음수값이 있다면 반대쪽으로 표현 가능 (양쪽으로 표현해야할 시 리스트 2개 생성)
# 각각 그래프 구조 뒤에 color, label, marker(='d') 등 입력 가능

plt.rc('font', family='Malgun Gothic') = 폰트 지정
    rcParams['axes.unicode_minus'] = False = 유니코드 사용시 '-' 부호 표현

# 한국어 사용에 필수

plt.title('제목')
    xlabel('x축 이름')
    ylabel('y축 이름')
    
# 이름 지정

plt.legend() = 그래프에서 지정한 라벨 표시
    grid() = 그리드 표시
    show() = 그래프 표시
    figure(figsize = (가로비율, 세로비율)) = 그래프 비율 조정
```

<h1> 기타 명령어 </h1>

- list.replace('제거하고자 하는 글자','바꿀 글자')
- list.split('나눌 기준 글자')[나눠진 이후 위치]
- 
