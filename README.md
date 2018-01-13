# 《冲顶大会》答题辅助工具
## 冲顶大会

>最近几天，“直播答题”已席卷互联网。《冲顶大会》题目的范围涉及很广，天文地理历史科学娱乐影视音乐诗歌礼仪等，每次活动共12道题，也难怪王思聪会挑衅地说“觉得自己很聪明可以来试试”，反正，规则就是10秒中之内未答题和答错题都将被淘汰，且无法角逐当期的奖金。

<img width="300px" src="https://github.com/steveyg/AnswerHelper/blob/master/res/img/chongding.jpg?raw=true"/>

虽然通过邀请好友可以获得复活次数，但是毕竟复活很宝贵，而且每轮只能复活一次，如果复活之后答错会更加可惜。那么怎么样才能够短时间内提升我们的准确率呢？

## 原理说明

1.手机进入答题app

2.Android可以通过adb截屏并拉取图片
```shell
adb shell screencap -p /sdcard/autojump.png
adb pull /sdcard/autojump.png .
```
iPhone可以通过WDA进行图片截取，或者通过通过AirPlay/QuickTime投影到电脑上截取，[参考](https://jingyan.baidu.com/article/64d05a02514064de54f73b7c.html)

3.通过ocr将题目内容识别出来

4.对题目进行分析，包括三个部分
- 直接打开相应的搜索网页
- 搜索问题，查找每个选项在搜索结果中的词频
- 将问题和每个答案分别搜索，将搜索结果数作为依据
通过后两种方式得出最终的推荐结果，如果后两种无法得出则可以选择打开网页

## 使用教程
### 通过ocr进行识别，适用于所有答题类APP

1.下载代码并安装python2.7环境

2.安装百度ocr库
```shell
pip install baidu-aip
```

3.在[百度云](https://cloud.baidu.com/product/ocr.html)中创建一个项目，获取相应的app id、api key以及secret_key，在config.py中进行替换

4.在img_utils中选择你喜欢的获取图片的方式，并且调整截图区域

5.修改config中的GET_TYPE为TYPE_IMG

6.在终端中运行
```shell
python main.py
```
进行搜索

### 通过api进行获取，适用于冲顶大会APP

1.下载代码并安装python2.7环境

2.修改config中的GET_TYPE为TYPE_NET_CHONGDING

3.在每道题出现前运行
```shell
python main.py
```
比如在前一道题出现答案之后，就运行脚本，等待结果即可

## 运行截图
<img width="550px" src="https://github.com/steveyg/AnswerHelper/blob/master/res/img/run.jpeg?raw=true"/>

## 更新日志
2018.01.11 增加了api访问方式，感谢[HuuBaa](https://github.com/HuuBaa)

## 常见问题

详见[Q&A](https://github.com/steveyg/AnswerHelper/blob/master/Q%26A.md)

## 进行中
1.尝试获取其他app接口

2.简化切换不同方式的操作


