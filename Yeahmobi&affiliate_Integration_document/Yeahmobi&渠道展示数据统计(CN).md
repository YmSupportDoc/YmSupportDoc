## Yeahmobi&渠道展示数据统计(CN)
### 2018年12月

#### 1．方案说明

&emsp;&emsp;Yeahmobi展示数据统计方案：渠道将素材链接（creatives_url）嵌在广告位，渠道通过请求触发展示事件，Yeahmobi后台进行展示事件的统计。

<div align=center><img src="https://github.com/YmSupportDoc/YmSupportDoc/blob/master/img/Yeahmobi&渠道展示数据统计(CN).png" width="100%" height="100%" /></div>

**报表数据说明：由于展示数据是离线方式采集和计算，所以通常有1~2小时延迟。**

#### 2．素材链接说明

- 链接结构：
<https://imp.ymtracking.com/imp.html?offer_id={offer_id}&aff_id={affiliate_id}&creative_id={creative_id}>

示例：
<https://impressiontest?offer_id=55555&aff_id=88888&creative_id=2018020101>

impressiontest 为YM的impression地址，请咨询业务经理获取详细信息

- 参数说明

参数|是否必须|描述
--|--|--
offer_id|Y|Yeahmobi系统的offer id
aff_id|Y|渠道在Yeahmobi系统中的id
creative_id|N|offer的素材id

#### 3．示例
```
<html>

<head>

<iframe src = "https://impressiontest?offer_id=55555&aff_id=88888&creative_id=2018020101"name = "display offer" >

</head>

<body>

</body>

</html> 
```