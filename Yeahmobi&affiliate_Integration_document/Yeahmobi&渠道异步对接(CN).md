## Yeahmobi&渠道异步对接(CN)
### 2018年12月
#### 一．对接方案说明

&emsp;&emsp;数据流示意图：  

<div align=center><img src="https://github.com/YmSupportDoc/YmSupportDoc/blob/master/img/Yeahmobi&渠道异步对接(CN).png" width="100%" height="100%" /></div>

流程说明：
- 用户点击广告，渠道对用户点击处理。
- 按照Yeahmobi提供的offer tracking link添加转化参数后302跳转。
- Yeahmobi收到点击后对相关数据进行流量校验，判断是否符合推广要求。
- Yeahmobi确认到有效激活后进行转化数据匹配，并按照渠道设置的Postback发起转化回调。

#### 二．参数说明

- aff_sub：追踪ID，由渠道生成。
- idfa：IOS设备id。
- google_adv_id：Android设备id。
- site_name：广告位信息。
- sub_affiliate_id：Yeahmobi子渠道id。
- site_name：广告位。
- payout：Offer结算Revenue。
- datetime：转化时间。
- sub_aff2——sub_aff5：渠道自定义参数。
- access_key:渠道授权标识key，请咨询业务经理获取
- ua: User Agent, Encode标准格式
链接示例：

Tracking Link：

<https://ymtacking.link?offer_id=565252&aff_id=5256&access_key=46b48599410889950868530dab8&aff_sub1={clickid}&sub_affiliate_id={publisherid}&idfa={idfa}&google_adv_id={gaid}&aff_sub6={appname}>

ymtacking.link 为YM 异步tracking的域名，请咨询业务经理获取详细信息

Post back：

<https://affiliate.com/conv?clickid={aff_sub}>
 

#### 三．常见问题

1. 点击数据和Yeahmobi系统数据不一致：

&emsp;&emsp;每个Offer都会有流量的限制条件，Yeahmobi会将国家，设备类型等不符流量处理，需调整流量。

2. 异常示例：

- unexpected redirect code: C003 message:offer[***] checkGeoLimits failed at regionLimits when region=CN (SAR)_CN(192.32.250.50)
推广的国家不符
- unexpected redirect code: C004 message:offer[***] checkUserAgentLimits failed at platformLimits when platform=macOS
推广的设备不符
- unexpected redirect code: C001 message:offer[****] checkPermission failed at affLimits with affid=11111
Offer未授权
- unexpected redirect code: C026 message:google_adv_id required for offer[11111], pls check
tracking link中未传google_adv_id
- unexpected redirect code: C026 message:idfa required for offer[11111], pls check
racking link中未传idfa