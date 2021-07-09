![comp](./info/001.png)
# atmacup11
atmacup#11 美術作品の年代予測

# Table of content
- [Basic](#Basic)
- [Log](#Log)
    - [20210709](#20210709)
   

# Basic

## info

### 予測対象について

予測対象は、train.csvのtarget　{0, 1, 2, 3}

**美術作品の年代カテゴリ**

代表年を x としたとき、ルールは以下のとおりです。

- 16世紀以前 (x <= 1600): 0
- 17世紀 (1601 < x <= 1700): 1
- 18世紀 (1701 < x <= 1800): 2
- 19世紀以降 (1800 < x): 3



## Evaluation
評価指標はRMSE.


## Datasets
- train.csv : size(3937, 4)
- test.csv : size(5919, 1)
- photos.zip
- materials.csv : size(9081, 2)
- techniques.csv : size(3777, 2)

# Log

## 20210709
- join！！！
- data download

- sorting_dateとtargetの違い(train.csv)
    - sorting_dateから年代分けられるんじゃないの？と思ったけど、test.csvにsorting_dateカラムがないみたい。
    - test.csvにはobject_idのみ
    - つまり、test.csvのobject_idから作品画像を読み込む→画像の特徴から年代を予測するということか。
    
- nb001
    - "counterproof"という技法、「版画」という意味らしい。
    - trainのデータ、18世紀の作品が最も多いらしい。次いで、１９世紀以降、１７世紀、１６世紀以前の順に多い。
    
|作品代表年(train)|target(train)|
|---|---|
|![](./info/002.png)|![](./info/003.png)|
    
