---
title: Python常用工具
description: Python常用小工具记录
date: 2023-05-12 1:0:00
updated: 2023-05-12 1:0:00
tags:
  - Python
categories:
  - 开发
swiper_index: 1 # 置顶权重
---


## 文件读写

~~~python
with open('xxx.txt', 'w', encoding='utf-8') as f:
	f.write('xxx' + '\n')
    f.close()
~~~



## 爬虫

> 代码案例

~~~python
from bs4 import BeautifulSoup
import requests

def getHTMLText(url):
    try:
        headers = {
            'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/67.0.3396.99 Safari/537.36'}
        res = requests.get(url, headers=headers)
        res.raise_for_status()
        res.encoding = res.apparent_encoding
        return res.text
    except:
        return 'error'

def get_info(url):
    demo = getHTMLText(url)
    soup = BeautifulSoup(demo, 'html.parser')
    table = soup.find('table', {'class': 'rk-table'})
    tbody = table.find('tbody')
    rows = tbody.find_all('tr')
    for row in rows:
        tds = row.find_all('td')
        rank = tds[0].text.strip()
        name = row.find('a').text.strip()
        location = tds[2].text.strip()
        total = tds[4].text.strip()
        data = {
            '排名': rank,
            '学校名称': name,
            '省市': location,
            '总分': total
        }
        print(data)


url_2020 = 'https://www.shanghairanking.cn/rankings/bcur/2020'
url_2021 = 'https://www.shanghairanking.cn/rankings/bcur/2021'
get_info(url_2021)
~~~



## 数据库管理

~~~python
import pymysql

conn=pymysql.connect(host = '127.0.0.1' # 连接名称，默认127.0.0.1
,user = 'root' # 用户名
,passwd='123456' # 密码
,port= 3306 # 端口，默认为3306
,db='python' # 数据库名称
,charset='utf8' # 字符编码
)
cur = conn.cursor() # 生成游标对象
if cur:
    print('数据库连接成功')
sql="select * from `web` " # SQL语句
cur.execute(sql) # 执行SQL语句
data = cur.fetchall() # 通过fetchall方法获得数据
for i in data[:1]: # 打印输出1条数据
    print(i)
cur.close() # 关闭游标
conn.close() # 关闭连接
~~~



## 爬虫案例（写入数据库）

> 实例

~~~python
import json
import re
import pymysql
import requests

conn = pymysql.connect(host='127.0.0.1'  # 连接名称，默认127.0.0.1
                       , user='root'  # 用户名
                       , passwd='123456'  # 密码
                       , port=3306  # 端口，默认为3306
                       , db='python'  # 数据库名称
                       , charset='utf8'  # 字符编码
                       )
cur = conn.cursor()  # 生成游标对象


def getHTMLText(url):
    try:
        headers = {
            'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/67.0.3396.99 Safari/537.36'}
        res = requests.get(url, headers=headers)
        res.raise_for_status()
        res.encoding = res.apparent_encoding
        return res.text
    except:
        return 'error'


def main(url):
    res = getHTMLText(url)
    regex = re.compile(r"(?=\()(.*)(?<=\))")
    jsonString = regex.findall(res)[-1]
    jsonString = jsonString.strip('()')
    jsonData = json.loads(jsonString)
    diffValue = jsonData['data']['diff']
    for i in range(len(diffValue)):
        demo = diffValue[i]['f12']
        name = diffValue[i]['f14']
        sql = "INSERT INTO money(demo,name) VALUES ('{}', '{}');".format(demo, name)
        cur.execute(sql)
        conn.commit()
        print(demo+name)
    cur.close()
    conn.close()


url = 'http://85.push2.eastmoney.com/api/qt/clist/get?cb=jQuery1124007516892373587614_1682312504170&pn=1&pz=20&po=1&np=1&ut=bd1d9ddb04089700cf9c27f6f7426281&fltt=2&invt=2&wbp2u=|0|0|0|web&fid=f3&fs=m:0+t:6,m:0+t:80,m:1+t:2,m:1+t:23,m:0+t:81+s:2048&fields=f1,f2,f3,f4,f5,f6,f7,f8,f9,f10,f12,f13,f14,f15,f16,f17,f18,f20,f21,f23,f24,f25,f22,f11,f62,f128,f136,f115,f152&_=1682312504458'
main(url)
~~~



## 图片转文字画

~~~python
import numpy as np
from PIL import Image
import time

if __name__ == '__main__':
    start_time = time.time()
    image_file = 'lena.png'
    height = 100

    img = Image.open(image_file)
    img_width, img_height = img.size
    width = int(1.8 * height * img_width // img_height)
    img = img.resize((width, height), Image.ANTIALIAS)
    pixels = np.array(img.convert('L'))
    print('type(pixels) = ', type(pixels))
    print(pixels.shape)
    print(pixels)
    chars = "MNHQ$OC?7>!:-;. "
    N = len(chars)
    step = 256 // N
    print(N)
    result = ''
    for i in range(height):
        for j in range(width):
            result += chars[pixels[i][j] // step]
        result += '\n'
    with open('text.txt', mode='w') as f:
        f.write(result)
    end_time = time.time()
    elapsed_time = end_time - start_time
    print(f'程序耗时：{elapsed_time:.2f} 秒')
~~~

**示例**

![image-20230504112017912](./img/image-20230504112017912.png)
