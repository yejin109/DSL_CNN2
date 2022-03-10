# 폴더 / 파일 설명


## 폴더 

- data

크롤링한 데이터 혹은 오픈 소스 데이터셋을 포함하고 있습니다. <br>
우선 예시로 사진 3개정도 넣어둔 상태입니다. <br>
추후에 하위 폴더로 크롤링한 것, 마스킹&라벨링한 것 구분해서 보관해도 될 것 같습니다!

- jupyter

주피터 파일들 보관하는 폴더입니다.<br>
크롤링코드랑 함께 추가적인 설명이 필요한 경우 jupyter로 작성해서 보관하시면 될 것 같습니다!

- save

이전에 간단하게 pretrained 모델 테스트해보고 마스킹결과 보관하려고 만든 폴더입니다! <br>
중간중간에 이미지 파일 저장하거나 결과물들 보관할 때 사용하시면 될 것 같습니다. <br>
추후에 하위 폴더로 테스트하고 시각화 체크하는 거나 테스트 로그 폴더 같은거 정리해도 좋을 것 같습니다!

- util

Mask R CNN 구현하다보면 일부 기능들을 함수나 클래스로 정리한 것들 보관하는 폴더입니다!<br>
일단 utils라는 파이썬 파일로 모아뒀는데 이해하기 편하게 세분화해서 나눠도 될 것 같습니다.

## 파일

- config.py

중간중간에 학습시키거나 class 이름 등 상수값들 모아둔 파일입니다.<br>
하이퍼파라미터나 모델 구조 등 값들을 지정해야하는 경우 해당 파일에서 한번에 관리하고, 다른 소스코드에선 config를 import해서 사용하도록 한다면 다른 파일에서 함께 사용하는 값들은 유지, 보수하기에 좋을 것 같습니다.

- dataset.py

torch의 Dataset을 상속하는 클래스들을 모아두는 파일입니다.<br>

직접 크롤링한 데이터나 오픈 소스 데이터마다 구조가 조금씩 달라질 수 있을 것 같아 구분하고 있습니다. 프로토타입으로 정리되어 있으며 추후에 업데이트 하면 좋을 것 같습니다.
 - ImgDataset : 크롤링한 데이터의 Dataset 클래스입니다.
 - FashionDataset : 오픈소스 데이터셋(ex. DeepFashion2 Dataset) 사용에 필요한 Dataset 클래스입니다. 해당 코드는 데이콘에서 공유된 [코드](https://dacon.io/competitions/official/235672/codeshare/1795?page=1&dtype=recent)를 가져온 것입니다. 커스터마이징할 때 참고해도 좋을 것 같습니다.

- mask_rcnn.py

전체 프로세스를 작성한 소스코드입니다.<br>
 - Model / Dataset 로드
 - Train
 - Test

의 간단한 구조로 정리했으며 이 파일 또한 앞서 데이콘에서 공유된 코드를 참고하여 정리해둔 것입니다. 저희가 사용할 때엔 알맞는 형태로 정리해서 사용하면 될 것 같습니다.

