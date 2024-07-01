# 6장  
텍스트 요약에 관한 부분을 공부함  
요약은 입력과 출력이 모두 seq-to-seq 작업 따라서 인코더-디코더 구조가 어울림  
데이터셋은 대표적으로 CNN/DailyMail 말뭉치 사용  
nltk라는 라이브러리가 문장의 종결과 약어에 등장하는 구두점을 구별해줌  

pipline을 사용해서 원하는 모델을 가져오고, 첫 번째 인자에 무슨 작업을 할 지 적어줌  
>feature-extraction : 특징 추출 (텍스트에 대한 벡터 표현 추출)  
>fill-mask : 마스크 채우기  
>ner : 개체명 인식 (named entity recognition)  
>question-answering : 질의 응답  
>sentiment-analysis : 감정 분석  
>summarization : 요약  
>text-generation : 텍스트 생성  
>translation : 번역  
>zero-shot-classification : 제로샷 분류

GPT-2, T5, PEGASUS 3개의 모델을 가지고 성능을 비교함  

성능 평가를 위해 두 가지 성능 지표 기준이 있음  
>BLEU:생성된 텍스트에서 얼마나 많은 토큰이 참조 텍스트 토큰과 완벽하게 똑같이 정렬됐는지 확인하는 대신  
단어 또는 n-gram을 체크함 따라서 BLEU는 정밀도를 근간으로 하는 지표  
>ROUGE: ROUGE는 높은 재현율이 정밀도보다 훨씬 더 중요한 요약같은 작업을 위해 개발됨  
ROUGE는 참조 텍스트에 있는 N-그램이 생성된 텍스트에 얼마나 많이 등장하는지도 확인

그 뒤 PEGASUS를 삼성에서 만든 데이터로 미세 튜닝 진행하려 했는데 문제 발생  
> * 메모리 이슈: GPU가 한정 되있으니 아껴쓰려했는데 계속 RAM 초과 문제가 발생함
  evaluate_summaries_pegasus 이 함수가 원인으로 생각하고 있음
  사진으로 결과 대체

## 결론  
텍스트 요약은 앞에서 진행한분류 작업에 비해 특수한 어려움이 있습니다.  
정확도 같은 지표를 생성된 텍스트에 적용하지 못합니다. 따라서 새로운 평가 지표가 필요합니다.  
여기서는 BLEU와 ROUGE 지표를 소개 했지만 결국 사람의 판단이 가장 좋은 척도입니다.  
