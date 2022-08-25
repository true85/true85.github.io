---
title:  "Python package"
layout: single
categories: code
tag: [Python]
toc: true
use_math: true #수학식 적용여부
author_profile: false #내 프로파일 안보이기
sidebar:
    nav: "docs" 
# search: false #검색불가
---

# Python 정리 
(참고)[https://wikidocs.net/84381]



## package

### package
모듈
```py
# foo.py
def grok(a):
    ...
def spam(b):
    ...
```

```py
import foo

a = foo.grok(2)
b = foo.spam('Hello')
```
패키지 :
모듈의 모음
```
setup.py
readme.txt
requirments.txt
script.py
    porty/
        __init__.py
        pcost.py
        report.py
        fileparse.py
    test/
        __init__.py
        test.py
```
```py
#script.py
import porty.pcost
a = porty.pcost.mean(3,4)
or
from porty import pcost
b = pcost.mean(3,4)
```
#### __init__.py
디렉토리에 이 파일이 있어야 패키지로 생각한다.
'from [package_name] import [module_name]'
#### setup.py
디렉토리에 이 파일이 있어야 프로젝트로 생각한다.
```py
#setup.py
import setuptools

setuptools.setup(
    name = "porty",
    version = "0.0.2",
    author = "name",
    author_email = "abc@aaa.com",
    description = " text ",
    packages=setuptools.find_packages(),
)
```

|Arguments	|Description|
|:---|---:|
|name|	패키지의 이름|
|version|	패키지의 배포 버전|
|description|	패키지에 대한 설명|
|url|	패키지를 대표하는 웹페이지|
|author|	패키지의 작성자|
|license|	패키지의 라이센스|
|packages|	프로젝트에 포함되는 패키지 리스트|
|install_requires|	실행 환경에 필요한 최소한의 패키지 리스트|
|python_requires|	실행 환경에 필요한 파이썬 버전|

### 배포
'python setup.py abc'
abc 폴더에 zip이나 tar.gz 생성

'pip install porty-0.0.2.tar.gz'
설치

### freeze
```py
pip freeze > requirement.txt
# 텍스트로 리스트 출력
pip install -r requirements.txt
# 저장된 목록 설치
```