# 課題6レポート

フリー素材アイドル「MIKA☆RIKA」 http://mika-rika-free.jp/ よりダウンロードしたフリー画像を原画像とする．
この画像は縦1084画像，横1692画素によるディジタルカラー画像である．

ORG=imread('org.png'); % 原画像の入力  
imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込み，表示した結果を図１に示す．

![原画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai1/kadai1_1.JPG?raw=true)   
図1 原画像  


まずは原画像を白黒濃淡画像に変換する。

ORG = rgb2gray(ORG);  

によって、白黒濃淡画像に変換し、表示した結果を図2に示す．

![濃淡画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai6/kadai6_1.JPG?raw=true)   
図2 白黒濃淡画像  

今回は通常の閾値を使った2値化とディザ法による2値化を行う。

最初に通常の閾値を使った2値化を行う。閾値を中央値である128とする。

IMG = ORG>128; % 128による二値化  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  

によって2値化された画像を図3に示す。

![2値画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai6/kadai6_2.JPG?raw=true)   
図3 通常の閾値による2値化画像  

今度はディザ法を使った2値化を行う。ディザ法とはあらかじめ決められた画像の位置ごとの閾値が決まったフィルター（ディザマトリクス）と画像を比較し、その大小関係で出力画像の濃度値を決定する方法である。

IMG = dither(ORG); % ディザ法による二値化  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

によって2値化された画像を図4に示す。

![ディザ2値画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai6/kadai6_3.JPG?raw=true)   
図4 ディザ法による2値化画像  
