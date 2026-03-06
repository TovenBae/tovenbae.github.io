---
title: "Claude Opus 4.6 공개"
date: 2025-02-09 09:00:00 -0400
categories: ai
---

향상된 코딩 능력과 장기적 작업 지속성을 갖춘 Anthropic의 최신 모델로, 1M 토큰 컨텍스트 윈도우를 베타로 지원한다.

> **컨텍스트 윈도우(Context Window)** : 모델이 한 번의 요청에서 입력(프롬프트)과 출력(응답)을 합쳐 처리할 수 있는 최대 토큰 수. 1M(100만) 토큰은 약 75만 단어, 일반 서적 약 10권 분량에 해당한다. 컨텍스트 윈도우가 클수록 긴 문서나 대규모 코드베이스를 한 번에 참조할 수 있다.
>
> **최대 출력(Max Output / Output Tokens)** : 모델이 한 번의 응답에서 생성할 수 있는 최대 토큰 수. Opus 4.6은 128k(약 12만 8천) 출력 토큰을 지원하며, 이는 긴 코드 생성이나 상세한 분석 보고서 작성에 유리하다. 컨텍스트 윈도우의 일부를 출력이 사용하므로, 입력이 길어지면 출력 가능한 토큰이 줄어든다.

# 요약

- 주요 벤치마크에서 업계 최고 수준의 점수를 기록하며, GPT-5.2보다 약 144 Elo 포인트 우위
- 코드 리뷰, 디버깅, 대규모 코드베이스 처리, 재무 분석, 순서 작성 등 실무 중심 작업에서 성능이 강화됨
- Adaptive thinking, context compaction, effort 조절 등 개발자 제어 기능이 추가되어 장기 실행형 에이전트 운영이 용이
- 안정성 평가에서도 오류, 남용, 과잉 거부율이 낮은 결과를 보여, 고성능의 안정성을 동시에 달성한 모델로 평가

# 주요 개선점

- Opus 4.6은 이전 대비 계획 능력, 에이전트 지속성, 코드 품질 관리가 향상된 모델
    - 대규모 코드 베이스에서 더 안정적으로 작동하며, 자체 오류 탐지 및 수정 능력 강화
    - 1M 토큰 컨텍스트 윈도우(베타)로 장문 복합 작업 처리 가능
- 일상 업무 활용성도 확대되어, 재무 분석, 리서치, 문서, 스프레드시트, 프레젠테이션 생성 등 다양한 작업 수행
- Cowork 환경에서 멀티태스킹 자율 수행이 가능, 사용자를 대신해 복합 업무 처리

# 벤치마크 및 성능 평가

- Terminal-Bench 2.0에서 최고 점수, Humanity's Last Exam에서도 모든 프런티어 모델 중 선두
- GDPval-AA 평가에서 GPT-5보다 약 144 Elo 포인트, Opus 4.5보다 190 포인트 높은 성능
- BrowseComp 테스트에서도 최고 성능을 기록, 온라인 정보 탐색 능력 강화
- MRCR v2(1M variant)에서 76% 점수로, Sonnet 4.5의 18.5% 대비 큰 향상
- 장문 컨텍스트 유지력과 정보 추적 능력이 개선되어 context rot 현상 완화

# 제품 및 API 업데이트

Claude Developer Platform에서 다음 기능이 추가되었다.

- **Adaptive Thinking** : 모델이 상황에 따라 심층 사고 여부를 자동 결정
- **Effort 레벨** : low, medium, high(기본), max 네 단계 제공
- **Context compaction(베타)** : 대화가 길어질 때 오래된 컨텍스트를 요약, 대체
- **1M 토큰 컨텍스트(베타)** 및 128k 출력 토큰 지원
- **US-only inference** 옵션 제공(1.1배 요금)
- Claude Code에 agent teams 기능 추가, 여러 에이전트가 병렬 협업 가능
- Claude in Excel은 비정형 데이터 구조화, 다단계 변경 처리 능력 향상
- Claude in PowerPoint(리서치 프리뷰)는 슬라이드 템플릿, 폰트, 레이아웃을 인식해 브랜드 일관성 유지

# 접근 및 가격

- Opus 4.6은 claude.ai, API, 주요 클라우드 플랫폼에서 즉시 사용 가능
- API 모델명은 `claude-opus-4.6`, 가격은 $5/$25 per million tokens으로 이전과 동일
- 200k 토큰 초과 프롬프트에는 프리미엄 요금($10/$37.5 per million tokens) 적용

# 결론

- Claude Opus 4.6은 장기 컨텍스트 처리, 자율적 에이전트 작업, 고급 추론 능력에서 큰 도약을 이룸
- 성능, 안정성, 개발자 제어성을 모두 강화한 모델로, 실무형 AI 도구의 새로운 기준 제시

# 참고

- [Claude Opus 4.6 모델 개요](https://platform.claude.com/docs/ko/about-claude/models/overview)
- [GeekNews - Claude Opus 4.6 공개](https://news.hada.io/topic?id=26433)
- [GeekNews - Claude Code 4.6 Fast Mode 공개](https://news.hada.io/topic?id=26499)
