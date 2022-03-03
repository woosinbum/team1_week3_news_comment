# week3-news-comment

## 뉴스 기사의 댓글 (comment) 중 편견, 혐오 표현 (bias, hate)이 포함된 댓글을 식별하는 과제

자연어 처리 과제는 대기업에서 대량의 데이터를 학습시킨 모델이 성능이 잘나온다고 알고 있어서 pretrained 된 모델을 잘 찾으려고 노력했습니다.
bert 모델이 전반적으로 text classification에 성능이 좋다는 것을 배워서 한국어로 pretrained 된 kcbert 와 koelectra 모델을 중점으로 성능평가를 
하였습니다. 데이터를 확인하였을 때 기사 제목에 종합,이슈,쎈 같은 언론사 이름이 많이 나오는 것을 확인하였고 이런 것들은 정규표현식으로 제거해주었습니다. pykospacing, hanspell, soynly 라이브러리를 이용해서 댓글의 맞춤법,띄어쓰기, 반복문을 전처리 후 학습 자료로 사용하였습니다.
koelectra v3 model이 최신에 업데이트 되어 성능이 잘나올 것 같았지만 kcbert가 오히려 더 좋은 성능을 보여주었습니다. hugging face 사이트에서 hate speech와 bias speech 에 특화되어 pretrained 된 모델을 찾아서 이 모델에 맞게 output 값과 label을 수정하여 모델학습을 진행하였습니다. 실제로 이 모델을 쓸 때 validation_accuracy 값이 좋아지는 것을 보고 config 파일을 고쳐가며 실험해보았습니다.

## 파일
nlp_eda 파일은 데이터 전처리를 할 때 썼던 코드입니다.
baseline_koelectra_v3 파일은 config를 바꿔가며 bert 모델과 koelectra_v3 모델을 평가할 때 썼던 파일입니다.
nlp_baseline_v3_normalized_bias,hate 파일은 hugginface 모델에 맞춰서 베이스라인 코드를 수정한 코드입니다.

## 모
