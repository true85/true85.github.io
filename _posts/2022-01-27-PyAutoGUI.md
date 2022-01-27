---
title:  "PyAutoGUI"
layout: single
categories: code
tag: [PyAutoGUI]
toc: true
use_math: true #수학식 적용여부
author_profile: false #내 프로파일 안보이기
sidebar:
    nav: "docs" 
# search: false #검색불가
---
## PyAutoGUI

### 마우스 죄표 출력

```py
import pyautogui as pag

while True:
    x,y=pag.position()
    positionStr = 'X: ' + str(x).rjust(4) + ' Y: ' + str(y).rjust(4)
    print(positionStr)
```
왼쪽 위가 0 , 0
ctr + c 로 창 정지
### 마우스 클릭
```py
import pyautogui as pag

def click(x, y):
  pag.moveTo(x=x, y=y, duration=0.0)
  pag.mouseDown()
  # time.sleep(random.uniform(0.0101, 0.0299))
  pag.mouseUp()
```
