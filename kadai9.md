

# 課題9レポート

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

![濃淡画像](https://github.com/muinus/lecture_image_processing/blob/master/kadai9/kadai9_1.JPG?raw=true)   
図2 白黒濃淡画像  

次にフィルタの効果を視覚的にわかりやすくするために、画像にノイズを添加する。

ORG = imnoise(ORG,'salt & pepper',0.02); 

によって、ノイズが添加された画像を図3に示す。

![濃淡画像2](https://github.com/muinus/lecture_image_processing/blob/master/kadai9/kadai9_2.JPG?raw=true)   
図3 白黒濃淡画像(ノイズ添加) 

最初に平滑化フィルタによって雑音除去を行う。

IMG = filter2(fspecial('average',3),ORG);

によって、フィルタを通した画像を図4に示す。

![平滑化フィルタ](https://github.com/muinus/lecture_image_processing/blob/master/kadai9/kadai9_3.JPG?raw=true)   
図4 白黒濃淡画像(平滑化フィルタ適応) 

2番目はメディアンフィルタによって雑音除去を行う。

IMG = medfilt2(ORG,[3 3]);  

によって、画像内の3×3の正方形の画素を抽出し、真ん中の値を9つの画素の中央値と同値とする。
このようなフィルタを通した画像を図5に示す。

![メディアンフィルタ](https://github.com/muinus/lecture_image_processing/blob/master/kadai9/kadai9_4.JPG?raw=true)   
図5 白黒濃淡画像(メディアンフィルタ適応)

最後に自分でフィルタを設計して、画像を通した。

f=[0,-1,0;-1,5,-1;0,-1,0];  
IMG = filter2(f,IMG,'same');  

によってフィルタを作成し、画像をフィルタに通した。
表示された画像を図6に示す。

![メディアンフィルタ](https://github.com/muinus/lecture_image_processing/blob/master/kadai9/kadai9_5.JPG?raw=true)   
図6 白黒濃淡画像(自作フィルタ適応)

図4、図5、図6を見比べると図5が最も図2と類似しており、ノイズ除去に成功したといえる。
