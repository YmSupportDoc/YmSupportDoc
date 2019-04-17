## Yeahmobi激活转化数据统计对接方案
### 2018年12月
#### 一．对接方案说明
&emsp;&emsp;激活数是广告商主衡量转化效果的重要指标，为更加高效的实现和广告主对接，Yeahmobi可匹配广告商提供多种转化归因方式的对接。

&emsp;&emsp;数据流示意图：  

<div align=center><img src="https://github.com/YmSupportDoc/YmSupportDoc/blob/master/img/广告商&Yeahmobi同步对接(CN).png" width="75%" height="75%" /></div>

&emsp;&emsp;流程说明：
- 用户点击广告，Yeammobi收集点击数据并进行归类处理。
- 按与广告商约定的Offer推广流量限制进行国家、Platform、Device_os等条件过滤，符合的点击数据按广告商提供的Tracking link宏替换后302跳转。
- 广告主收到用户激活数据后与Yeahmobi点击数据进行对比，若为Yeahmobi带来的合规用户，则将Tracking link中的追踪ID（Transaction_id）回传给Yeammobi。

#### 二．参数说明

Transaction_id：追踪ID，由Yeahmobi生成，每一个点击都会有唯一的Transaction_id，广告主确认到转化后，需要将点击对应的Transaction_id作为转化给Yeahmobi回调。
注：若广告主使用的callback方式，则对应的参数链接为:

***callback=http%3A%2F%2Fymcallback.link%2Fconv%3Ftransaction_id%3D{transaction_id}%26affiliate_id%3D{affiliate_id}***

ymcallback.link 为ymcallback的域名，请咨询业务或技术获取详细信息。

idfa：IOS Offer设备id。

google_adv_id：Android设备id。

affiliate_id：Yeahmobi渠道id。

sub_affiliate_id：Yeahmobi子渠道id。

site_name：广告位。

active_time：激活转化发生时间，若广告主在回发转化时未添加该参数，则我们默认安装广告主回调时间作为用户转化时间。

Client_ip：用户发生转化设备的ip。

Revenue：若Offer对接方式为Dynamic-Revenue，则广告主回调转化时需要加上和Yeahmobi结算单价
Carriers：若Offer推广限定了运营商，则广告商回调转化时需加上Carriers。

链接示例：Tracking Link：

<https://advertiser.link?adv1={transaction_id}&adv2={affiliate_id}&adv3={sub_affiliate_id}&adv4={idfa}&adv5={google_adv_id}&callback=http%3A%2F%2Fymcallback.link%2Fconv%3Ftransaction_id%3D{transaction_id}%26affiliate_id%3D{affiliate_id}>

Post back：

<https://ympostback.link?transaction_id={adv1}&active_time={adv_conv_time}&client_ip={adv_conv_ip}&revenue={adv_cost}&carrier={adv_carriers}>

ympostback.link 为YM postback域名，请咨询业务或技术人员获取详细信息。

#### 三．常见问题

1. 广告主转化一直回调失败：

&emsp;&emsp;核对点击通知时Transaction_id是否有进行宏替换，Yeahmobi Transaction_id共计67位，必须按照标准的Postback链接回调，若回调时提示Unknown Transaction_id Format则表示格式非法。

2. 如何判断广告主回调转化成功：

&emsp;&emsp;流程说明：转化回调时返回：success=true;conversion accepted (please check report for final verification result)。