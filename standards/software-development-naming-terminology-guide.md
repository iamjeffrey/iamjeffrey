# 📚 Software Development Naming & Terminology Guide

> 상황별 사용하는 권장 업무 용어, 파일명·화면 문구·DB 식별자의 영어 표현 개인 가이드

-   **Document type:** Naming & Terminology Standard
-   **Language:** Korean / English
-   **Scope:** Business terminology, UI labels, file names, database
    identifiers, and organizational hierarchy
-   **Status:** Working draft

------------------------------------------------------------------------

## 1. 목적과 적용 원칙
소프트웨어 개발 및 업무 시스템에서 의미가 좀더 적절한 영어 표현을 선택하기 위한 개인 목적

### 1.1 기본 원칙

1.  **의미 우선:** 개인적으로 필요한 영문 네이밍 및 업무상 용어 우선
2.  **대상 명확화:** Member, Partner, Vendor, Account처럼 대상의 성격 구분
3.  **상태와 행위 구분:** 승인 행위(`Approve`)와 승인된 상태(`Approved`) 구분
4.  **명사형 우선:** 파일명과 데이터 항목에는 일반적으로 명사형 사용
5.  **일관성 유지:** 같은 도메인에서는 동일한 개념에 동일한 용어 사용
6.  **식별자 규칙 준수:** DB 컬럼과 코드에서는 프로젝트의 기존 대소문자 및 구분자 규칙 준수

### 1.2 사용 위치별 네이밍 기준
| 사용 위치 | 권장 형태 | 예시 |
|:---|:---|:---:|
| UI 버튼 / 액션 |  동사 중심                 |  `Approve Withdrawal` |
| UI 상태 / 알림 |  상태를 나타내는 문구         |  `Withdrawal Approved` |
| 파일명         | 명사 중심                  |  `Partner-Withdrawal-Approvals.xlsx` |
| DB 컬럼       |  의미가 명확한 명사구         |  `PREVIOUS_STATUS_CODE` |
| 코드 변수      |  프로젝트 규칙에 따른 camelCase 등 |  `previousStatusCode` |
| 조직 계층      |  Parent / Child 관계       | `PARENT_DEPT_CODE` |
