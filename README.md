# 句子级中文三元组抽取
欢迎大家测试、使用和交流。目前使用的是华为云，1核2G，服务器带宽有限。
## 三元组抽取：
- 输入：
content：str，需要抽取的句子。
time：str，基准时间。
- 输出：
code：抽取服务状态。
data：List，抽取结果。（主体，关系词，客体，时间，句子起始点）
message：抽取结果状态。
## 参考代码
```
import requests
url = 'http://124.71.160.12:1220/product'
body = {"content": '美国回购利率暴跌为负，一场新的金融风暴正在酝酿。', 'time': '2019-11-01 08:00:00'}
try:
	r = requests.post(url, json=body)
	print(r.json())
except:
	print("服务错误")
```
## 返回数据：
```
{'code': 200, 'data': ["(['美国', '回购利率'], ['暴跌', '为'], ['负'], '2019-11-01 08:00:00', '', [0, 24])", "(['一', '场', '新', '的', '金融', '风暴', '正在'], ['进行'], ['酝酿'], '2019-11-01 08:00:00', '', [0, 24])"], 'message': 'OK'}
```
