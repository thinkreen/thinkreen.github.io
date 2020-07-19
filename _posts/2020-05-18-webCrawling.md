---
title: "Web Crawling by Selenium"
categories: 
    - "Machine Learning"
tags:
    - "Machine Learning"
    - "Python"
    - "Crawling"
last_modified_at: 2020-07-01T12:00:00+09:00
toc: true
---

## Google image downloads

2020년 2월부터 Google DOM 변경으로 인하여 google_images_downloads대체를 위하여 Selenium을 사용한 gids 패키지를 이용하여 이미지를 추출한다.

### Install
```
pip install gids
```

### Example code



```python
from gids import builder

config = {
    'driver_path': '/usr/local/bin/chromedriver',
    'headless': True,
    'window-size': '720x480',
    'disable_gpu': False
}

first_item = {
    'keyword': 'White Shark',
    'limit': 10, # The number of images
    'download_context': './data',
    'path': 'animal' # save in ./data/animal/img_01...10
}

second_item = {
    'keyword': 'Whale Shark',
    'limit': 10, # The number of images
    'download_context': './data',
    'path': 'Shark' # save in ./data/plant/img_01...10
}

items = [first_item, second_item]

downloader = builder.build(config)

downloader.download(items)
```

    Loading Pages. This may take a few moments...
    Page Scroll done...
    Start to downloading
    Downloading ...White Shark - [./data/animal/White Shark/img_0]
    Downloading ...White Shark - [./data/animal/White Shark/img_1]
    Downloading ...White Shark - [./data/animal/White Shark/img_2]
    Downloading ...White Shark - [./data/animal/White Shark/img_3]
    Downloading ...White Shark - [./data/animal/White Shark/img_4]
    Downloading ...White Shark - [./data/animal/White Shark/img_5]
    Downloading ...White Shark - [./data/animal/White Shark/img_6]
    Downloading ...White Shark - [./data/animal/White Shark/img_7]
    Downloading ...White Shark - [./data/animal/White Shark/img_8]
    Downloading ...White Shark - [./data/animal/White Shark/img_9]
    White Shark download completed. [Successful count = 10].
    Loading Pages. This may take a few moments...
    Page Scroll done...
    Start to downloading
    Downloading ...Whale Shark - [./data/Shark/Whale Shark/img_0]
    Downloading ...Whale Shark - [./data/Shark/Whale Shark/img_1]
    Downloading ...Whale Shark - [./data/Shark/Whale Shark/img_2]
    Downloading ...Whale Shark - [./data/Shark/Whale Shark/img_3]
    Downloading ...Whale Shark - [./data/Shark/Whale Shark/img_4]
    Downloading ...Whale Shark - [./data/Shark/Whale Shark/img_5]
    Downloading ...Whale Shark - [./data/Shark/Whale Shark/img_6]
    Downloading ...Whale Shark - [./data/Shark/Whale Shark/img_7]
    Downloading ...Whale Shark - [./data/Shark/Whale Shark/img_8]
    Downloading ...Whale Shark - [./data/Shark/Whale Shark/img_9]
    Whale Shark download completed. [Successful count = 10].
    Total time is 36.451616048812866 seconds.


## Troubleshooting

아래와 같이 에러가 나올 때 chromedriver파일이 있는 디렉토리로 PATH를 설정해줌.

No found chromedriver in this environment.
Install on your machine. exception: Message: 'chromedriver' executable needs to be in PATH. Please see https://sites.google.com/a/chromium.org/chromedriver/home

```
export PATH=$PATH:/usr/local/bin/chromedriver
```


```python

```
