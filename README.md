# lda_topic_modeling

1. **기간 : 2020.06~2020.11**

2. **기술스택 : python, pickle, gensim, lda_modeling, corpora**

3. **내용 : 문서의 주제가 무엇인지 위키피디아로 학습한 lda모델을 이용하여 판단**
    1. 위키피디아 데이터를 단어단위로 자르고 문서별로 태깅.
    2. 불용어 제거
    3. corpora를 이용하여 단어단위 corpus, dictionary 변수 만듬
    4. 학습 및 학습으로 부터 추출한 주제 태깅
    5. 모델 테스트 및 불용어 존재시 2로 돌아가서 다시 반복
    
4. **파일설명**  
![스케치](https://user-images.githubusercontent.com/50386280/107105255-a93a7480-6868-11eb-917e-dc46bd4f730a.png)

    1. 1_remove_stopword.ipynb  
        **[input file : data.p, kor_stopword2.csv]**  
        **[output file : data]**
        - 위키피디아 문서들(data.p)을 불러와서 불용어(kor_stopword2.csv)들을 제거하고 data폴더에 10만개씩 저장  
    2. 2_make_pandas_series_learning.ipynb  
        **[input file : data]**  
        **[output file : dictionary.pickle, corpus.pickle]**  
        - 같은번호로 태깅된 문장들(같은 문서에 있는 문장들)을 하나의 리스트로 묶기
        - gensim라이브러리에 corpora를 이용하여 lda모델 학습을 위한 단어단위 corpus만들기  
    3. 3_learning.ipynb  
        **[input file : dictionary.pickle, corpus.pickle]**  
        **[output file : lda_model120.pickle]**  
        - gensim라이브러리 이용하여 ldamodel학습  
        - 주제별 단어의 가중치 확인  
        - 주제를 구성하는 단어들 중 불용어가 있으면 불용어를 제외하여 다시 학습  
    4. 4_show_20_topic.ipynb  
        **[input file : lda_model20.pickle, test.txt]**  
        - 확인하고 싶은 txt파일 불러오기  
        - txt파일 corpus분해  
        - lda모델 이용하여 주제 추출  
        
        
        
