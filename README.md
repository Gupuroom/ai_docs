# 웹파트 AI 툴 활용 사례

## 1️⃣ 신규 프로젝트 개발: 자동화된 코드 생성

### 작업 개요
데이터베이스 스키마를 기반으로 Entity 클래스 및 CRUD 코드 생성

### 기존 작업 방식
- ERD 문서를 참조하여 수동으로 Entity 클래스 작성
- 테이블별 CRUD 코드 개별 구현
- 패키지 구조 수동 설계

### ✅AI 툴 활용 방식 (Claude + MCP)
#### 1. MCP(Model Context Protocol)를 통한 개발 서버 DB 연동
<img src="https://github.com/user-attachments/assets/a85b88a5-644f-42a0-92ba-1cc39e399e62" alt="캡처1" width="60%">

#### 2. MCP를 통한 데이터베이스 테이블 구조 조회 요청
<img src="https://github.com/user-attachments/assets/b1330671-bf10-4239-bf2e-9971786f1f2a" alt="캡처1" width="60%">
<img src="https://github.com/user-attachments/assets/627430fc-af76-4d67-a6cd-637cdbf830cc" alt="캡처1" width="60%">

#### 3. 테이블 스키마 기반 Entity 클래스 자동 생성 요청
<img src="https://github.com/user-attachments/assets/66f3ed23-aa07-42f1-bf56-a5b5830faa99" alt="캡처1" width="80%">

#### 4. Entity 기반 요구사항 설명 및 고려할 점 리스트 확인
<img src="https://github.com/user-attachments/assets/5c36f3b2-d59a-4cc5-9563-3a1dbdb681a1" alt="캡처1" width="60%">

#### 5. 코드 생성
<img src="https://github.com/user-attachments/assets/ea9685ad-f66e-49aa-9d71-1467ec80b17f" alt="캡처1" width="80%">


### 개선 효과
- **소요 시간**: 기존 2-3일 → 1-2시간
- 데이터베이스 직접 연동으로 실시간 스키마 정보 기반 정확한 Entity 생성
- 수동 코딩 시 발생하는 오타나 필드 누락 없이 완전한 CRUD 코드 자동 생성
- AI가 테이블 관계와 비즈니스 로직을 분석하여 적절한 패키지 구조 및 코드 패턴 제안
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
  - 기존 코드와 JavaScript 연동 확인으로 인한 시간 소모

### ✅ AI 툴 활용 방식 (Cursor)
#### 1. `/templates` 폴더 내 모든 파일에서 input, textarea 요소 검색 요청
<img src="https://github.com/user-attachments/assets/70469bc3-4bd9-4dff-a47c-1f4e03db9951" alt="캡처1" width="60%">

#### 2. 해당 요소가 포함된 파일 목록 추출 요청 (데이터 양 과다로 인한 처리 한계 확인)
<img src="https://github.com/user-attachments/assets/aba56bbe-0df7-4789-a184-35864337b323" alt="캡처1" width="60%">

#### 3. 파일별 placeholder 적용 요청
<img src="https://github.com/user-attachments/assets/37ac8ab0-cf47-4ff2-8592-e436fb544eda" alt="캡처1" width="60%">

#### 4. Git diff를 통한 변경사항 검토 및 개발 완료

### 개선 효과
- **소요 시간**: 대략 2시간 → 10분
- 수동 작업 시 발생할 수 있는 누락이나 오타 없이 일관성 있는 결과
- AI가 각 입력 필드에 적합한 placeholder 문구를 자동 생성하여 별도 고민 불필요
---

## 3️⃣ 시스템 버전 업그레이드: Tomcat 버전 업데이트

### 작업 개요
- Tomcat 버전 업그레이드 

### 기존 작업 방식
- 공식 문서를 통한 수동 분석
- 실제 프로그램 구동을 통한 반복 테스트
- **주요 문제점**: 
  - 모든 사이드 이펙트를 사전에 예측하기 어려움
  - 테스트 과정에서 상당한 시간 소모

### ✅ AI 툴 활용 방식 (Claude)
#### 1. 버전 업그레이드 시 고려사항 리스트업 요청
<img src="https://github.com/user-attachments/assets/f88bb6db-e6ca-4f2e-bb84-8a5e3bf4f619" alt="캡처1" width="60%">

#### 2. 기존 설정 파일 공유 및 분석 요청
<img src="https://github.com/user-attachments/assets/0adfa336-c1df-4e0f-9a73-4c6c7401fd9e" alt="캡처1" width="60%">

#### 3. 공식 문서와 AI 제안 내용 교차 검증
<img src="https://github.com/user-attachments/assets/22b48bff-f15f-4570-8e50-a44fd85849e3" alt="캡처1" width="60%">


**주요 개선점**: 
- 사이드 이펙트 사전 파악으로 리스크 최소화
- 빠르게 변경점 파악 및 파일 적용 가능
  
---

## 종합 효과 및 결론

### 주요 성과
- **시간 효율성**: 단순 반복 작업의 대폭적인 시간 단축
- **품질 향상**: 사람의 실수로 인한 누락 방지
- **업무 집중도**: 핵심 비즈니스 로직 개발에 더 많은 시간 투자 가능

### 향후 활용 계획
- 복잡한 비즈니스 로직 AI 툴을 활용한 구현
- WebRTC 활용한 대용량 트래픽 시스템 아키텍처 설계 및 개선



