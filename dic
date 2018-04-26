import urllib.request
import urllib.parse
import json

print("有道翻译\n")
print("输入*结束程序\n")
while(True):

    content = input("请输入需要翻译的内容：")
    if(content == '*'):
        break
    url = "http://fanyi.youdao.com/translate?smartresult=dict&smartresult=rule"#真翻译地址（原地址为：translate=0? 导致error50  删掉=0后运行正常）

    head = {}
    head['User-Agent'] = 'Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/64.0.3282.119 Safari/537.36'#模拟用户点击

    data = {}
    data['i'] = content
    data['from'] = 'AUTO'
    data['to'] = 'AUTO'
    data['smartresult'] = 'dict'
    data['client'] = 'fanyideskweb'
    #data['salt'] = '1524726372187'
    #data['sign'] = '6df47dd9bc551e18334f36d02794a6a7'
    data['doctype'] = 'json'
    data['version'] = '2.1'
    data['keyfrom'] = 'fanyi.web'
    data['action'] = 'FY_BY_CLICKBUTTION'
    data['typoResult'] = 'false'
    data = urllib.parse.urlencode(data).encode('utf-8')

    req = urllib.request.Request(url,data,head)
    response = urllib.request.urlopen(req)
    html = response.read().decode('utf-8')


    #print(html)
    target = json.loads(html)
    target = target['translateResult'][0][0]['tgt']#字典解析
    print(target)
