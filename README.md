# 해외축구 선수 몸값 분석

2023년 1학기 경희대학교 **웹/파이썬프로그래밍(SWCON10401)** 텀프로젝트입니다. 해외축구 선수의 몸값(시장가치)이 포지션·나이·골 수와 어떤 관계가 있는지 데이터로 분석했습니다.

## 데이터

- 출처: [Transfermarkt](https://www.transfermarkt.com/) 시장가치 상위 선수 목록
- `requests`와 `BeautifulSoup`으로 상위 300명의 이름, 포지션, 나이, 시장가치, 경기 수, 골 수를 크롤링해 `player_info.xlsx`로 저장했습니다.

## 가설과 결과

| 가설 | 분석 | 결과 |
|---|---|---|
| 1. 공격수의 몸값이 가장 비싸다 | 포지션별 boxplot | 공격수의 중앙값·3사분위·이상치가 모두 높아 대체로 맞음 |
| 2. 나이가 어릴수록 몸값이 비싸다 | 나이대 5개 그룹(~20, 21–24, 25–28, 29–31, 32~)의 평균 | 21–24세가 가장 높고 32세 이상이 가장 낮음. 단, 29–31세가 25–28세보다 높아 엄밀한 반비례는 아님 |
| 3. 골을 많이 넣은 공격수일수록 몸값이 비싸다 | 골 수 vs 몸값 산점도 | 0–15골 구간에서는 대체로 비례하지만 20–30골인데도 몸값이 낮은 선수가 있음 |

## 파일

- `term project_report.ipynb`: 크롤링부터 시각화, 결론까지 담은 보고서 노트북
- `player_info.xlsx`: 수집한 선수 데이터

```bash
pip install pandas matplotlib openpyxl requests beautifulsoup4
jupyter notebook "term project_report.ipynb"
```
