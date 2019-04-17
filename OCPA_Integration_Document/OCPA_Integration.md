## Yeahmobi OCPA Integration

### Definition
YM：YeahMobi system   
CS：Customer System(Web/App) or Third Trace System   
OCPA：Optimize Cost Per Action   
EVENT：Event name or action   

### Trace Process Description
<div align=center><img src="https://github.com/YmSupportDoc/YmSupportDoc/blob/master/img/OCPA_Integration.png" width="75%" height="75%" /></div>

### Interface 
HTTP GET interface   
<http://global.ymtracking.com/event>

### Parameter Description
Meaning|Key|Necessity|Description
--|--|--|--
event action|event|Y|detailed event name like login,pay... etc.
event value|event_value| |detailed value for one even, like event=pay&event_value=123.00
transaction ID|transaction_id|Y|transaction id of YM，it is required.
unique ID|unique_id|Y|unique transaction ID of CS,like traceId(or deviceId), it must be unique to remove duplicate
source|event_source|Y|event source,like baidu,tencent etc.
app ID|app_id| |packageName or apple store Id
app version|app_ver| |app version
click time|click_time| |user click time
install or transaction time|install_time|Y|the time that user insall the app or open the app 
event time|event_time|Y|the time that the event happens
device ID|device_id|Y|device_id or android_id,ios_idfa,win_adid
android ID|android_id| |android_id
iOS ID|idfa| |idfa
windows ID|win_aid| |window_aid
phone imei number|imei| |imei
mac address|mac| |mac_address
Google Play Advertising ID|google_adv_id| |google_adv_id

### Example
#### android
<http://global.ymtracking.com/event?event={event_name}&event_value={event_value}&transaction_id={ransactionId?yeahmobi}&unique_id={cs_traceId}&event_source=baidu&app_id={package_name}&app_ver={app_version}&click_time={click_time}&install_time={installed_time}&event_time={event_time}&device_id={device_id||android_id}&android_id={android_id}&imei={imei}&mac={mac_md5}&google_adv_id={android_advertising_id}>
#### ios
<http://global.ymtracking.com/event?event={event_name}&event_value={event_value}&transaction_id={transactionId?yeahmobi}&unique_id={cs_traceId}_&event_source=baidu&app_id={app_store_id}&app_ver={app_version}&click_time={click_time}&install_time={installed_time}&event_time={event_time}&device_id={idfa||android_id}&idfa={idfa}&imei={imei}&mac={mac_md5}>

### Remark
#### 一、Direct Adv:
1. please configure the url, and when event happened, call the url
2. please use the real value to relace the event_value data
3. all event type can be supported
4. the android and iOS url can be merge into one url depending on the circumstances

#### 二、3rd Trace System
1. when you use the 3rd Trace System, please configure the event call back url according to the 3rd Trace System, and when event happened, call the url
2. please use the real value to relace the event_value data
3. all event type can be supported
4. the android and iOS url can be merge into one url depending on the circumstances

