# 5주차 이미지, 음성파일 처리

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

![cat_1](https://github.com/mhg337/-4-Image_SoundFile/assets/144089001/186255c8-0bbf-47cc-b143-45244b6c3ccb)

이미지 회전

        img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg')
        img_rotated = img.rotate(135)
        img_rotated.show()

![cat_2](https://github.com/mhg337/-4-Image_SoundFile/assets/144089001/515f8ed6-db08-493f-a283-1a685078ed94)


이미지 상하, 좌우대칭

상하

        img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg')
        img_flipped_TB = img.transpose(Image.FLIP_TOP_BOTTOM)
        img_flipped_TB.show()

![cat_3](https://github.com/mhg337/-4-Image_SoundFile/assets/144089001/5dffdd2a-30cb-4d08-a009-6f8c6e700d37)

좌우

        img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg')
        img_flipped_LR = img.transpose(Image.FLIP_LEFT_RIGHT)
        img_flipped_LR.show()

![cat_4](https://github.com/mhg337/-4-Image_SoundFile/assets/144089001/ae76924e-4143-4578-88b9-848412fdb0c8)

이미지 필터

블러 효과

        img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg')
        img_blur = img.filter(ImageFilter.GaussianBlur(10))
        img_blur.show()

![cat_5](https://github.com/mhg337/-4-Image_SoundFile/assets/144089001/d7ae63be-90d1-42ee-8b30-91713529dbdd)

윤곽 효과

        img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg')
        img_contour = img.filter(ImageFilter.CONTOUR)
        img_contour.show()

![cat6](https://github.com/mhg337/-4-Image_SoundFile/assets/144089001/16a9f60b-54f5-4fc6-83a3-f49cc1b470d9)

스무스 효과

        img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg')
        img_detail = img.filter(ImageFilter.SMOOTH)
        img_detail.show()

![cat7](https://github.com/mhg337/-4-Image_SoundFile/assets/144089001/b1e6996b-c560-4e0d-8a52-460eb17f79d9)

이미지 합치기

        image1 = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg')

        image2 = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat_3.jpg')

        image1 = image1.resize((450, 163))
        image2 = image2.resize((450, 163))
        image1_size = image1.size
        image2_size = image2.size
        new_image = Image.new('RGB',(2*image1_size[0], image1_size[1]), (250,250,250))
        new_image.paste(image1,(0,0))
        new_image.paste(image2,(image1_size[0],0))
        new_image.show()

이미지 저장

윤곽 효과 저장

        img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg')
        img_contour = img.filter(ImageFilter.CONTOUR)
        img_contour.save('cat_contour.jpg) 
