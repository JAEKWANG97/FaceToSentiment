# FaceToSentiment-
얼굴 인식하여 표정 분석 후 감정 도출

이 프로젝트는 Python을 이용하여 비디오 스트림에서 실시간으로 사람의 얼굴을 인식하고, 표정을 분석하는 애플리케이션입니다. OpenCV, dlib, Keras를 활용하여 구현되었습니다.

## 사전 요구사항

프로젝트를 실행하기 전에, 아래의 라이브러리들이 설치되어 있어야 합니다.
먼저 윈도우 관련 설정을 해야하는데 해당 블로그 참고했습니다. https://velog.io/@yimethan/Windows10%EC%97%90-CMake-dlib-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0-Python-3.10

- Python 3.6+
- OpenCV
- dlib
- Keras
- NumPy

먼저, `dlib` 라이브러리를 사용하기 위해서는 `cmake`가 설치되어 있어야 합니다. `cmake`는 다음과 같은 명령어로 설치할 수 있습니다:

```bash
pip install cmake
```

이후, 다음과 같이 필요한 Python 라이브러리들을 설치합니다:

```bash
pip install opencv-python dlib keras numpy
```

## 파일 구성

- `haarcascade_frontalface_default.xml`: OpenCV 얼굴 인식용 Haar Cascade 분류기 파일.
- `shape_predictor_68_face_landmarks.dat`: dlib 얼굴 랜드마크 인식을 위한 학습 모델 파일.
- `emotion_model.hdf5`: 표정을 분류하기 위한 Keras 모델 파일.

## 사용법

1. 모든 종속성이 설치되었는지 확인합니다.
2. 스크립트를 실행합니다:

   ```bash
   python expression_recognition.py
   ```

3. 웹캠이 활성화되고, 프로그램이 얼굴과 표정을 실시간으로 인식하게 됩니다.
4. `ESC` 키를 눌러 프로그램을 종료할 수 있습니다.

## 구현 설명

- **얼굴 인식**: OpenCV의 Haar Cascade 분류기를 사용하여 비디오 스트림에서 얼굴을 인식합니다.
- **표정 인식**: dlib를 사용하여 얼굴의 랜드마크를 찾고, 이를 바탕으로 Keras 모델을 사용하여 표정을 분류합니다.
- **표정 라벨**: 표정은 'Angry', 'Disgust', 'Fear', 'Happy', 'Sad', 'Surprise', 'Neutral'의 7가지로 분류됩니다.
