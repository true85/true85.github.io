---
title:  "Python_Module"
layout: single
categories: code
tag: [Python_Module ,Module]
toc: true
use_math: true #수학식 적용여부
author_profile: false #내 프로파일 안보이기
sidebar:
    nav: "docs" 
# search: false #검색불가
---
## colorama 
콘솔에 색입력을 다양히.
Fore : 폰트색
Back : 배경색
Style : 스타일

리셋하지 않음 계속 설정이 유지된다.
```py
from colorama import Fore, Back, Style

print(Back.WHITE + Fore.RED + Style.NORMAL + " TEST " + Style.RESET_ALL)
print(Back.WHITE + Fore.RED + Style.DIM + " TEST " + Style.RESET_ALL)
print(Back.WHITE + Fore.RED + Style.BRIGHT + " TEST " + Style.RESET_ALL)
```
## dlib
: 얼굴찾기

얼굴에 요소를 찾아서 점찍어준다.
```py
detector = dlib.get_frontal_face_detector()
predictor = dlib.shape_predictor('shape_predictor_68_face_landmarks.dat')
```

## os
```py
목표.replace("old","new")
rename(전,후)
os.listdir('path')
```

