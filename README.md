## 공부 순서
# 1. NLTK-Setup
- NLTK설치
- 구텐베르크 책에서 세익스 피어의 시저를 토큰화
- NLTK를 이용해서 단어만 추출 이후 문자만(특수문자 제외) .isalnum() 추출
- stopword 이용해서 불용어 사전 다운
- 소문자로 변환한 단어들을 불용어 사전과 비교하여 처리
- FreqDist 이용하여 단어들의 사용빈도 확인
- .most_common() 이용한 빈도수 확인 매개변수 자리에 들어가는 숫자에 따라 보여지는 값이 다르다.
- matplotlib.pyplot이용한 시각화
# 2. tokenization
- 파이썬의 split()과  regex의 spilt()와 nltk.regexp_tokenize을 활용한 tokenize방식이 있음
- nltk.sent_tokenize 통해 문장을 tokenize할 수 있음(마침표 기준 짤라줌)
# 3. normalization
- word_tokenize통한 tokenize
- stemming(어근 찾기) -단어하나를 줄때 한번씩 어근을 찾아줌(반복문 필수)
- PorterStemmer (유명함)
- lemmatization굴절이 일어나기 이전의 어휘를 'lemma'라고 하며 lemma로 복원하는 작업을 lemmatization이라 합니다.
# 4. processing-web-data
- BeautifulSoup4를 통해 html파싱 후.get_text() 메서드를 통한 텍스트 파싱
- 가져온 text를 word_tokenize통해서 tokenize해준다.
- .concordance("문장")통해 문장내 일치 확인
- re.compile통해 regex 규칙을 만든 후 적용
- contraction는 I’ve -> I have로 바꾸는 좋은것
# 5. vectorization
- 문장 사전 만들기
- 벡터화 하는 로직 만들기
- Bag Of Words(단어 빈도수 만들기)
- TF-IDF(중요도)
- sklearn이용한 벡터화(정말 간단)
# 6. sentimental_analysis
- 트위터 csv 가져오기
- 데이터로 그래프 그려보기
- 문장 내부 특수문자 제거
- 불용어 제거
- 단어들 어근화
- Vectorization
- Train_X, Test_X, Train_Y, Test_Y 분리
- LinearSVC모델로 학습시키기
- accuracy_score로 성능확인(prediction, Test_Y)값 비교
# 7. classifying_research
- 순서 
-  데이터 준비(read.csv)
-  데이터 전처리(특수문자 제거->불용어 제거-> 벡터화-> 라벨링)
-  train test값 분리
-  모델소환
-  학습시키기(.fit)
-  accuracy_score로 지표 확인하기
# 8. review_analysis
- 7번과 같은 순서와 모델이지만 모델의 파라미터를 살짝 조정함
# 9. news_summary
- 뉴스 전문 데이터를 가지고 전처리 해보는 것.
- 데이터 읽기
- 결측치 처리
- 뉴스 전문중 첫번째 전문만 가져와서 데이터 처리
- 문장 단위 토큰화-> 특수문자 제거 -> 불용어 처리-> 단어 단위 토큰화-> 어근추출->빈도 확인 -> 가장 높은빈도를 가지고 비율 측정 ->비율 0.5 이상만 출력(자주 쓰이는 단어)
# 10. topic_modeling
- 이 문서는 비지도 학습으로 카테고리 만들어 보는 문서이다.
- 스위트 비즈로 데이터 확인
- ProfileReport로 데이터 확인(개인적으로 좋았음)
- text 데이터 가져와서 전처리-> 벡터화 까지는 동일
- lda 모델 이용한 학습(비지도 학습용 모델)(비지도 학습 이므로 라벨링은 없다.)
- 솔직히 이 다음부터는 이해가 안된다. 그저 학습을 하면 카테고리별 라벨링이 되고 검증할 방법은 없다는 것만 이해함

# 11. chunking-chinking
- 이 문서는 구를 만드는 문서이다.
- 청킹 (Chunking) => 토큰 (token)을 가지고 구(pharase)를 만드는 것
- 만들어진 구(pharase) => chunk라고 함!

# 12. textblob_01
- 이 문서는 textblob에 대한 문서이다
- `textblob`은 `NLTK`를 기반으로 하여 텍스트 처리를 수월하게 할 수 있도록 다양한 기능을 많이 포함하고 있다
- .words 하면 단어단위로 토큰화
- .sentences하면 문자단위로 토큰화
- .tokens 일반적인 토큰화
- .tags 태깅

# 12. textblob_02
- 이 문서는 textblob에 대한 문서이다
- .synsets는 단어를 넣었을때 여러개의 유사단어를 뽑아준다(리스트로)
- .lemmas는 표제어를 추출해준다
- .definitions 단어의 뜻을 뽑아준다
- .path_similarity 유사도를 판단할때 사용한다.
- 조합상 가장 높은 유사성 찾아주는 프로그램

# 12. textblob_03
- 이 문서는 textblob에 대한 문서이다
- 빈도 확인 순서
1. blob 만들기
2. 단어 리스트 만들기
3. 단어 개수 세기
4. 특정 단어 개수 세기
5. WORD SIGN STEM 개수 세기
- .correct 맞춤법 확인 메소드
- .ngrams 단어들 묶어서 가져오기
- 묶은 단어들로 빈도 찾기
- 빈도가 높은 단어 찾기 프로그램
1. 입력받기
2. TextBlob(입력)
3. 문법 검사
4. .word_counts .....(단어 빈도 찾기)
5. max  함수로 딕셔너리중 최대 값 찾기
6. 그에 해당하는 value 출력

# 12. textblob_04
- 이 문서는 textblob에 대한 문서이다
- 감성분석
- .sentiment 결과로 Sentiment(polarity=0.4, subjectivity=0.5)이런 게 나옴
- polarity는 극성(+면 긍정 -면 부정) subjectivity는 주관적인지 확인해줌
- 하지만 이런 메소드는 생각보다 효과가 별로임
- 데이터셋 다운
- 학습용 데이터와 평가용 데이터 다운
- 전처리
- 나이브 베이즈 모델 사용
- 성능은 0.7정도 나옴
- .classify 메소드로 긍부정 분류 
# 12. textblob_05
- 데이터 셋으로 학습시키기
- 현재 계속 오류가 나는데 왜인지는 확인 안됨


#라이브러리 설치 명령어
pip install -r requirements.txt
#가상환경 설치 
python -m venv 가상환경이름
#라이브러리 저장 명령어
pip freeze > requirements.txt