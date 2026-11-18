# 📚 Software Development Naming & Terminology Guide

> 상황별 사용하는 권장 업무 용어, 파일명·화면 문구·DB 식별자의 영어 표현 개인 가이드

-   **Document type:** Naming & Terminology Standard
-   **Language:** Korean / English
-   **Scope:** Business terminology, UI labels, file names, database
    identifiers, and organizational hierarchy
-   **Status:** Working draft


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


## 2. 조직 및 계층 구조 용어

조직의 본사·지사인지, 데이터 목록의 최상위 항목인지, 조직도상의 상위 부서인지에 따라 표현 구분

### 2.1 본사 및 지사

|  한국어         |         권장 영어        |  설명 |
|:---|:---:|---:|
| 본사            |     `Head Office`       |     일반적인 본사 표현 |
| 본사 / 기업 본부   |     `Corporate HQ`  |    기업 차원의 본부 또는 총괄 조직 강조 |
| 본사 사무실  |  `Head Office` / `Corporate Office`  |  조직의 본사 사무소  |              
| 지사     |     `Branch Office`    |     본사 아래의 지점 또는 지사 |
| 건축 회사 본사      |    `Architecture Firm HQ`  |    건축 회사의 본사라는 의미를 명확히 표현 |
| 건축 회사 본점     |  `Architecture Firm Head Office` |  공식 조직·주소·사업장 분류에 적합 |


**표현 선택 참고**

-   일반적인 회사 조직에서는 `Head Office`가 무난
-   기업 전체의 전략·경영을 총괄하는 본부를 강조할 때는 `Corporate HQ` 
-   건축 회사라는 업종을 명시해야 한다면 `Architecture Firm HQ`가 좀더 명확
-   일반 문장이나 문서에서는 `Headquarters`, 짧은 라벨이나 식별자에서는 `HQ`

### 2.2 목록(List)의 종류

  -----------------------------------------------------------------------
  한국어 / 개념           권장 영어               사용 맥락
  ----------------------- ----------------------- -----------------------
  본사 목록               `Head Office List` /    본사 조직 또는 사업장
                          `HQ List`               목록

  최상위 목록             `Root List`             트리 구조에서 최상위
                                                  노드 목록

  기준 목록               `Master List`           다른 데이터가 참조하는
                                                  기준 목록

  드롭다운 목록           `Drop-down List`        UI에서 사용자가
                                                  선택하는 목록

  전체 목록               `Complete List` /       누락 없이 전체 항목을
                          `Full List`             보여주는 목록
  -----------------------------------------------------------------------

**주의:** `Root List`, `Master List`, `HQ List`는 서로 대체할 수 있는
표현이 아닙니다. `HQ List`는 본사 관련 목록이고, `Root List`는 계층
구조의 최상위 목록이며, `Master List`는 기준 데이터 목록

### 2.3 부서 계층 및 상위·하위 관계

  ------------------------------------------------------------------------
  한국어                  권장 영어                비고
  ----------------------- ------------------------ -----------------------
  상위 부서               `Parent Department`      계층 구조에서 부모 부서

  하위 부서               `Child Department` /     상위 부서 아래의 부서
                          `Sub-department`         

  상위 부서 코드          `PARENT_DEPT_CODE`       부모 부서 식별 코드

  하위 부서 코드          `CHILD_DEPT_CODE`        자식 부서 식별 코드

  상위 부서명             `PARENT_DEPT_NAME`       부모 부서명

  최상위 부서             `ROOT_DEPARTMENT`        조직 트리의 루트 부서

  부서 계층               `Department Hierarchy`   부서 간 계층 구조
  ------------------------------------------------------------------------

`PARENT_DEPT_CODE`는 Parent-Child 트리 구조를 표현하는 일반적인 이름

`UPPER DEPT`는 일부 국내 SI 현장에서 사용, 영어권에서는 `PARENT_DEPT` 권장

------------------------------------------------------------------------

## 3. 업체 및 회원 가입·탈퇴 용어

가입과 탈퇴는 대상이 개인 회원인지, 입점 업체인지, 공급업체인지에 따라 적합한 주어 선택

