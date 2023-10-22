# 5주차 이미지, 음성파일 처리

## 이미지 처리


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

![cat_+](https://github.com/mhg337/-5-Image_SoundFile/assets/144089001/d33458a8-834b-474c-a8f6-78f510cfb9ed)

이미지 저장

- 윤곽 효과 저장

        img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg')
        img_contour = img.filter(ImageFilter.CONTOUR)
        img_contour.save('cat_contour.jpg) 

이미지를 바이트 배열로 변환

        img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg', mode='r')

        buffer = io.BytesIO()
        img.save(buffer, format='PNG')
        buffer.seek(0)
        #결과 : <_io.BytesIO object at 0x000001E4A29AF830>

넘파이 배열을 이미지로 변환

        img = Image.open(r'C:\Users\PC\OneDrive\문서\GitHub\-4-Image_SoundFile\cat-323262_640.jpg', mode='r')
        img_np = np.array(img) #이미지를 Numpy 배열로 변환
        im = Image.fromarray(img_np)
        im.show()

![cat_8](https://github.com/mhg337/-5-Image_SoundFile/assets/144089001/fadf114f-5e52-46f3-8050-05eaf6b36bfa)

## 음성 파일 처리

- 라이브러리 불러오가
    
      import soundfile as sf
      import pydub
      import librosa
      import librosa.display
      import IPython.display as ipd
      import numpy as np
      import matplotlib.pyplot as plt

- 음성 파일을 읽고 재생, 메타정보를 출력

      file_path = r"C:\Users\PC\OneDrive\문서\GitHub\-5-Image_SoundFile\Monologue.mp3"

      data, sample_rate = sf.read(file_path)

      print("Sample Rate:", sample_rate)
      print("Duration:", len(data) / sample_rate, "seconds")

      audio = pydub.AudioSegment.from_file(file_path)
      audio.play()

- 음성파일 Hz 변환

      sf.write('./' + '16k.wav' , y, origin_sr, format='WAV', endian='LITTLE', subtype='PCM_16')
      sf.write('./' + '8k.wav', resample, resample_sr, format='WAV', endian='LITTLE', subtype='PCM_16'

- 음성파일 그려보기


      def down_sample(r"C:\Users\PC\OneDrive\문서\GitHub\-5-Image_SoundFile\Monologue.wav", origin_sr, resample_sr):
          y, sr = librosa.load(input_wav, sr=origin_sr)
          resample = librosa.resample(y, sr, resample_sr)

      plt.figure(figsize=(10, 4))
      plt.subplot(2, 1, 1)
      time1 = np.linspace(0, len(y) / sr, len(y))
      plt.plot(time1, y)
      plt.title('Original Wav')

      plt.subplot(2, 1, 2)
      time2 = np.linspace(0, len(resample) / resample_sr, len(resample))
      plt.plot(time2, resample)
      plt.title('Resampled Wav')

      plt.tight_layout()

- 음성파일 변환 후 시각

  푸리에 변환

      file_path = r"C:\Users\PC\OneDrive\문서\GitHub\-5-Image_SoundFile\Monologue.wav"
      y, sr = librosa.load(file_path)
      D = librosa.stft(y)
      plt.figure(figsize=(16,6))
      plt.plot(D)
      plt.show()

  스펙트그램 변환

      file_path = r"C:\Users\PC\OneDrive\문서\GitHub\-5-Image_SoundFile\Monologue.wav"
      y, sr = librosa.load(file_path)
      D = librosa.amplitude_to_db(np.abs(librosa.stft(y)), ref=np.max)
      plt.figure(figsize=(10, 6))
      librosa.display.specshow(D, sr=sr, x_axis='time', y_axis='log')
      plt.colorbar(format='%+2.0f dB')
      plt.title('스펙트로그램')
      plt.show()

- 음성파일 잘라서 저장

      def trim_audio_data(audio_file, save_file):
          sr = 96000
          sec = 30

          y, sr = librosa.load(audio_file, sr=sr)

          ny = y[:sr*sec]

          librosa.output.write_wav(save_file + '.wav', ny, sr)

      base_path = 'dataset/'

      audio_path = base_path + '/audio'
      save_path = base_path + '/save'

      audio_list = os.listdir(audio_path)

      for audio_name in audio_list:
          if audio_name.find('wav') is not -1:
              audio_file = audio_path + '/' + audio_name
              save_file = save_path + '/' + audio_name[:-4]

              trim_audio_data(r"C:\Users\PC\OneDrive\문서\GitHub\-5-Image_SoundFile\Monologue.mp3", r"C:\Users\PC\OneDrive\문서\GitHub\-5-Image_SoundFile\Monologue_modification.mp3")
