# Computer Vision related

## BGR to RGB
```
import cv2 as cv

def bgr2rgb(bgr):
  return cv.cvtColor(bgr, cv.COLOR_BGR2RGB)
```

## RGB to Grayscale
```
import numpy as np

def rgb2gray(rgb):
  return np.dot(rgb[...,:3], [0.299, 0.587, 0.114])
```


## URL to BGR
```
import requests
import cv2 as cv
import numpy

def get(url, gray=False):
  image = np.asarray(bytearray(requests.get(url).content), dtype="uint8")
  if gray:
      return cv.imdecode(image, cv.IMREAD_GRAYSCALE)
  return cv.imdecode(image, cv.IMREAD_COLOR)
```
