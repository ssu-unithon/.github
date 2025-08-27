# 모여봐요 정보섬 🏝️

![University](https://img.shields.io/badge/University-Soongsil-blue)
![Team](https://img.shields.io/badge/Team-모여봐요정보섬-brightgreen)
![Hackathon](https://img.shields.io/badge/Hackathon-UNITHON-orange)

## 🏝️ About Us

안녕하세요! **모여봐요 정보섬** 팀입니다.

우리는 숭실대학교에서 **UNITHON(숭실대학교 IT대학 해커톤)** 에 참가하여 **Pillink** 프로젝트를 개발하였습니다.

---

## 🔗 Pillink Project

> **"고령층의 복약 관리와 약물 상호작용을 가족이 실시간으로 모니터링하고 지원하는 헬스케어 앱"**

### 🎯 Problem & Solution

**Problem**: 
- 🧓 65세 이상 시니어 다약제 복용률 높아 약물 부작용·상호작용 및 복용 누락 위험 증가
- 📊 75세 이상 노인 중 70.2%가 3개월 이상 5개 이상의 약물을 만성 복용 (OECD 최고수준)
- 👨‍👩‍👧‍👦 서로 다른 의료기관 처방으로 통합 관리 부재, 가족·의료진이 실시간 확인 어려움
- ⚠️ 10종 이상 약제 복용 시 부작용 발생 가능성 거의 100%

**Solution**: 
AI 기반 약물 상호작용 분석과 보호자-대상자 실시간 연동을 통한 **안전하고 지속적인 복약 관리 플랫폼**

### 🏗 Architecture Overview

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Frontend      │───▶│   Backend API   │───▶│  Flask Service  │
│  (TypeScript)   │    │  (TypeScript)   │    │    (Python)     │
│                 │    │                 │    │                 │
│ • 링크 관리 UI   │    │ • RESTful API   │    │ • AI 약물 분석   │
│ • 사용자 인터페이스│   │ • 인증/권한관리  │    │ • 상호작용 검증  │
│ • 반응형 디자인   │    │ • 비즈니스 로직  │    │ • 위험도 계산    │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

---

## 🎪 UNITHON 상세 기획

### 💡 핵심 아이디어 

**"시니어 복약 관리 + 가족 연동 + AI 위험도 분석"**

40-50대 보호자가 70-80대 부모님의 복약을 원격으로 안전하게 관리할 수 있는 차세대 헬스케어 솔루션

### 🔍 타겟 사용자

#### 1차 타겟: 보호자 (40-50대)
- **페르소나**: 김미영 (50세, 중견기업 정규직)
- **상황**: 75세 부모님 (고혈압·당뇨 복합), 직장-가정 병행으로 원거리 부모 건강관리 어려움
- **니즈**: 실시간 건강 상태 확인 수단 절실히 필요

#### 2차 타겟: 보호 대상자 (70-80대)
- **상황**: 다량의 약물 복용, 복용 시간 및 순서 혼란 빈번
- **니즈**: 간단하고 직관적인 복약 알림 시스템

### 🚀 핵심 기능 상세

#### 1. **복용 검증 캘린더**
- **보호대상자**: 해당 캘린더를 통해 자신의 알약 섭취 사실을 기억 가능
- **보호자**: 보호대상자의 복용 여부를 캘린더를 통해 실시간 확인
- **실시간 동기화**: 복용 완료 시 즉시 보호자에게 알림 전송

#### 2. **AI 기반 위험도 시각화**
- **색상 코딩 시스템**:
  - 🟢 **안전 (0점)**: "현재 약물 상호작용에 문제가 없습니다"
  - 🟡 **주의 (1-33점)**: "상호작용 위험 존재, 의사·약사 상담 고려"
  - 🟠 **경고 (34-66점)**: "위험 점수 높음, 약물 변경 또는 중단 상담 필요"
  - 🔴 **위험 (67-100점)**: "즉시 의료진과 상담 필요"
- **원형 게이지**: 인지능력이 떨어지는 고령층도 쉽게 이해 가능한 직관적 UI

#### 3. **상호작용 분석 리포트**
- **MVP 단계**: 공공 데이터(KPIC) 기반 기본 상호작용 분석 제공
- **고도화 단계**: 머신러닝 기반 개인 맞춤 예측 기능
- **실시간 분석**: 새로운 약물 추가 시 즉시 위험도 재계산

#### 4. **보호자-보호대상자 상호 연동 시스템**
- **약물 리스트 관리**: 보호자가 보호대상자의 모든 약물 정보 통합 관리
- **알람 설정**: 약물별 개별 복용 알람 스케줄링
- **복용 확인**: 설정된 알람 → 보호대상자 복용 → 보호자 확인 워크플로우

#### 5. **스마트 약물 등록**
- **OCR 기반 처방전 인식**: 처방전 촬영으로 약물 정보 자동 추출
- **AI 라벨 인식**: 약통 사진 촬영으로 약명, 용법, 용량 자동 등록
- **약품 검색**: 식품의약품안전처 API 연동 실시간 검색

#### 6. **AI 챗봇 상담**
- **Hybrid 구조**: 규칙 기반 + AI 챗봇 결합
- **3단계 질의응답**:
  - 사용 문의 → 사전 작성된 FAQ (규칙 기반)
  - 약 관련 질문 → koBERT + 식약처 API
  - 개인 프로필 문의 → 사용자 DB 연동

### 🎨 UX/UI 설계 철학

#### **시니어 중심 UX**
- **이중 모드 설계**: 보호자와 보호대상자 각각 최적화된 별도 인터페이스
- **보호대상자 모드**: 홈화면 + 알람화면 단순 구성, 모바일 앱 사용 미숙자도 쉽게 이용
- **색상 대조**: 시니어 색상 구별 능력 고려한 명확한 대비 (회색/파란색/빨간색)

#### **핵심 화면 구성**
1. **온보딩**: 보호자/보호대상자 역할 선택
2. **프로필 선택**: 넷플릭스 스타일 다중 프로필 관리
3. **홈 대시보드**: 복용 현황 캘린더 + 위험도 게이지
4. **약물 관리**: 복용 중인 약물 리스트 + 추가/수정 기능
5. **리포트**: 상호작용 분석 결과 + 의료진 상담 권장사항

---

### 📊 시장 분석 및 경쟁우위

#### **시장 규모 (TAM-SAM-SOM)**
- **TAM**: 국내 65세 이상 다약제 복용자 약 350만 명
- **SAM**: 스마트폰 사용 시니어 약 255만 명 (스마트폰 보급률 73%)
- **SOM**: 보호자 연동 수요 높은 가구 약 12.7만 명 (점유율 5% 가정)

#### **경쟁사 대비 차별화 전략**

| 서비스 | 개인 헬스케어 | 가족 연동 | AI 상호작용 분석 | 시니어 특화 UX |
|--------|:-------------:|:---------:|:----------------:|:-------------:|
| **Pillink** | ✅ | ✅ | ✅ | ✅ |
| Medisafe | ✅ | ⚠️ | ❌ | ❌ |
| MyTherapy | ✅ | ⚠️ | ❌ | ❌ |
| 스마트 DUR | ❌ | ❌ | ⚠️ | ❌ |

**핵심 차별점**: 
- 💊 **통합 관리**: 복약 알람 + 상호작용 분석 + 가족 모니터링 원스톱 솔루션
- 👥 **실시간 연동**: 보호자-대상자 양방향 실시간 커뮤니케이션
- 🧠 **AI 기반**: KPIC 데이터 + 머신러닝을 통한 개인화된 위험도 분석

---

## 💰 비즈니스 모델

### **수익 구조**
#### 1차 (시장진입): B2C 프리미엄 구독제
```
무료 버전:
- 기본 알람 기능
- AI 챗봇
- 최대 보호 대상자 2명

프리미엄 버전 (월 5,400원):
- AI 약물 상호작용 분석
- 보호 대상자 인원 제한 없음
- 고급 리포트 및 통계
```

#### 2차 (시장 확대): B2B 제휴 확장
- **약국/의료기관 제휴**: 복약 지도 서비스 패키지
- **보험사 연계**: 건강관리 부가서비스 제공
- **데이터 수익화**: 익명화된 복약 패턴 데이터 분석 리포트 판매

### **성장 전략**
1. **1-3개월**: 대학생 네트워크 → 가족 추천을 통한 유기적 확산
2. **6개월**: 지역 약국 및 지자체 복지센터 제휴
3. **1년 이후**: 전국 약국 체인 및 의료진 연계 서비스 확장

---

## 📂 Repository Structure

### 🗂 Our Repositories

<table>
<tr>
<td width="50%">

#### 🎨 Frontend
**[Pillink](https://github.com/ssu-unithon/Pillink)**
- **Language**: TypeScript + React Native
- **Features**: 시니어 친화적 UI, 실시간 동기화
- **핵심 화면**: 복용 캘린더, 위험도 대시보드

</td>
<td width="50%">

#### ⚙️ Backend API
**[Pillink-Backend](https://github.com/ssu-unithon/Pillink-Backend)**  
- **Language**: TypeScript + NestJS
- **Features**: 
  - 사용자 인증 및 가족 그룹 관리
  - 약물 데이터 CRUD 및 복용 기록
  - 실시간 알림 시스템

</td>
</tr>
<tr>
<td width="50%">

#### 🐍 AI-Powered Analysis Service
**[Pillink-Flask](https://github.com/ssu-unithon/Pillink-Flask)**
- **Language**: Python + Flask
- **AI Features**: 
  - 🧠 **약물 상호작용 분석** (KPIC 데이터 기반)
  - 🎯 **위험도 스코어링** (머신러닝 모델)
  - 🔍 **자연어 처리** (koBERT 기반 챗봇)
  - 📊 **개인화 추천** (복용 패턴 학습)

</td>
</tr>
</table>

---

## 🛠 Tech Stack

<div align="center">

### Frontend Development
![React Native](https://img.shields.io/badge/react_native-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)
![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white)
![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)

### Backend Development
![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white)
![NestJS](https://img.shields.io/badge/nestjs-%23E0234E.svg?style=for-the-badge&logo=nestjs&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A8?style=for-the-badge&logo=python&logoColor=ffdd54)
![Flask](https://img.shields.io/badge/flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white)

### AI/ML Technologies
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white)
![OpenCV](https://img.shields.io/badge/opencv-%23white.svg?style=for-the-badge&logo=opencv&logoColor=white)

### Infrastructure & Tools
![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)
![Railway](https://img.shields.io/badge/Railway-131415?style=for-the-badge&logo=railway&logoColor=white)

</div>

---

## 🎪 UNITHON Experience

### 🔥 5일 해커톤 여정

```
📅 Day 1: 아이디어 발굴 & 팀 빌딩
├─ 🎯 문제 정의: 고령층 복약 관리의 사회적 이슈 분석
├─ 💡 솔루션 구상: Pillink 컨셉 설계 및 차별화 전략  
├─ 👥 역할 분담: PM/디자이너/3명 개발자 역할 정의
└─ 📋 기술 스택 선정: TypeScript + Python + AI 통합 아키텍처

💻 Day 2-3: 개발 스프린트  
├─ 🎨 Frontend: React Native 기반 시니어 친화적 모바일 앱 개발
├─ ⚙️ Backend: NestJS API 서버 및 실시간 알림 시스템 구축
├─ 🐍 Flask: **AI 약물 상호작용 분석 엔진**
│  ├─ KPIC 공공데이터 API 연동 및 전처리
│  ├─ 약물 위험도 스코어링 알고리즘 개발
│  ├─ koBERT 기반 자연어 처리 챗봇 구현
│  └─ OCR 처방전/약통 라벨 인식 시스템
├─ 🗺️ Positioning: 응급상황 대응 위치 기반 서비스
└─ 🔗 시스템 통합: 마이크로서비스간 API 연동

🚀 Day 4-5: 완성도 향상 & 발표 준비
├─ 🔧 통합 테스트 및 버그 픽스
├─ 📊 사업계획서 및 시장분석 자료 준비
├─ 🎬 데모 시나리오 구성 및 발표 연습
└─ 🎤 최종 발표 및 심사위원 질의응답
```

### 🏆 주요 성과

- ✅ **완전한 Full-Stack AI 서비스** 구현 (4개 독립 서비스)
- ⚡ **마이크로서비스 아키텍처** 성공적 설계 및 배포  
- 🎯 **실사용 가능한 MVP** 개발 완료 (베타테스트 준비 완료)
- 🤝 **5인 팀워크**: 각자 전문영역에서 탁월한 성과 달성
- 📈 **비즈니스 완성도**: 시장분석부터 수익모델까지 체계적 계획
- 🧠 **AI 기술 통합**: OCR, NLP, 상호작용 분석 등 다각도 AI 활용

---

## 💫 What We Learned

### 🎓 Technical Growth

#### **Architecture & Integration**
- **마이크로서비스 설계**: 4개 독립 서비스의 유기적 연동
- **AI 서비스 통합**: Flask 기반 머신러닝 모델의 REST API 배포
- **실시간 통신**: WebSocket을 활용한 보호자-대상자 실시간 동기화

#### **AI/ML Implementation**
- **자연어 처리**: koBERT를 활용한 의료 도메인 특화 챗봇 개발
- **컴퓨터 비전**: OCR을 통한 처방전 및 약물 라벨 자동 인식
- **데이터 분석**: KPIC 공공데이터 전처리 및 약물 상호작용 알고리즘 구현

#### **Full-Stack Development**
- **Frontend**: React Native 기반 크로스플랫폼 모바일 앱 아키텍처
- **Backend**: NestJS의 모듈 구조와 의존성 주입 패턴 활용
- **Database**: 복용 기록 및 가족 관계 데이터 모델링

### 🤝 Collaboration & Project Management  

#### **역할 기반 협업**
- **PM**: 전략적 기획 및 개발 일정 조율, 요구사항 관리
- **Designer**: 시니어 친화적 UX 리서치 및 직관적 UI 시스템 구축
- **개발자**: Frontend, Backend, AI 각 영역의 전문성 발휘

#### **문제 해결 능력**
- **기술적 도전**: 해커톤 제한 시간 내 복잡한 AI 기능 구현
- **의사소통**: 5명 팀원간 효율적인 진행상황 공유 및 이슈 해결
- **품질 관리**: 사용자 중심 사고로 핵심 기능 우선순위 설정

---

## 👥 Team 모여봐요 정보섬

| Role | Name | Contribution & Expertise |
|------|------|-------------------------|
| **PM** | **남지윤** | 프로젝트 전략 기획, 팀 협업 조율, 요구사항 분석<br>• 시장분석 및 사업계획서 작성<br>• 개발 일정 관리 및 품질 관리 |
| **Designer** | **유은정** | UI/UX 디자인 시스템, 사용자 리서치, 브랜드 아이덴티티<br>• 시니어 친화적 UX 설계<br>• 직관적 색상 시스템 및 아이콘 디자인 |
| **Frontend Lead** | **홍준우** | TypeScript React Native 개발, 모바일 앱 아키텍처<br>• 크로스플랫폼 모바일 애플리케이션 구현<br>• 실시간 데이터 바인딩 및 상태 관리 |
| **Backend Lead** | **이재헌** | NestJS API 서버, 데이터베이스 스키마 설계<br>• RESTful API 및 실시간 알림 시스템<br>• 가족 그룹 관리 및 권한 시스템 |
| **AI Lead** | **이수아** | Python Flask ML 서비스, 자연어 처리<br>• KPIC 데이터 기반 약물 상호작용 분석<br>• OCR 및 koBERT 챗봇 개발 |

---

## 🏆 UNITHON 성과 및 학습

### 📊 정량적 성과

**개발 성과**:
- ⏱️ **5일 집중개발**: 기획부터 배포까지 완전한 서비스 구현
- 🖥️ **4개 독립 서비스**: Frontend, Backend, AI, Positioning 각각 배포 완료
- 📱 **12개 핵심 화면**: 온보딩부터 리포트까지 완전한 사용자 여정 구현
- 🔗 **15개 API 엔드포인트**: 인증, 약물관리, 가족연동, 알림, 챗봇 등 구현
- 🧠 **3개 AI 모듈**: OCR, 상호작용 분석, NLP 챗봇 통합

**기획 완성도**:
- 📈 **시장규모 분석**: TAM 350만명, SAM 255만명, SOM 12.7만명
- 💰 **수익모델 설계**: B2C 구독제 + B2B 제휴 + 데이터 수익화
- 🎯 **경쟁분석**: 기존 3개 주요 서비스 대비 4개 차별화 요소 도출
- 📋 **사업계획**: 5개 단계별 성장전략 및 자금조달 계획 수립

### 🎓 질적 성장

**기술적 역량**:
- **시스템 설계 능력**: 복잡한 헬스케어 도메인을 명확한 서비스 아키텍처로 구현
- **AI 실전 적용**: 학술적 지식을 실제 사용자 문제 해결에 활용
- **풀스택 개발**: 각자의 전문 영역에서 전체 시스템에 기여하는 통합적 사고

**협업 및 소통**:
- **애자일 방법론**: 짧은 스프린트와 지속적인 피드백을 통한 빠른 개발
- **의사결정 과정**: 기술적 제약과 사용자 니즈 사이의 균형점 찾기
- **위기관리**: 개발 중 발생한 기술적 이슈들을 팀워크로 신속하게 해결

---

*Made with ❤️ by Team 모여봐요 정보섬*  
*UNITHON 2025 • Soongsil University IT College*  
*Connect. Create. Change.*

![Wave Footer](https://capsule-render.vercel.app/api?type=waving&color=gradient&height=100&section=footer)

</div>
