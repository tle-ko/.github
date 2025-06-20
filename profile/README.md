<img src="https://github.com/user-attachments/assets/1d3bc4d2-90b5-4319-9e78-ef81d0476ace">

> __LLM을 활용한 코딩테스트 스터디 플랫폼, TLE__ (🔗 https://tle-kr.com/)

🏆 제 8회 개방형 클라우드 플랫폼(K-PaaS) 기반 서비스 개발·아이디어 공모전 <b><네이버클라우드상></b> <sub>2024.11.20</sub>

🏆 2024학년도 상명대학교 컴퓨터과학전공 캡스톤디자인 <b><대상></b> <sub>2024.11.29</sub>

## 1. 프로젝트 개요

### 🗓 개발 기간
2023년 9월 ~ 2024년 11월 (1년 3개월)  
### 👨‍👩‍👧‍👧 팀원
| 김동주 (팀장)| 조유진 | 이유민 | 강윤진 |
| --- | --- | --- | --- |
| <a href="https://github.com/hepheir"><img src="https://avatars.githubusercontent.com/u/19310326?v=4" width="120px" alt="김동주"/><br /><sub><b>hepheir</b></sub></a> | <a href="https://github.com/ohcuy"><img src="https://avatars.githubusercontent.com/ohcuy?s=100" width="120px" alt="조유진"/><br /><sub><b>ohcuy</b></sub></a> | <a href="https://github.com/Whatdoyumin"><img src="https://avatars.githubusercontent.com/u/90082215?v=4" width="120px" alt="이유민"/><br /><sub><b>Whatdoyumin</b></sub></a> | <a href="https://github.com/yun0329"><img src="https://avatars.githubusercontent.com/u/90076631?v=4" width="120px" alt="강윤진"/><br /><sub><b>yun0329</b></sub></a> |
| 개발 PM<br/>Backend Lead Developer<br/>Infrastructure<br/>AI Research & MLOps | 기획 PM<br/>Frontend Developer<br/>UI/UX Design<br/>Infrastructure<br/>AI Research & Visualization | Frontend Lead Developer<br/>Infrastructure | Frontend Developer<br/>Data ETL |

### ✏️ 프로젝트 기획 배경 및 문제 해결 과정
#### 문제 인식
코딩 테스트는 IT 분야 취업 및 이직을 준비하는 이들에게 **기술 역량을 평가받는 핵심 관문**입니다. 기업들이 채용 과정에서 이를 적극적으로 활용하면서, 많은 예비 개발자들이 코딩 테스트 준비에 상당한 시간과 노력을 들이고 있습니다.

이 과정은 쉽지 않고, 특히 지역 간 **학습 자원의 불균형**은 여전히 큰 장벽으로 작용하고 있습니다. 수도권에 비해 지방은 알고리즘 스터디 참여나 피드백 받을 기회가 현저히 부족하며, 함께 공부할 동료를 찾기도 어렵습니다.
실제로 한 팀원은 지방 거주 당시 알고리즘 스터디에 참여하고 싶었지만, 함께할 사람을 모으기도, 홍보하기도 쉽지 않은 현실에 부딪혔습니다.

#### 해결 방안
이러한 문제의식을 바탕으로, **누구나 장소에 구애받지 않고 체계적으로 코딩 테스트를 준비**할 수 있는 온라인 플랫폼의 필요성을 느꼈습니다.
단순한 문제 풀이를 넘어, **학습의 흐름과 사람 간의 연결**을 함께 설계하고자 했습니다.

TLE는 단순한 알고리즘 문제 풀이 서비스를 넘어서는,
**효율적이고 지속 가능한 코딩 테스트 준비**를 위한 통합 학습 플랫폼입니다.

#### 주요 기능
- 🔍 문제 분석 기반 학습 – 단순 정답이 아닌 알고리즘적 사고를 길러주는 해설 및 분석 지원
- 👥 스터디 그룹 관리 – 그룹 생성부터 참여, 학습 진행을 한 플랫폼에서 효율적으로 모두 한 곳에서 간편하게 관리
- 🧑‍💻 코드 리뷰 & 피드백 – 서로의 코드를 읽고, 질문하고, 성장할 수 있는 상호 학습 구조

**혼자보다 함께, 지역과 환경의 제약 없이, 누구든 효과적으로 성장할 수 있도록** 돕는 것이 TLE의 목표입니다.

## 2. 개발 환경
### ⚙️ 환경 설정
#### Frontend
```
- Node.js
- React
- JavaScript
- Tailwind CSS
- React Router Dom
```

#### Backend
```
- Django Rest Framework(DRF)
- PostgreSQL
```

#### CI/CD
```
- AWS EC2
- Docker
- nginx
```

#### AI
```
- Gemini-1.5-flash
- GPT-3.5-turbo
```

### ⚙️ 개발 문서
#### 서비스 아키텍처
![서비스 아키텍처](https://github.com/user-attachments/assets/dadce7d4-729d-4358-922d-eb9148e2d68f)

---

#### LLM 모델 아키텍처
![모델 아키텍처](https://github.com/user-attachments/assets/b2f9d6b4-5cac-4df4-9d17-6b0ce7eef387)

-  LLM 모델 서비스에서의 가장 큰 어려움은 느린 응답속도와 API 사용에 따른 비용 부담입니다. 이러한 요소들을 고려하면서 사용자 경험을 향상시키는 것이 중요하였습니다.
-  따라서 지연 큐를 거쳐 일정한 속도로 분당 약 15회 정도로 LLM에 답변을 넣고 분석하여 이 결과를 평가한 뒤에 프롬프트 개선 과정을 반복하는 파이프라인을 구축하였습니다.
-  자연어 구문 분석의 난이도가 높아, 이를 해결하기 위해 다양한 정확도 지표를 조사하였고, 최종적으로 자체적인 정확도 측정 함수를 설계하였습니다.

---

## 3. 주요 기능
![기능1](https://github.com/user-attachments/assets/5133bb46-5353-4a85-a408-8a9c6369c50e) 
![기능2](https://github.com/user-attachments/assets/2ab20bd4-41fe-4642-b829-edec1a076e26)
- 사용자가 문제를 등록하면 자동으로 분석을 수행하며, 알고리즘 문제 분석 모델로 분석 된 알고리즘 태그, 난이도, 예측 시간 복잡도, 순차적 풀이 힌트를 제공합니다.
![기능3](https://github.com/user-attachments/assets/0ca45014-cd95-4510-adff-177da158a738)
- 원하는 크루원의 조건을 설정하여 모집할 수 있습니다. 특히, 백준 온라인 저지의 티어에 관련 된 상한을 설정할 수 있으며, 사용자가 회원가입 시 입력한 아이디에 따라 서비스 내에서 자동적으로 티어를 산출하여 필터링합니다.
- 가입 요청 시 선장의 이메일로 신청서가 발송되며, 플랫폼 내에서 승인 여부를 체크하면 결과가 회원가입 한 이메일로 신청자에게 발송됩니다.
![기능4](https://github.com/user-attachments/assets/9e83f1e3-8100-48de-95a6-0dd806e57d76)
![기능5](https://github.com/user-attachments/assets/4656e361-e12f-4249-91a8-e547d165d975)
- 사용자들이 함께 학습할 수 있도록 크루 별 대시보드로 활동 정보를 시각화 하여 제공합니다. 
- 대시보드에서는 크루 전체가 풀이한 문제의 총 난이도, 풀이한 문제의 알고리즘 태그 순위와 주차별 풀이할 문제 리스트, 문제 풀이 현황, 코드 리뷰 현황을 확인할 수 있습니다.


## 4. 기대 효과
1. 지역 간 학습 기회의 불균형을 해소함으로써 더 많은 사람들이 동등한 학습 기회를 얻게 되고, 장기적으로는 IT 개발 인력 시장에서 우수한 인재를 발굴하고 육성하는 것을 기대합니다.
2. 사용자는 자신이 풀고자 하는 문제를 명확하게 이해하고 풀이에 필요한 가이드를 제공받을 수 있습니다. 이는 코딩 테스트 준비에 대한 진입 장벽을 낮추며 학습의 효율성을 향상시킵니다.
3. 기계 학습을 통한 자료구조 알고리즘 태그 예측 시 평가 지표로 활용할 수 있는 방법을 제시하며 관련 연구의 활성화에 기여합니다.

## 5. 관련 링크
🔗 시연 영상: https://youtu.be/ajJrBxF5-iU <br/>
🔗 K-Paas 공모전 수상 결과 및 발표자료: https://contest.k-paas.org/awardList_2024.jsp;jsessionid=15BB6BAAF58160697CA1327E13F236B1
