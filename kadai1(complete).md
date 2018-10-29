
フリー素材アイドル「MIKA☆RIKA」 http://mika-rika-free.jp/ よりダウンロードした
フリー画像を原画像とする．この画像は縦544画像，横827画素による正方形のディジタルカラー画像である．

ORG=imread('ex1.png'); % 原画像の入力  
imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込み，表示した結果を図１に示す．

![原画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai1/kadai1_1.JPG?raw=true)   
図1 原画像

原画像を1/2サンプリングするには，画像を1/2倍に縮小した後，2倍に拡大すればよい．

IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大

1/2サンプリングの結果を図２に示す．

![原画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai1/kadai1_2.JPG?raw=true)  
図2 1/2サンプリング原画像

同様に原画像を1/4サンプリングするには，先ほどのサンプリング画像を1/2倍に縮小した後，4倍に拡大すればよい．すなわち，

IMG = imresize(IMG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,4,'box'); % 画像の拡大

とする．1/4サンプリングの結果を図３に示す．

![原画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai1/kadai1_3.JPG?raw=true)  
図3 1/4サンプリング原画像

1/8から1/32サンプリングは，

IMG = imresize(IMG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,8,'box'); % 画像の拡大

IMG = imresize(IMG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,16,'box'); % 画像の拡大

IMG = imresize(IMG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,32,'box'); % 画像の拡大

を繰り返す．サンプリングの結果を図４～６に示す．

![原画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai1/kadai1_4.JPG?raw=true)  
図4 1/8サンプリング原画像

![原画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai1/kadai1_5.JPG?raw=true)  
図5 1/16サンプリング原画像

![原画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai1/kadai1_6.JPG?raw=true)  
図6 1/32サンプリング原画像

このようにサンプリング幅が大きくなると，モザイク状のサンプリング歪みが発生する．
