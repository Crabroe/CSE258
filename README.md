# CSE258: Web Mining and Recommender Systems Assignment2

This repository contains the reference code for the project CSE258: Web Mining and Recommender Systems Assignment2

初步任务：
1. 确定数据集，完成数据可视化，查找相关资料，列出数据特征;
2. 根据数据集来确定算法，课内算法（3个）其他算法（若干个）;

## Dataset推荐（可随时补充）

1. [GoodreadsSpoilers](#GoodreadsSpoilers)
2. [ClothingFitData](#ClothingFitData)

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

数据集总链接：https://mengtingwan.github.io/data/goodreads.html

过滤后数据集链接：https://datarepo.eng.ucsd.edu/mcauley_group/gdrive/goodreads/goodreads_reviews_spoiler.json.gz

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

## NetModel

参考了网络上处理好的数据集，train: test : valid = 8 : 1 : 1 \
使用特征：\
"user_id" : np.array(r['user_id'], dtype=np.int64), \
"cup_size" : np.array(r['cup_size'], dtype=np.int64), \
"user_numeric" : np.array([r['waist'], r['hips'], r['bra_size'], r['height'], r['shoe_size']], dtype=np.float32), \
"item_id" : np.array(r['item_id'], dtype = np.int64), \
"category" :np.array(r['category'], dtype = np.int64), \
"item_numeric" : np.array([r['size'], r['quality']], dtype=np.float32), \
来预测：\
"fit" : np.array(r['fit'], dtype=np.int64)

使用的方法有：MLP, SFNet.

1. MLP训练结果：\
TRAIN Epoch 2 / 2, Mean Total Loss 0.556090235710144 \
VALID Epoch 2 / 2, Mean Total Loss 0.7838857173919678 \
MLP预测结果：\
Metrics: \
 Precision = 0.6192578682183549 \
 Recall = 0.6494140625 \
 F1-score = 0.6293734155069196 \ 
 Accuracy = 0.6494140625 \
 AUC = 0.6799020238170111 

2. SFNet训练结果：\
TRAIN Epoch 20 / 20, Mean Total Loss 0.7175785303115845 \
VALID Epoch 20 / 20, Mean Total Loss 0.7518382668495178 \
SFNet预测结果：\
Metrics: \
 Precision = 0.6396702524325568 \
 Recall = 0.688720703125 \
 F1-score = 0.5702997811215722 \
 Accuracy = 0.688720703125 \
 AUC = 0.6984894609825474 

## Contents

1. [Dataset](#Dataset)
2. [Algorithm](#Algorithm)
3. [Training](#train)
4. [Testing](#test)

## Dataset


## Algorithm


## Training


## Test

