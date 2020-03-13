## 获取小号接口
|参数名|类型|描述|是否必须|
|---|---|---|---|
|called|String|被叫号码|是|
|caller|String|主叫号码|是|
|expiration|int|有效期，单位秒|是|
|needRecord|String|"true" 录音 "false" 不录音, 默认为”true” String形式|否|
|icDisplayFlag|String|被叫外显号码,"0"显真实号码 "1"显示中间号 默认 "1" String形式|否|

```
成功返回值
{
    "ret": 200,
    "data": {
        "midNum": "xxx",//虚拟号码
        "mappingId": "xxx"//绑定id
    }
}
```

## 话单推送接口（推送给调用方）
|参数名|类型|描述|是否必须|
|---|---|---|---|
|mappingId|String|绑定id|是|
|recorder_id|String|通话id|是|
|record_file_url|String|通话录音链接，正常通话时必传|否|
|call_duration|int|通话时长|是|
|begin_time|String|拨通虚拟号码时间,格式为YYYY-MM-DD HH:mm:ss|否|
|alerting_time|String|响铃时间,格式为YYYY-MM-DD HH:mm:ss|否|
|connect_time|String|被叫接通时刻,格式为YYYY-MM-DD HH:mm:ss|否|
|release_time|String|通话结束时刻,格式为YYYY-MM-DD HH:mm:ss|否|
|result|String|通话状态，通话状态的取值请查通话状态区分（0 成功 2无应答 9呼叫失败 11主叫号码与中间号没有关联）|是|
```
成功返回值
{
    "ret": 200,
    "data": {}
}
```