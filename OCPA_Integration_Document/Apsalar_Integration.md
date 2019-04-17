## APSALAR INTEGRATION
#### Field Mapping
Description|Yeahmobi Parameter|Apsalar Parameter
--|--|--
Event Category|event|{EVTNAME}
Transaction ID|transaction_id|{cl?YeahMobi}
Tracking Source|event_source|apsalar
App ID|app_id|{LONGNAME}
App Version|app_ver|  
Click Time|click_time|{CLICK_UTC}
Installation Time|install_time|{INSTALL_UTC}
Event Time|event_time|{UTC}
Event Content/Payment Amount|event_value|{EVTATTR:$Attribute_Name}/{AMOUNT}
Device ID|(android_id or idfa or win_aid)|device_id|{IDFA}|{AIFA}|{}
Android ID|android_id|{AIFA}/{COALESCE|{AIFA},{ANDI}}
IOS ID|idfa|{IDFA}
windows ID|win_aid|  
IMEI Code|imei|{IP}
Mac Address|mac|  
Google Play Advertising ID|google_adv_id/{AIFA}
Unique ID|unique_id|{COALESCE/{APID},{CLID}}

### Apsalar DOC:

<http://support.apsalar.com/customer/portal/articles/1305106-integration-glossary#passthrough>

<http://support.apsalar.com/customer/en/portal/articles/1996141-integrating-with-apsalar>


### Advertiser Authorization for Event

1. Retention

<div align=center><img src="https://github.com/YmSupportDoc/YmSupportDoc/blob/master/img/Apsalar_Integration1.png" width="90%" height="90%" /></div>

2. Unique event

<div align=center><img src="https://github.com/YmSupportDoc/YmSupportDoc/blob/master/img/Apsalar_Integration2.png" width="90%" height="90%" /></div>

3. Repeated event

<div align=center><img src="https://github.com/YmSupportDoc/YmSupportDoc/blob/master/img/Apsalar_Integration3.png" width="90%" height="90%" /></div>