### <감석분석을 활용한 다이어트 보조식품에 대한 온라인 평판분석>



#### 1. 프로젝트 내용 내용 요약

1. 본 연구에서는 체중 감량을 위해 무분별한 다이어트 식품의 남용을 막고, 다이어트 보조 식품에 대한 정보를 제공하기 위해서 감성 분석을 활용하여 다이어트 보조 식품에 대한 온라인 후기를 분석
2. 다이어트 보조 식품을 섭취 후 흡수 형태에 따라 네 가지 종류로 분류
      
      (A) 포만감을 느끼게 하는 식품
      (B) 식욕을 억제하도록 돕는 식품
      (C) 단백질을 보충해 주는 식품
      (D) 칼로리 흡수를 저지하는 식품으로 분류

3. 각 카테고리 별로 긍정 및 부정 점수를 계산
3. 체중 감량에 대한 감성 사전을 다이어트 식품에 대한 후기를 텍스트 마이닝하여 구축
4. 특히 부작용이 있는 식품에 대한 부정 점수에 가중치를 두기 위해서 WHO-ART에서 정의한 부작용 용어에는 가중치를 두어 처리
5. 분석 결과 단백질 보충 식품군이 긍정 점수가 가장 높게 나타났고, 이는 다이어트를 위한 목적 이외에도 운동을 전문적으로 하는 사람들에게 오랜기간 사용되어 왔기 때문인 것으로 해석
6. 식욕 억제제 식품군이 긍정점수는 가장 낮고 부정 점수는 가장 높게 나타났는데, 이는 식욕억제제의 주성분인 펜타민에 의한 가능성이 클 것이라고 예측



#### 2. 개발일정 및 개발 인원 소개

개발일정 |  내용  
:---: | --- 
2018-01-02 | 프로젝트 시작
2018-03-03 | 코드완성, 논문 작성
2018-04-05 | 논문 작성 완료
2018-05-12 | 논물 발표, 프로젝트 완료

사용 언어 : R

제작 인원 : 3명 ( 학생2 + 교수1) 

제작 기간 : 4달

협업 방식 : 주 1~2회 미팅, 매일 상황 공유

주요담당: R 코드작성, 수치 계산


#### 3. 프로젝트 개요
1. 분류: 분류된 4가지 카테고리 별 후기를 크롤링(crawling)하여 다이어트 보조 식품에 관한 후기 및 댓글들을 수집
2. 명사화: 세종사전(한글 데이터를 처리하기 위해 만들어진 사전, 이 사전에 등록되지 않은 한글은 처리할 수 없다.)을 기반으로 문장에서 명사만 추출하는 함수를 사용하여 명사를 추출
3. 전처리: 빈칸이나 조사 등의 불필요한 단어가 상위 빈도수를 많이 차지하고 있었기 때문에 데이터 전처리를 통해 데이터를 정제
4. 감성분석:  R 프로그램에서 감성 분석을 실시
5. 다이어트 보조 식품의 그룹별 온라인 평판 분석 실시
6. SNS 댓글과 후기를 참고하여 다이어트를 주제로 한 감성 사전을 구축
   * World Health Organization Adverse Reaction Terminology 에 정의된 부작용을 나타내는 표준 단어들에 가중치를 부과
7. 부정 점수를 산정



### 4. 데이터수집
1. 본 연구는 텍스트 마이닝(Text Mining)을 이용하여 포털 블로그에서 각 다이어트 보조 식품의 장점과 단점 및 부작용을 검색 후, 100여 개의 사용자들의 후기를 스크랩하여 수집
2. 수집 기간은 2018년 2월 5일부터 2018년 3월 11일까지 약 한달 간의 자료를 분석
3. 분류된 4가지 카테고리 별 후기를 크롤링(crawling)하여 분석할 문장의 군집분석
4. 세종사전을 이용하여 명사만 추출
5. 데이터 전처리
6. 데이터 시각화 

* 상위 50개 단어
(A) 포만감을 느끼게 하는 식품: 포만감, 식욕, 변비, 가르니시아 
(B) 식욕을 억제하도록 돕는 식품: 식욕, 지방, 비타민, 구토, 당뇨병
(C) 단백질을 보충해 주는 식품: 건강, 운동, 증가, 탈모
(D) 칼로리 흡수를 저지하는 식품: 차단, 흡수, 마그네슘, 강력, 주의


### 5. 감성사전
1. 감성 사전은 비정형 데이터를 분석하여 긍정, 부정으로 나누어 활용
2. 다이어트 보조 식품에 관련한 상품평을 분석하기 위해 다이어트 보조 식품 사용자들의 어휘를 고려하여 감성 사전을 구축
3. 부정 점수에서 후기나 검색 결과에 부작용 사례가 등장할 때, WHO-ART에 등록되어 있는지 유무를 확인 후 등록되어 있다면 가중치를 주어 계산
4. 다이어트 보조 식품의 후기를 분석하는데 사용된 감성 사전의 가장 큰 특징은 일반적으로 감성분석에서 사용되는 부정의 단어가 본 사전에서는 긍정으로 쓰이고, 긍정의 단어가 부정으로 사용된다는 것
   ‘줄어들다, 식욕부진, 감소하다, 빠지다’ 등의 단어는 일반적으로 부정적인 의미를 가지지만 본 연구에서는 긍정적인 의미로 사용
   ‘증가, 왕성, 늘었다’ 등의 단어가 부정적인 의미로 사용


분류 |  단어  
:---: | --- 
긍정 | 날씬, 가느다란, 추천, 변비탈출, 간편,식욕부진, 성공, 효율적, 줄어들다, 감소하다, 빠지다, 억제, 도움, 원활, 성공, 극대화, 만족, 극복, 체중감량, 재구매
부정 | 거짓, 증가, 별다른, 제자리, 돈낭비, 과대광고, 실망, 없다, 체중증가, 일시적, 요요, 가격부담, 부작용, 무분별, 손상, 피해, 포기, 주의, 과도, 왕성, 내성, 망했다
WHO-ART | 손떨림, 두통, 탈모, 불면증, 우울증, 신경과민, 설사, 탈수, 현기증, 여드름, 소화장애, 무기력, 간손상, 구토, 생리불순, 두드러기, 메스꺼움, 어지러움, 가슴통증, 피로



### 6. 분석결과
1. 각 수치의 평균, 표준편차르 구함
2. 긍정, 부정 점수의 기준치가 다르기 때문에 이후 긍정, 부정 점수를 각각 z-score 정규화하여 비교
3. 단백질 보충 식품군이 긍정 점수가 가장 높게 나타났고, 이는 다이어트를 위한 목적 이외에도 운동을 전문적으로 하는 사람들에게 오랜기간 사용되어 왔기 때문인 것으로 해석
4. 식욕 억제제 식품군이 긍정점수는 가장 낮고 부정 점수는 가장 높게 나타났는데, 이는 식욕억제제의 주성분인 펜타민에 의한 가능성이 클 것이라고 예측

분류 |  A  | B  |	C   | 	D	| 평균	| 표준편차
:---: | --- :---: | --- :---: | --- :---: 
긍정|	12.51|	8.18|	17.26|	8.60|	11.367|	4.23
부정|	9.23|	19.38|	7.30|	7.13|	10.76|	5.83

