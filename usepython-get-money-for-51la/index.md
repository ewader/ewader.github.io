# 用python代码来薅51.la的羊毛

前天，51.la宣布，终止优站计划了，不再审核新的用户，不过老的用户可以一直到年底。
看到这个消息，以前还登陆一下，做做任务，因为我觉得，这是一种相互的交换吧，但是这个消息公布之后，老刘就觉得没有必要了，因为按照我的流量，是不会达到体现的金额的。正好，从别的博客看到这个代码，所以搬运过来，实际体验了一下还是很方便的。
## 以下是代码
```python
import requests
import json
import time

#任务
def Report(tasktype,cookies):
    url = "https://user.51.la/api/user/active/pv?productCode=v6&pageType="+str(tasktype)
    
    payload={}
    headers = {
      'Host': 'user.51.la',
      'User-Agent': 'Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/105.0.0.0 Safari/537  .36',
      'Referer': 'https://v6.51.la/',
      'Cookie': cookies
    }
    
    response = requests.request("GET", url, headers=headers, data=payload)
    
    print(response.text)

#查询任务
def getnum(name,cookies):
    url = "https://user.51.la/api/user/active/taskList"
    
    payload={}
    headers = {
      'Accept': 'application/json, text/plain, */*',
      'Cookie': cookies,
      'Host': 'user.51.la',
      'Origin': 'https://user.51.la',
      'Referer': 'https://user.51.la/activity/yzjh?action=show'
    }
    
    response = requests.request("POST", url, headers=headers, data=payload)
    r=response.json()
    if r['code']==2000:
        data=r['data']
        return data[name]
    else:
        return False
    
cookies=''

#
Report(1,cookies)

n=getnum('dailyReportPages',cookies)
if 5-n>-1:
    for i in range((5-n+1)):
        Report(2,cookies)
        time.sleep(5)
else:
    print('报表任务已完成'+str(n))

```

## 使用方法
登录你的51,la账户
，浏览器F12，把cookies复制到下面的cookies里，保存即可。
如果你使用的是windows，需要安装python3.
如果你使用的linux或者mac，需要给据系统的情况，升级到python3.因我本人使用的是manjaro，python是3.10版本，可以直接使用。

把上面的代码保存成一个文件，比如51la.py
用以下命令：
```bash
python3 51la.py
```
等待运行完毕即可。

