# 4주차 이미지, 음성파일 처리

라이브러리 불러오기

from PIL import Image
from PIL import ImageFilter
from PIL import Image
import numpy as np
import matplotlib.pyplot as plt
import os , sys
from PIL import Image

이미지 불러오기
img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg')
img_resized = img.resize((400,300))
img_resized.show()
