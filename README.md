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

![cat-323262_640](https://user-images.githubusercontent.com/144089001/277109754-af1632b5-2109-4fe9-a383-62168575ffa5.jpg)

이미지 크기 변경

        img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg')
        img_resized = img.resize((400,300))
        img_resized.show()

이미지 자르기

        img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg')
        img_cropped = img.crop((200,200,500,500))
        img_cropped.show()

이미지 회전

        img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg')
        img_rotated = img.rotate(135)
        img_rotated.show()

이미지 상하, 좌우대칭

상하

        img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg')
        img_flipped_TB = img.transpose(Image.FLIP_TOP_BOTTOM)
        img_flipped_TB.show()

좌우

        img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg')
        img_flipped_LR = img.transpose(Image.FLIP_LEFT_RIGHT)
        img_flipped_LR.show()

이미지 필터

블러 효과

        img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg')
        img_blur = img.filter(ImageFilter.GaussianBlur(10))
        img_blur.show()
