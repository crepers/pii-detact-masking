# 개인정보(주민번호) 마스킹 처리 테스트

## Textract
Amazon Textract는 스캔한 문서에서 텍스트, 필기 및 데이터를 자동으로 추출하는 기계 학습(ML) 서비스입니다. 단순한 광학 문자 인식(OCR) 이상으로 양식 및 표의 데이터를 식별하고 이해하며 추출합니다.
[Amazon Textract Code Samples](https://github.com/aws-samples/amazon-textract-code-samples)
[python-textract-textract_wrapper.py](https://docs.aws.amazon.com/ko_kr/code-samples/latest/catalog/python-textract-textract_wrapper.py.html)
 
결과 : 한글이 포함된 문서는 문자 인식률이 너무 낮아서 사용할 수 없었습니다. 한글 문서의 경우 숫자도 거의 확인하지 못했습니다.
 
## Amazon Rekognition
Amazon Rekognition은 이미지 및 비디오에서 정보와 인사이트를 추출하기 위해 사전 훈련된 컴퓨터 비전(CV) 및 사용자 지정 가능한 CV 기능을 제공합니다. Amazon Rekognition - DetectLabels 작업을 사용하여 이미지에서 레이블을 감지할 수 있습니다.
[이미지에서 레이블 감지](https://docs.aws.amazon.com/ko_kr/rekognition/latest/dg/labels-detect-labels-image.html)
DetectText는 이미지에서 최대 100개 단어를 감지할 수 있습니다. 이미지에서 추가로 감지 할 수 있는지는 티켓으로 문의해봐야 합니다.
 
결과 : 양식이 정해져 있고, 주민번호가 문서의 하단에 있기 때문에, 이미지를 거꾸로 회전하여 검색하시면 100자 이내에 주민번호 검색이 가능했습니다. 정규식을 이용하여 마스킹하면 사용이 가능합니다.
   
## 오픈소스 EasyOCR
한글뿐만 아니라 다양한 언어를 지원하고 있고, Demo website에서 테스트 해보니 한글 인식이 잘되서 테스트 했습니다.
[github](https://github.com/JaidedAI/EasyOCR)
[document](https://www.jaided.ai/easyocr/documentation/)
gpu 옵션도 사용이 가능합니다.
 
결과: 한글이 꽤 검출이 잘되었습니다. 한글 또는 정규식을 이용하여 마스킹하면 사용이 가능합니다.
 
