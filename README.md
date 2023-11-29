# CSE258: Web Mining and Recommender Systems Assignment2

This repository contains the reference code for the project CSE258: Web Mining and Recommender Systems Assignment2

初步任务：
1. 确定数据集，完成数据可视化，查找相关资料，列出数据特征;
2. 根据数据集来确定算法，课内算法（3个）其他算法（若干个）;

## Dataset推荐（可随时补充）

0. [GoodreadsSpoilers](#GoodreadsSpoilers)
0. [ClothingFitData](#ClothingFitData)

## GoodreadsSpoilers

数据集格式：
\{
  'user_id': '01ec1a320ffded6b2dd47833f2c8e4fb',                                                               
  'timestamp': '2013-12-28',                                                                                   
  'review_sentences': [[0, 'First, be aware that this book is not for the faint of heart.'],                   
   [0, 'Human trafficking, drugs, kidnapping, abuse in all forms - this story contains all of this and more.'],
   ...,                                                                                                        
   [0, '(ARC provided by the author in return for an honest review.)']],                                       
  'rating': 5,                                                                                                 
  'has_spoiler': False,                                                                                        
  'book_id': '18398089',                                                                                       
  'review_id': '4b3ffeaf14310ac6854f140188e191cd'
\}

特征："review_sentences"、('user_id')、('book_id')

标签：0,1

可定义分类任务： 预测二分类--是否剧透

参考论文地址：https://cseweb.ucsd.edu/~jmcauley/pdfs/acl19.pdf

数据集大小：592MB

问题：是否需要根据用户做个性化订制，不做是否有其他问题

## ClothingFitData

数据集1格式：
\{
  "fit": "fit",
  "user_id": "420272",
  "bust size": "34d",
  "item_id": "2260466",
  "weight": "137lbs",
  "rating": "10",
  "rented for": "vacation",
  "review_text": "An adorable romper! Belt and zipper were a little hard to navigate in a full day of wear/bathroom use, but that's to be expected. Wish it had pockets, but other than that-- absolutely perfect! I got a million compliments.",
  "body type": "hourglass",
  "review_summary": "So many compliments!",
  "category": "romper",
  "height": "5' 8\"",
  "size": 14,
  "age": "28",
  "review_date": "April 20, 2016"
\}

特征："bust size"、"height"、"weight"、"age"、"body type"、"category"、"size"、("review_text")

数据集2格式：
\{'item_id': '123373',
 'waist': '30',
 'size': 7,
 'quality': 2,
 'cup size': 'b',
 'shoe size': '9.00',
 'bra size': '32',
 'category': 'new',
 'length': 'slightly long',
 'height': '5ft 7in',
 'user_name': 'Ugggh',
 'fit': 'small',
 'user_id': '395665'
 \}

特征："waist"、"cup size"、"shoe size"、"bra size"、"length"、"height"、"size"、"category"

标签：small/fit/large

可定义分类任务： 预测二分类--是否fit/预测多分类--small/fit/large

参考论文地址：https://cseweb.ucsd.edu/~jmcauley/pdfs/recsys18e.pdf

数据集大小：40MB

问题：参考论文用的方法有点抽象

## Contents

0. [Dataset](#Dataset)
0. [Algorithm](#Algorithm)
0. [Training](#train)
0. [Testing](#test)

## Dataset


## Algorithm


## Training


## Test

