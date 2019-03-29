## Yeahmobi&affiliate_Integration(S2S)
### 2018.12
#### 1. Integration Description

Data process：  

<div align=center><img src="https://github.com/YmSupportDoc/YmSupportDoc/blob/master/Yeahmobi&affiliate_Integration_document/Yeahmobi&affiliate_Integration(S2S).png" width="100%" height="100%" /></div>

- user click the advertisement, and affiliate system collect the click data.
affiliate system filter the click data by Geo/Platform/device_os and other filter condition. 
- The click which matchs the condition will send click notification to Yeahmobi system. At the same time, The click which matchs the condition will redirect to landing page.
- When conversion event happens, Yeahmobi system will collect conversion date. And the legal conversion data will sent to affiliate.

#### 2. Parameter Description

- aff_sub：affiliate track id, generate by affiliate

- idfa：IOS Offer device id

- google_adv_id：Android device id

- aff_sub6：appname infomation

- sub_affiliate_id：sub affiliate id

- payout：Offer payout

- datetime：conversion time

- sub_aff2——sub_aff5：other parameter affiliate defined

- access_key:generate by Yeahmobi

- ua: User Agent, Encode format

link example：

Tracking Link：

<https://ymtacking.link?offer_id=565252&aff_id=5256&access_key=46b48599410889950868530dab8&aff_sub1={clickid}&sub_affiliate_id={publisherid}&idfa={idfa}&google_adv_id={gaid}&aff_sub6={appname}>

ymtacking.link is the domain of ym tracking link(S2S), please contact account manager for detail information

Post back：

<https://affiliate.com/conv?clickid={aff_sub}>

#### 3. question

- click data can't match Yeahmobi system condition

Yeahmobi system filter the click data by Geo/Platform/device_os and other filter condition, so some click is not match the condition will rejected by Yeahmobi system.

- illegal data：
   + unexpected redirect code: C003 message:offer[***] checkGeoLimits failed at regionLimits when region=CN (SAR)_CN(192.32.250.50)
   + unexpected redirect code: C004 message:offer[***] checkUserAgentLimits failed at platformLimits when platform=macOS
   + unexpected redirect code: C001 message:offer[****] checkPermission failed at affLimits with affid=11111 
   + unexpected redirect code: C026 message:google_adv_id required for offer[11111], pls check
   + unexpected redirect code: C026 message:idfa required for offer[11111], pls check