### 3.1 대상 용어 선택

  용어         의미                  적합한 맥락
  ------------ --------------------- ---------------------------------
  `Member`     회원                  일반적인 서비스 회원
  `Partner`    파트너 / 제휴 업체    협력사, 제휴사, 파트너사
  `Vendor`     공급업체 / 판매업체   상품·서비스 공급자, 입점 판매자
  `Business`   사업체                업체 일반을 포괄하는 표현
  `Account`    계정                  로그인 및 시스템 접근 단위

- 일반적인 입점 업체라면 `Partner` 또는 `Vendor`
- 계약상 협력 관계를 강조하면 `Partner`, 상품·서비스 공급 역할을 강조하면 `Vendor`

### 3.2 업체 탈퇴 승인

#### 권장 표현

  용도                         권장 영어
  ---------------------------- -------------------------------------
  업체 탈퇴 승인               `Partner Withdrawal Approval`
  업체 탈퇴 승인 목록 / 파일   `Partner-Withdrawal-Approvals.xlsx`
  승인된 업체 탈퇴 목록        `Approved-Partner-Withdrawals.xlsx`
  회원 탈퇴 승인               `Membership Withdrawal Approval`
  공급업체 계정 삭제 승인      `Vendor Account Deletion Approval`

#### 파일명 차이

  -----------------------------------------------------------------------
  파일명                              의미
  ----------------------------------- -----------------------------------
  `Partner-Withdrawal-Approvals.*`    업체 탈퇴 승인 건 또는 승인 업무
                                      목록
  `Approved-Partner-Withdrawals.*`    탈퇴가 승인된 업체 또는 탈퇴 건의
                                      목록
  -----------------------------------------------------------------------

#### UI 버튼 / 액션

-   `Approve Withdrawal`
-   `Approve Account Deletion`

#### 사용자 알림 / 상태 문구

-   `Membership Withdrawal Approved` --- 회원 탈퇴가 승인됨
-   `Account Closure Confirmed` --- 계정 폐쇄가 확인됨
-   `Cancellation Approved` --- 계약·서비스 등의 취소가 승인됨

**Withdrawal / Deletion / Closure 구분**

-   `Withdrawal`: 회원이나 업체가 관계 또는 가입 상태에서 탈퇴하는 행위
-   `Deletion`: 계정 또는 데이터를 시스템에서 삭제하는 행위
-   `Closure`: 계정이나 서비스 이용 관계를 종료하는 행위

단순히 서비스에서 탈퇴하는 것과 개인정보·계정 데이터를 실제 삭제하는
것은 다를 수 있으므로, 실제 처리 정책에 맞춰 영어 선택

### 3.3 업체 가입 승인

#### 권장 표현

  용도                         권장 영어
  ---------------------------- ---------------------------------------
  업체 등록 승인               `Partner Registration Approval`
  업체 등록 승인 목록 / 파일   `Partner-Registration-Approvals.xlsx`
  승인된 업체 등록 목록        `Approved-Partner-Registrations.xlsx`
  신규 업체 온보딩 목록        `Partner-Onboarding-List.xlsx`
  신규 승인 업체 목록          `Approved-New-Partners.xlsx`

#### 표현 차이

-   `Registration`: 회원·업체 정보를 등록하는 절차에 초점
-   `Onboarding`: 등록 이후 초기 설정, 계약, 교육, 시스템 이용 준비까지
    포함하는 온보딩 과정
-   `Approval`: 등록 또는 가입 요청을 검토하고 승인하는 행위
-   `Approved`: 승인 완료 상태

단순 업체 가입 신청 및 승인 업무에는
`Partner Registration Approval`을, 
계약·계정 설정 등 초기 정착 절차까지 관리한다면 `Partner Onboarding` 권장

------------------------------------------------------------------------

## 4. 이전 / 현재 상태 및 구분 코드

상태 변화나 프로세스 단계에서 '이전'을 표현할 때는 일반적으로 `Previous`가 `Before`보다 적절

