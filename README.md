# 🗂 BASE DB Tracker

> BASE DB시점별 DATA 누적 빌드 & 추적 도구
---
> DATA종류: ①TEMP Rule ②TT ③9cell ④Stream

**Live Site**: https://one1peace.github.io/BASE_DB_Tracker

---

## 📌 개요

Base DB가 Revision마다 달라지는 환경에서, **시점별 DATA 누적 이력을 관리**하기 위한 웹 도구입니다.

- Excel history 데이터를 붙여넣기만 하면 즉시 사용 가능
- 서버 불필요. 순수 HTML 단일 파일
- BASE 그룹 기준으로 TEMP rule 누적 빌드

---

## 🚀 기능

| 탭 | 기능 |
|---|---|
| 📅 Rev 타임라인 | Rev별 BASE / TEMP 적용 현황 테이블 |
| 🔎 Rule 추적 | 특정 TEMP rule이 어떤 Rev에 걸쳐 적용됐는지 시각적 타임라인 |
| ⚙️ 누적 빌드 | 선택한 Rev 시점까지 BASE가 같은 Rev의 rule을 자동 누적 |
update 예정항목
▶ Truth Table
▶ 9cell
---

## 📋 데이터 형식

Excel에서 아래 컬럼 구조로 복사 후 붙여넣기:

```
Rev번호	날짜	TEMP 적용	TEMP 내용	BASE
R03	260103	TEMP03_DR	DC max_length 예외	R03
R04	260303	TEMP03_DR+TEMP04_DR	DC max_length 예외+GP max_length 예외	R03+R04
R05	260503	TEMP03_DR+TEMP05_DR	DC max_length 예외+IIP overlap 예외	R03+R05
```

- 복수 TEMP rule은 `+` 로 구분
- BASE도 `+` 로 복수 기재 가능

---

## 🛠 로컬 실행

```bash
git clone https://github.com/MTO/temp-rule-tracker.git
cd temp-rule-tracker
# index.html을 브라우저로 열기 (서버 불필요)
open index.html
```

---

## 📁 구조

```
temp-rule-tracker/
├── index.html   # 앱 전체 (단일 파일)
├── README.md
└── LICENSE
```

---

## 📄 License

MIT License — 자유롭게 사용, 수정, 배포 가능
