# 7장-질문 답변

**아쉬운 점**
* 코랩 버전이 업데이트 되면서 책에서 제공하는 코랩 코드를 아예 못씀 그래서 그냥 파일 다운받아서 내가 주석다는 식으로 공부를 진행

아마 제일 공부가 많이 필요한 장 이 아니였나 생각함  
특히 **RAG**를 설명해주는 부분이 있어서 집중해서 공부를 진행함  

본 적 없는 데이터 셋을 사용하고 라이브러리를 사용해서(특히 Popen 같이 서브 프로세스 라이브러리가 갑자기 나와서 당황) 어려웠음  
정말 많은 개념들이 등장  
세계적으로 많이 쓰이는 SQuAD 2.0 데이터 셋 소개하고 이에 맞게 사전 학습된 모델 설명 책에서는 MiniLM 사용  
긴 문장을 위한 슬라이딩 윈도우 개념 설명  
**리트리버-리더 구조 설명** 이게 이 장의 가장 큰 중요한 개념 
리트리버는 희소 리트리버와 밀집 리트리버 존재 그중 BM25 사용 (희소 리트리버)  
그리고 검색 엔진은 일래스틱서치 사용  
리더는 일반적으로 사전 학습된 모델 사용 여기서는 위에 나온 MiniLM 사용  
그리고 BM25와 다른 밀집 리트리버에서 DPR 소개  
2개의 BERT를 사용하여 질문 인코더와 문맥 인코더로 사용  

평가하는 방법은 EM과 F1 두 가지 방법을 설명



# RAG의 기본 설명

RAG가 현업에서 자주 찾는 지원 자격이므로 복습하며 공부하기
