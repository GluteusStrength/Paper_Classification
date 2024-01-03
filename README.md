# paper classification
### Task, dataset
- 과학기술표준분류의 중분류로 주제 분류를 정확히 하는 모델 개발
- multi-class classification(total 365 classes)
- dataset: 논문 연구분야 분류 데이터
  
`input` - 국내 논문 전문 텍스트
<br>
`output` - 과학기술표준 **'중분류'**

### Training
**KoBERT**
- pretrained model for korean(SKT Brain team)

**Vocab Customizing**
- 가설: 각 class 별로 논문 텍스트를 바탕으로 새로운 vocab 사전을 만드는 편이 논문이라는 특수한 성격의 데이터를 분류하는 데 있어서 성능 향상에 도움이 될 것이다.
- BertWordPieceTokenizer → 새로운 vocab dictionary → 학습 시 이용

**Class Imbalance**
- Weighted Cross Entropy Loss 이용

**Score**
- Accuracy: 0.598
- Precision(macro): 0.505
- Recall(macro): 0.569
