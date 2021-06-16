---
title: "SaaS & ASP 비교"
date: 2021-06-15 18:37:28 -0400
categories: SaaS
---

혼동하기 쉬운 SaaS와 ASP르 비교한다.

# 기본 개념
## SaaS : Software as a Service
서비스 기반 아키텍쳐

대표주자 : 세일즈포스닷컴, 석세스펙터, 베이스 캠프

### 특징
[SaaS와 ASP차이](https://heyhyungki.tistory.com/149)
1. 사용자 기능 재정의(Configurable App)
- 업무 프로세스나 로직, 화면, 데이터베이스 조작 등을 고객사의 특정 요구에 맞춰 수정하거나, 새로운 업무 기능을 기존 앱에 추가할 수 있는 기술을 내포해야함
- 이러한 수정 작업에 '재코딩/재컴파일' 과정을 밟지 않고, 정의(Define) 작업만으로 수행해야 함.
- 이를 위해서 2015년 가트너 발표 10대 IT 키워드로 선정된 "SDA : Software-Defined Application"이 접목되어야 함.

2. 멀티테넌트(Multi_Tenancy)
![Multi Tenant & Single Tenant](https://mblogthumb-phinf.pstatic.net/MjAyMDAxMjBfODgg/MDAxNTc5NDk0ODQ2OTM3.ojXj6Fg4AyZhoXT2uy8tXlhkETmqoz479v_WPyj7cugg.zdmOSUhnn9kXIFEtBWVdAOoW11RrkSoIrCCFe6q-ZLwg.PNG.ki630808/multitenancy2.PNG?type=w800)
- 고객사별 요구사항이 수용된 맞춤 업무 처리 서비스를 하지만, 앱 실행 인스턴스는 단 1개만 실행되어야 함.
- 소프트웨어 멀티 테넌시란 소프트웨어 아키텍처의 한 종류로 하나의 Software Instance 가 하나의 서버 위에서 여러개의 Tenant를 서비스함. 멀티인스턴스와 다른 개념
- 복수의 고객들은 동일한 데이터 스토리지 매커니즘과 함께 동일한 하드웨어의 동일한 OS에서 실행되는 동일한 Application을 공유한다.
- 이는 구성요소가 이양됨으로써 각 고객이 별도의 VM에서 구동되는 것처럼 보이게 하는 가상화와의 차이점이다. [ref](https://jins-dev.tistory.com/entry/Software-Multi-Tenancy-%EC%99%80-Cloud-%EC%97%90%EC%84%9C%EC%9D%98-Multi-Tenancy)
- 고객사별 요구사항이 별도의 프로그램소스와 이에 대응된 실행 인스턴스가 각각 존재하게 되면, 서비스 제공자는 각 고객사별로 소스관리와 인스턴스 관리를 해야 하기 때문에 서비스 사용자 범위 확장을 어렵게하는 주범이 됨
- 이 두 기술의 존재 여부에 땨라 SaaS와 ASP로 구분할 수 있음

```
테넌트(Tenant)란 소프트웨어 인스턴스에 대해 공통이 되는 특정 접근 권한을 공유하는 사용자들
```

3. 성능확장성(Scalability)
- 비즈니스 앱 자체적인 스케일-업 기능 수단 마련 필요
- 앱 실행 상태를 자체적으로 수집하고 모니터링 할 수 있는 기능 자체 내제

## ASP : Application Service Provider
소프트웨어를 패키지 형태로 판매하지 않고 일정한 요금을 받고 온라인으로 어플리케이션 임대 서비스
예) 전사적자원관리(ERP), 제품정보관리(PDM), 그룹웨어, 전자상거래(EC), 전자문서교환(EDI) 등 하이엔드 어플리케이션는 물론 오피스 제품 등을 빌려주는 것

# ASP와의 공통점 과 차이
[ASP앱 vs SaaS 앱 비교](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FqFeSR%2FbtqCcCpTbMT%2FlMp8UA58evrzV3itO4ad70%2Fimg.png)
## 공통점
* 인터넷을 통해 소비자(주로 기업)에 어플리케이션을 제공함.
* 정액제 또는 종량제 등의 방식으로 빌렸쓰는 모델
* 이를 통해 소비자들은 어플리케이션 구매 비용 절감 및 막대한 인프라 투자와 관리 어려움 제거

## 차이점
* ASP는 단순희 일부 어플리케이션 공급 방식을 온라인으로 대체, 사용자 요구 사항 대응이 어려움
* SaaS는 기본적으로 SW의 선택, 공급, 운영을 지원하는 단일한 플랫폼을 통해 모든 SW 영역의 서비스 제공, 구현이 어려움

