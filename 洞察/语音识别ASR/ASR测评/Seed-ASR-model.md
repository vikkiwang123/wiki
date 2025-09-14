## 原理
[Seed-ASR](https://bytedancespeech.github.io/seedasr_tech_report/)
![](attachments/Pasted%20image%2020250915042658.png)
模型：分成2个，CN和ML；使用的时候，通过language字段区分
![](attachments/Pasted%20image%2020250915044340.png)
架构
![](attachments/Pasted%20image%2020250915042848.png)
## 测评结果
API：[产品简介--豆包语音-火山引擎](https://www.volcengine.com/docs/6561/1354871)
特性
![](attachments/Pasted%20image%2020250915041328.png)

测试结果
1、用例 -- 一个HR谈薪资场景
file_url = "https://ttc-advisory-oss.oss-cn-hangzhou.aliyuncs.com/lark_audio/int/T_APLA_1941058348698869760.mp3"

vocab={
    "context_type":"dialog_ctx",
    "context_data":[
        {"text":"soft"},
        {"text":"tough"},
        {"text":"虚线"},
        {"text":"HR"},
        {"text":"base"},
        {"text":"13薪"}
    ]
}

2、效果
1）speaker区分：不好，区分不了2个人的话
![](attachments/Pasted%20image%2020250915041625.png)
2）segmentation：不错，基本上能把两个人说的话划分开 -- 这个也和这个场景两个人说话没有打断对方有关
3）error rate：加了vocab之后好很多，否则对于专业词汇识别很不好
没有加vocab
![](attachments/Pasted%20image%2020250915041951.png)
加了vocab
![](attachments/Pasted%20image%2020250915041834.png)


原始数据
1）without dict
Submit task id: 715ec0b6-ae15-4145-a41d-34d300b15169
Submit task response header X-Tt-Logid: 20250915033010D099CA2604EE0BF6159B

2)with dict
Submit task id: e49283b1-d55f-47f4-ae05-21553f17ec2e
Submit task response header X-Tt-Logid: 20250915040045952595F749817A47B87A

