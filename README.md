# ☕️ 텅장 구원 커피 수혈단
 본 프로젝트는 전국 주요 체인점 카페에서 합리적인 가격으로 커피를 즐기고자 하는 소비자들을 대상으로 합니다.

프로젝트 개요 : 주요 체인점 카페(스타벅스, 할리스, 메가커피, 커피빈, 더벤티, 컴포즈커피, 탐앤탐스, 이디야, 빽다방)의 커피 제품을 기준으로 가격 및 칼로리,카페인 함량 데이터를 분석합니다.

목적 : 분석된 데이터를 통해 소비자들이 가격 대비 효율적인 커피를 선택하고, 합리적인 소비를 할 수 있도록 실질적인 정보를 제공하는 것이 목표입니다.

## 👩👨 Team
#### 팀원: 정광민, 손성경, 최승혁, 김연희
|이름|역할|
|------|---|
|정광민|데이터 수집, 회의록 관리, 자료 내용정리|
|손성경|데이터 수집, 데이터 시각화, README작성|
|최승혁|데이터 수집, 데이터 관리, 코드 통합 및 관리|
|김연희|데이터 수집, PPT 초안 만들기, README작성|

## 💻 사용 기술
|분류|기술|
|------|---|
|개발 환경|![ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white) ![VScode](	https://img.shields.io/badge/Made%20for-VSCode-1f425f.svg)|
|언어|![python](	https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)|
|데이터 수집|<img src="https://img.shields.io/badge/Selenium-4CAF50?style=flat-square&logo=selenium&logoColor=white" alt="Selenium" /> <img src="https://img.shields.io/badge/BeautifulSoup-FFB300?style=flat-square&logo=beautifulsoup&logoColor=white" alt="BeautifulSoup" /> |
|형상 관리|![github](	https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white) ![git](https://img.shields.io/badge/GIT-E44C30?style=for-the-badge&logo=git&logoColor=white)|
|협업 도구|<img src="https://img.shields.io/badge/Confluence-0052CC?style=flat-square&logo=confluence&logoColor=white" alt="Confluence" /> <img src="https://img.shields.io/badge/Slack-4A154B?style=flat-square&logo=slack&logoColor=white" alt="Slack" />|
|DB 관리| ![MySql](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white) ![AWS](https://img.shields.io/badge/Amazon_AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white) ![GoogleCloud](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white) |

## 📂 데이터 수집 및 처리
|데이터 종류|출처|수집 방법|
|---------|---|-------|
|카페(아메리카노, 카페라떼, 카페모카)|브랜드별 홈페이지|Selenium, Beautifulsoup|
|카페 브랜드별 가격| 카카오 선물하기 홈|Selenium, beautifulsoup|
|브랜드별 평판 순위| Brand Reputation Index | 
|카페별 선호도 조사| 자체 제작 | Google form |

### 데이터 통합
본 프로젝트는 다양한 브랜드의 커피 데이터를 수집하고 이를 통합하여 비교 가능하도록 정리하였습니다. 이후, 가격·카페인·칼로리 등의 데이터를 지수화하고, 다음과 같은 전처리 과정을 통해 분석 준비를 마쳤습니다.

__1. 데이터 흐름 요약__
1. 브랜드 별 메뉴(아메리카노, 카페라떼, 카페모카) 데이터 추출 ->
2. 메뉴별 가격 데이터 추출 ->
3. 메뉴, 가격 데이터 데이터 프레임 통합 ->
4. 브랜드별 인기도, 설문 데이터 수집 ->
5. 통합한 데이터 DB 저장 ->
6. DB 데이터 시각화

__- 데이터 수집__
* 대상 브랜드 선정:
  대표적인 커피 브랜드: 할리스, 메가, 커피빈, 더벤티, 컴포즈, 탐앤탐스, 이디야, 뺵다방, 스타벅스

* 수집 항목:
  음료명(ICE): 아메리카노, 카페라떼, 카페모카
  데이터: 카페인 함량(g), 칼로리(kcal), 가격(원)

* 데이터 출처:
  * 각 브랜드별 공식홈페이지
  * 카카오 선물하기 홈페이지
 
__- 데이터 통합__
* 브랜드별 데이터베이스 저장
  * Brand : 브랜드명
  * menu : 아메리카노, 카페라떼, 카페모카
  * Kcal : 메뉴별 칼로리
  * Caffeine : 메뉴별 카페인

__2. 데이터프레임 기반 분석 및 지표 계산__
* 가성비 지수:
    * 가격/1mg = 카페인 / 가격

## 📊결과
__1. 카페인과 칼로리 비교__
<p align="center">* 아메리카노 카페인과 칼로리</p>

![image](https://github.com/user-attachments/assets/1c809102-7f51-4911-95c1-d21b4defc170)

<p align="center">* 카페라떼 카페인과 칼로리</p>

![image](https://github.com/user-attachments/assets/c312dedf-178d-42b3-b636-5f44008fc257)

 <p align="center">* 카페모카 카페인과 칼로리</P>
 
![image](https://github.com/user-attachments/assets/bc100eb5-97f6-4acd-bfaa-29731578e358)
 
 ---
__2. 카페인과 가격 비교__
<p align="center">* 아메리카노 카페인과 가격</p>

![image](https://github.com/user-attachments/assets/f073db61-afc8-4e7c-9881-2ad6e166e85e)

<p align="center">* 카페라떼 카페인과 가격</p>

![image](https://github.com/user-attachments/assets/35025c7a-613b-4a2d-b4b1-f91a35acc926)

<p align="center">* 카페모카 카페인과 가격</p>

![image](https://github.com/user-attachments/assets/981bd928-3232-4a8c-b2be-3853e0b4299a)

---
__3. 카페인 1mg당 가격 비교__
<p align="center">브랜드별 카페인 1mg당 가격 전체</p>

![image](https://github.com/user-attachments/assets/7d547977-f18a-44f1-87e0-81f393d989b4)

---
__4. 메뉴별 카페인 1mg당 가성비 비교__
<p align="center">* 아메리카노 1~4위</P>

![image](https://github.com/user-attachments/assets/47efc6f2-571a-4f82-ac95-4abe727e4121)

<p align="center">* 카페라떼 1~4위</p>

![image](https://github.com/user-attachments/assets/d0995adb-f089-47c0-b645-016a65173f14)
<p align="center">* 카페모카 1~4위</p>

![image](https://github.com/user-attachments/assets/6802b2e1-63a6-4856-a247-83d6deee3824)