### 4.1 Previous vs. Before

  -----------------------------------------------------------------------
  표현                    의미                    적합성
  ----------------------- ----------------------- -----------------------
  `Previous`              이전의, 바로 앞선       이전 상태·단계·값을
                                                  나타내는 명사 수식에
                                                  적합

  `Before`                \~전에, 이전에          시간이나 사건의 선후
                                                  관계를 설명할 때 적합
  -----------------------------------------------------------------------

예를 들어 DB 컬럼명에서는 `PREVIOUS_STATUS_CODE`가 `BEFORE_STATUS_CODE`보다 자연스러움

### 4.2 권장 네이밍

  --------------------------------------------------------------------------
  의미                    권장 컬럼명                설명
  ----------------------- -------------------------- -----------------------
  이전 상태 코드          `PREVIOUS_STATUS_CODE`     상태 변경 전 코드

  현재 상태 코드          `CURRENT_STATUS_CODE`      현재 적용 중인 상태
                                                     코드

  이전 단계 코드          `PREVIOUS_STAGE_CODE`      프로세스의 이전 단계

  현재 단계 코드          `CURRENT_STAGE_CODE`       프로세스의 현재 단계

  이전 카테고리 코드      `PREVIOUS_CATEGORY_CODE`   변경 전 카테고리

  현재 카테고리 코드      `CURRENT_CATEGORY_CODE`    현재 카테고리

  이전 프로세스 코드      `PREVIOUS_PROCESS_CODE`    변경 전 프로세스 구분
                                                     코드
  --------------------------------------------------------------------------

### 4.3 약어 사용

  전체 표현    약어 예시
  ------------ -----------
  `PREVIOUS`   `PREV`
  `CURRENT`    `CURR`

약어는 컬럼 길이 제한이나 기존 시스템 규칙이 있을 때 사용

-   `PREV_STATUS_CODE`
-   `CURR_STATUS_CODE`


## 5. 빠른 선택 가이드

  -------------------------------------------------------------------------------------
  상황                    우선 추천 표현                    피하거나 주의할 표현
  ----------------------- --------------------------------- ---------------------------
  회사 본사               `Head Office`                     맥락 없는 `Root Office`

  기업 총괄 본부          `Corporate HQ`                    `Master Office`

  건축 회사 본사          `Architecture Firm HQ`            모호한 `Architecture HQ`

  본사 목록               `HQ List`                         `Root List`

  트리 최상위 목록        `Root List`                       `HQ List`

  기준 데이터 목록        `Master List`                     `Drop-down List`

  UI 선택 목록            `Drop-down List`                  `Master List`

  상위 부서               `Parent Department`               `Upper Department`

  상위 부서 코드          `PARENT_DEPT_CODE`                `UPPER_DEPT_CODE`

  업체 탈퇴 승인          `Partner Withdrawal Approval`     문맥 없는 `Partner Delete`

  계정 삭제 승인          `Account Deletion Approval`       `Membership Withdrawal`과
                                                            혼용

  업체 등록 승인          `Partner Registration Approval`   의미가 불분명한
                                                            `Partner Join`

  이전 상태 코드          `PREVIOUS_STATUS_CODE`            `BEFORE_STATUS_CODE`

  현재 상태 코드          `CURRENT_STATUS_CODE`             `NOW_STATUS_CODE`
  -------------------------------------------------------------------------------------


## 6. 네이밍 체크리스트

새로운 영문 용어 또는 식별자를 정할 때 다음 항목 확인

-   [ ] 실제 업무 의미를 정확하게 표현하는가?
-   [ ] 개인 회원, 파트너, 공급업체, 계정의 대상을 구분했는가?
-   [ ] 행위(Action)와 상태(Status)를 구분했는가?
-   [ ] 등록(Registration), 온보딩(Onboarding), 탈퇴(Withdrawal),
    삭제(Deletion)의 의미를 구분했는가?
-   [ ] 조직 계층에서 Parent / Child / Root 관계를 일관되게 사용했는가?
-   [ ] 기존 테이블·컬럼·API 및 화면 용어와 충돌하지 않는가?
-   [ ] 프로젝트의 대소문자, 구분자, 약어 규칙을 따르는가?

------------------------------------------------------------------------



*Consistent naming makes software easier to understand, maintain, and
evolve.*
