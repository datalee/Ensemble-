# python-jieba-keywords

import jieba
import jieba.analyse
#jieba实现提取关键词
content = u'该同学来电反映学校食堂趁刮台风涨价，建议拨打12345'

#基于TF-IDF
keywords = jieba.analyse.extract_tags(content,topK = 10,withWeight = True,allowPOS = ('n','nr','ns'))
for item in keywords:    
    print item[0],item[1] 

#基于TextRank结果：
keywords = jieba.analyse.textrank(content,topK = 10,withWeight = True,allowPOS = ('n','nr','ns'))
for item in keywords:    
    print item[0],item[1]   
