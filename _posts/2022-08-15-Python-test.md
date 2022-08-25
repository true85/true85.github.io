---
title:  "Python test"
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



## Test
### repr
print(repr(x)) :
더 많은 정보를 볼수 있다.
### assert
참이 아니면 AssertionError 발생
```py
assert <표현식> [,'진단메세지']
assert isinstance(10,int), 'Expected int'
```
### unittest
단위 테스트
```py
import unittest
```

## logging
```py
import logging
```

## debuging
`breakpoint()`