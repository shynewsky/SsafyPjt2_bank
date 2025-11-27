# 📈 넷플릭스 주가 데이터 분석

본 프로젝트는 Pandas, NumPy, Matplotlib을 활용하여 넷플릭스(NFLX)의 주가 데이터를 시계열로 분석하고 시각화하는 과정을 다룹니다.

## 🛠️ 설치 환경

```bash
pip install numpy
pip install pandas
pip install matplotlib
```

## 📂 데이터 불러오기 (F01)

- `pandas.read_csv()`를 이용해 `./NFLX.csv` 파일을 불러옵니다.
- 주요 컬럼(`Date`, `Open`, `High`, `Low`, `Close`)만 추출합니다.
- `loc[]`: 열 기준 인덱싱, `iloc[]`: 행 기준 인덱싱.

## 🗓️ 2021년 이후 종가 시각화 (F02)

- 2021년 1월 1일 이후의 데이터를 필터링.
- `pd.to_datetime()`을 통해 날짜 포맷을 변환.
- `Close` 종가의 변화 추이를 `matplotlib.pyplot.plot()`으로 시각화.

```python
plt.plot(x, y)
plt.title('NFLX Close Price')
plt.xlabel('Date')
plt.ylabel('Close Price')
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

## 🔺 최고가와 최저가 계산 (F03)

- `max()`, `min()` 메서드를 사용해 종가(Close)의 최대/최소값을 출력.

```python
print("최고 종가:", max_price)
print("최저 종가:", min_price)
```

## 📊 월별 평균 종가 분석 (F04)

- `dt.to_period('M')`로 월 단위 데이터 생성.
- `groupby()` + `mean()`을 이용해 월별 평균 종가 계산.
- 시각화 시 `Month`는 `datetime` 형식으로 변환하여 사용.

```python
plt.plot(month_avg['Month'], month_avg['Close'])
plt.title('Monthly Average Close Price')
plt.xlabel('Date')
plt.ylabel('Average Close Price')
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

## 📉 2022년 이후 고가/저가/종가 시각화 (F05)

- 2022년 1월 이후의 데이터를 필터링.
- `High`, `Low`, `Close` 데이터를 동시에 선 그래프로 출력.
- `legend()`를 통해 범례를 표시하여 비교 가능.

```python
plt.plot(x, y1, label='High')
plt.plot(x, y2, label='Low')
plt.plot(x, y3, label='Close')
plt.legend()
plt.title('High, Low, and Close Prices since January 2022')
plt.xlabel('Date')
plt.ylabel('Price')
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

---

```html

```