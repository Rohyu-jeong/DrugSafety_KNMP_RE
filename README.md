# 의약품 안전나라 자동화 프로그램

> **의약품 안전나라 행정 처분 데이터를 수집하여 조건별로 분류·가공하고, 결과를 Excel로 저장한 후 메일로 전송하는 자동화 프로그램입니다.**

<br>

## 기술 환경

- UiPath Studio
- Robotic Enterprise Framework (REFramework)
- Excel, Web Automation
- HTML Email, DataTable, Dictionary 등 활용

<br>

## 자동화 흐름 요약

1. 메일 수신 후 검색어, 검색 기간, 시트 명 기준이 되는 날짜 정보 추출
2. 의약품 안전나라 사이트 접속 후 행정 처분 정보 카테고리 진입
3. ‘의약품’ 항목의 현재 처분 정보 내 행정 처분 데이터를 검색
4. 검색 결과 전체 데이터를 추출하여 Excel 시트에 저장
5. 처분 내용 텍스트 내에서 필터 키워드 포함 여부로 필터링하여 별도 시트 저장
6. 필터링된 데이터를 처리일자(월일/응답) 항목 기준으로 분리 저장
7. (선택) 필터링된 시트를 기준으로 오류사유 정렬하여 메일 본문용 테이블 작성
8. 메일 본문 작성 후 첨부 파일과 함께 자동 발송

<br>

## Workflow 구성

- **Initialization** <br>
  00\_폴더 초기화.xaml <br>
  01\_메일 수신.xaml <br>
  02\_결과 파일 저장.xaml <br>
  03_TransactionDT 생성.xaml <br>
  04\_초기 DT 생성.xaml <br>

- **Process Transaction** <br>
  05\_상세 정보 DT 추출.xaml <br>
  06_DT 가공.xaml <br>

- **End Process** <br>
  07_DT 저장.xaml <br>
  08\_메일 발송.xaml <br>
