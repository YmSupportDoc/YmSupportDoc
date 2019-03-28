## Advertiser&Yeahmobi Integration(S2S)
### 2018.12
#### 1. Integration Description

The transaction data is the most important data of Key Performance Indicator for advertising efferc. In order to reduce the time of redirect to landing page for users, Yeahmobi systeme support S2S integration for advertiser.
Data process：

<div align=center><img src="https://github.com/YmSupportDoc/YmSupportDoc/blob/master/Advertiser&Yeahmobi_Integration_document/Advertiser&Yeahmobi_Integration(S2S).png" width="75%" height="75%" /></div>

user click the advertisement, and Yeahmobi system collect the click data.
Yeahmobi system filter the click data by Geo/Platform/device_os and other filter condition. The click which matchs the condition will redirect to landing page. At the same time Yeahmobi system will send click notification to advertiser system.

When conversion event happens, advertiser system will collect conversion date. And the legal conversion data will sent to Yeahmobi.

#### 2. Parameter Description

Transaction_id：unique track ID,generate by Yeahmobi.

notice：if advertiser use callback url,the call back link is
callback=http%3A%2F%2Fymcallback.link%2Fconv%3Ftransaction_id%3D{transaction_id}%26affiliate_id%3D{affiliate_id}。

ymcallback.link is the domain of ymcallback,please contact account manager for detail information.

idfa：IOS Offer device id

google_adv_id：Android device id

affiliate_id：Yeahmobi affiliate id

sub_affiliate_id：Yeahmobi sub_affiliate id

active_time：active time, if there is no active_time in postback parameter, Yeahmobi system will user receive date as active time.

Client_ip： client ip for transaction event

Revenue：If use Dynamic Revenue for integration, advertiser must add this parameter in postback.

link example：

Tracking Link：

<https://advertiser.link?adv1={transaction_id}&adv2={affiliate_id}&adv3={sub_affiliate_id}&adv4={idfa}&adv5={google_adv_id}&adv_ip=${ip}&adv_ua=${user_agent}&adv_click_time=${click_time_mills}&callback=http%3A%2F%2Fymcallback.link%2Fconv%3Ftransaction_id%3D{transaction_id}%26affiliate_id%3D{affiliate_id}>

Post back：

<https://ympostback.link?transaction_id={adv1}&active_time={adv_conv_time}&client_ip={adv_conv_ip}&revenue={adv_cost}&carrier={adv_carriers}>

ympostback.link is the domain of YM postback,please contact account manager for detail information

#### 3. questions

a.postback fail：

  Please check the Transaction_id data. Transaction_id is a 67 bits string, please make sure the format is right.

b.how to judge postback success：

  if the postback result is "success=true;conversion accepted (please check report for final verification result)。" means the postback success.

c.parameter support：

  Yeahmobi system support the parameter format by requirement such as encode, MD5 ,captital and small letter.
