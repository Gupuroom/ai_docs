# 웹파트 AI 툴 활용 사례

## 1️⃣ 신규 프로젝트 개발: CRUD 

### 작업 개요
데이터베이스 스키마를 기반으로 Entity 클래스 및 CRUD 코드 생성

### 기존 작업 방식
- ERD 문서를 참조하여 수동으로 Entity 클래스 작성
  
  <img src="https://github.com/user-attachments/assets/d914461d-7a12-4544-a2d4-29feda6f8513" alt="캡처1" width="60%">

- 테이블별 CRUD 코드 개별 구현
  
### ✅AI 툴 활용 방식 (Claude + MCP)
#### 1. MCP(Model Context Protocol)를 통한 개발 서버 DB 연동
<img src="https://github.com/user-attachments/assets/a85b88a5-644f-42a0-92ba-1cc39e399e62" alt="캡처1" width="80%">

#### 2. MCP를 통한 데이터베이스 테이블 구조 조회 요청
<img src="https://github.com/user-attachments/assets/b1330671-bf10-4239-bf2e-9971786f1f2a" alt="캡처1" width="80%">
<img src="https://github.com/user-attachments/assets/627430fc-af76-4d67-a6cd-637cdbf830cc" alt="캡처1" width="80%">

#### 3. 테이블 스키마 기반 Entity 클래스 자동 생성 요청
<img src="https://github.com/user-attachments/assets/66f3ed23-aa07-42f1-bf56-a5b5830faa99" alt="캡처1" width="80%">

#### 4. Entity 기반 요구사항 설명 및 고려할 점 리스트 확인
<img src="https://github.com/user-attachments/assets/5c36f3b2-d59a-4cc5-9563-3a1dbdb681a1" alt="캡처1" width="80%">

#### 5. 코드 생성
<img src="https://github.com/user-attachments/assets/ea9685ad-f66e-49aa-9d71-1467ec80b17f" alt="캡처1" width="80%">


### 개선 효과
- **소요 시간**: 기존 1일 → 1-2시간
- 데이터베이스 직접 연동으로 실시간 스키마 정보 기반 정확한 Entity 생성
- 수동 코딩 시 발생하는 오타나 필드 누락 없이 완전한 코드 생성 가능
- 반복적인 보일러플레이트 코드 작성에서 해방되어 핵심 비즈니스 로직 개발에 집중 가능

## 2️⃣ 단순 작업 최적화: Placeholder 일괄 추가

### 작업 개요
nBlock 관리웹 모든 HTML 파일의 input 및 textarea 요소에 placeholder 추가

### 기존 작업 방식
- 각 화면을 수동으로 확인하며 Ctrl+F로 input 요소 검색
- 파일별로 개별 수정 작업 진행
- **소요 시간**: 3 ~ 4시간 예상
- **주요 문제점**: 
  - 파일이 산개되어 있어 누락 가능성 존재

### ✅ AI 툴 활용 방식 (Cursor)
#### 1. `/templates` 폴더 내 모든 파일에서 input, textarea 요소 검색 요청
<img src="https://github.com/user-attachments/assets/70469bc3-4bd9-4dff-a47c-1f4e03db9951" alt="캡처1" width="80%">

#### 2. 해당 요소가 포함된 파일 목록 추출 요청 (데이터 양 과다로 인한 처리 한계 확인)
<img src="https://github.com/user-attachments/assets/aba56bbe-0df7-4789-a184-35864337b323" alt="캡처1" width="80%">

#### 3. 파일별 placeholder 적용 요청
<img src="https://github.com/user-attachments/assets/37ac8ab0-cf47-4ff2-8592-e436fb544eda" alt="캡처1" width="80%">

#### 4. Git diff를 통한 변경사항 검토 및 개발 완료

### 개선 효과
- **소요 시간**: 대략 3 - 4시간 → 30분
- 수동 작업 시 발생할 수 있는 누락이나 오타 없이 일관성 있는 결과
- AI가 각 입력 필드에 적합한 placeholder 문구를 자동 생성하여 별도 고민 불필요
---

## 3️⃣ 테스트 데이터 생성 최적화: Claude + DB 연동

### 작업 개요
개발 및 QA 환경에 필요한 대량 테스트 데이터를 실제 DB 스키마 기반으로 자동 생성

### 기존 작업 방식
- 개발자가 수동으로 INSERT 쿼리 작성
- 실제 데이터와 유사한 더미 데이터 고민하며 생성
- 테이블 간 관계(FK) 고려하여 순서대로 데이터 입력
- **예상 소요 시간**: 1시간 (테이블 10개 기준)
- **주요 문제점**:
  - 제약조건 위반으로 인한 오류 발생
  - 비현실적인 테스트 데이터로 인한 QA 품질 저하
  - 관계 테이블 순서 고려로 인한 복잡성

### ✅ AI 툴 활용 방식 (Claude + DB 연동)

#### 1. 데이터베이스 스키마 정보 자동 분석
- Claude가 자동으로 테이블 구조와 외래키 관계 파악

#### 2. 비즈니스 로직에 맞는 현실적인 테스트 데이터 생성 요청
- "Group 20개, 각각 User 100개를 가지게 테스트 데이터 생성해줘"

<img src="https://github.com/user-attachments/assets/fee9badc-ffb3-4cca-ac00-b04d7ad4a847" alt="캡처1" width="80%">

#### 3. 관계 무결성을 고려한 순차적 데이터 생성
Claude가 자동으로:
- 부모 테이블 → 자식 테이블 순서 결정
- 외래키 제약조건 준수
- 각 테이블별 적절한 데이터 타입과 범위 적용
<img src="https://github.com/user-attachments/assets/219e487e-9a95-4baa-af21-902dfdcc63fd" alt="캡처1" width="80%">

#### 4. INSERT 쿼리 실행
외래키 관계 무결성을 보장하며 대량 데이터 생성
<img src="https://github.com/user-attachments/assets/2199a9e4-2743-4818-af30-a5029b040a21" alt="캡처1" width="80%">
<img src="https://github.com/user-attachments/assets/c439c8d7-8010-4588-9ad0-87ef8dfd7e08" alt="캡처1" width="80%">


### 개선 효과
- **소요 시간**: 기존 1시간 → 5-10분
- 실제 DB 스키마 기반으로 정확한 데이터 타입과 제약조건 준수
- 비즈니스 로직을 반영한 현실적인 테스트 데이터로 QA 품질 향상
- 외래키 관계 자동 분석으로 데이터 무결성 보장
- 대량 데이터 생성 시에도 일관된 품질 유지

