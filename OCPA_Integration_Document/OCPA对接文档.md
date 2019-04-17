## Yeahmobi OCPA 对接文档

### 名词定义
YM：泛指Yeahmobi   
CS：客户系统(Web/App)或追踪平台系统   
OCPA：optimize cost per action   
EVENT：事件action具体内容   

### 追踪流程说明
<div align=center><img src="https://github.com/YmSupportDoc/YmSupportDoc/blob/master/img/OCPA_Integration.png" width="75%" height="75%" /></div>

### 接口协议
HTTP GET接口

<http://global.ymtracking.com/event>

### 参数说明
含义|key|必选|说明
--|--|--|--
事件类型|event|Y|具体的事件名称login,pay...
事件值|event_value| |具体对应事件的值,例event=pay&event_value=123.00
交易ID|transaction_id|Y|YM系统传⼊CS的追踪ID，需要回传
外部唯⼀ID|unique_id|Y|CS内部确定交易的唯⼀ID,例traceId(+deviceId），必须全局唯一，用于去重
追踪来源|event_source|Y|请求来源,例baidu,xxx
应⽤ID|app_id| |packageName or apple store Id
应用版本|app_ver app| |version
点击时间|click_time| |链接点击时间，尽量需要填充
安装/转化时间|install_time|Y|app安装或者site open等时间
事件发生时间|event_time|Y|追踪的事件发生的时间
设备ID|device_id|Y|device_id或android_id,ios_idfa,win_adid
安卓ID|android_id| |android_id,
iOS ID|idfa| |idfa
windows ID|win_aid| |window_aid
手机串码|imei| |imei
mac地址|mac| |mac_address
Google Play Advertising ID|google_adv_id| | 

### 示例
#### android
<http://global.ymtracking.com/event?event={Event_Name}&event_value={event_value}&transaction_id={ransactionId?yeahmobi}&unique_id={cs_traceId}&event_source=baidu&app_id={package_name}&app_ver={app_version}&click_time={click_time}&install_time={installed_time}&event_time={event_time}&device_id={device_id||android_id}&android_id={android_id}&imei={imei}&mac={mac_md5}&google_adv_id={android_advertising_id}>
#### ios
<http://global.ymtracking.com/event?event={Event_Name}&event_value={event_value}&transaction_id={transactionId?yeahmobi}&unique_id={cs_traceId}_&event_source=baidu&app_id={app_store_id}&app_ver={app_version}&click_time={click_time}&install_time={installed_time}&event_time={event_time}&device_id={idfa||android_id}&idfa={idfa}&imei={imei}&mac={mac_md5}>

### 说明
#### 一、Direct Adv:
1. 在事件触发位置(可以是app上操作，也可以是后台系统异步触发)，调用上述GET请求
2. 替换具体的key对应的value为真实数据
3. 如果有第三⽅方或者⾃自有追踪监控平台，可以配置为相应的eventcallback请求
4. 多种类型事件，皆可通用
5. 根据情况可以将android和iOS链接参数拼接，合为一个通⽤用链接

#### 二、3rd Trace System
1. 在事件触发位置(可以是app上操作，也可以是后台系统异步触发)，配置相对应的call back url
2. 替换具体的key对应的value为真实数据
3. 如果由于⼴广告商或者YM传⼊入的参数，使⽤用了了3rd Trace System⾃定义的param key,请⾃自⾏行行配置YM callback URL固定的参数key，以便和传入的值相对应。
4. 多种类型事件，皆可通⽤用
5. 根据情况可以将android和iOS链接参数拼接，合为一个通用链接

