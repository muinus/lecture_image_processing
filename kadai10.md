
# 課題10レポート

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

![濃淡画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai10/kadai10_1.JPG?raw=true)   
図2 白黒濃淡画像  

まず、プレイウィット法を使用してエッジ抽出した。

IMG = edge(ORG,'prewitt');

によって、エッジを抽出した画像を図3に示す。


![プレイウィット法](https://github.com/muinus/lecture_image_processing/blob/master/kadai10/kadai10_2.JPG?raw=true)   
図3 エッジ抽出(プレイウィット法) 

次に、ソベル法を使用してエッジ抽出した。

IMG = edge(ORG,'sobel'); 

によって、エッジを抽出した画像を図4に示す。


![ソベル法](https://github.com/muinus/lecture_image_processing/blob/master/kadai10/kadai10_3.JPG?raw=true)   
図4 エッジ抽出(ソベル法)


最後に、キャニー法を使用してエッジ抽出した。

IMG = edge(ORG,'canny'); 

によって、エッジを抽出した画像を図5に示す。

![キャニー法](https://github.com/muinus/lecture_image_processing/blob/master/kadai10/kadai10_4.JPG?raw=true)   
図5 エッジ抽出(キャニー法)

