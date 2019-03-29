## KOCHAVA INTEGRATION
#### Field Mapping
Description|Yeahmobi Parameter|Kochava Parameter
--|--|--
Event Category|event|{event_name}
Transaction ID|transaction_id|{publisher_ref_id}
Tracking Source|event_source|mat
App ID|app_id|{package_name} for android|{store_app_id} for apple
App Version|app_ver|{package_app_version}
Click Time|click_time|{click_timestamp}
Installation Time|install_time|{conversion_timestamp}
Event Time|event_time|{timestamp}
Event Content/Payment amount|event_value|{revenue}
Device ID (android_id or idfa or win_aid)|device_id|{android_id},{ios_idfa},{windows_aid}
Android ID|android_id|{android_id}
IOS ID|idfa|{ios_idfa}
Windows ID|win_aid|{windows_aid}
IMEI Code|imei|{device_id}
Mac Address|mac|{mac_address}
Google Play Advertising ID|google_adv_id|{google_aid}
Unique ID|unique_id|{unid}
Payment Amount|event_value|{amount}

### Kochava DOC:

<http://www.kochavasupport.com/reference-information/integrate-as-a-networkpublisher>

<http://www.kochavasupport.com/>

### Advertiser Authorization for Event

The green on the left means there is no setting problem. Orange on the left means some parameter is missing. Blue on the left means postback hasn't been chosen.

<div align=center><img src="https://github.com/YmSupportDoc/YmSupportDoc/blob/master/OCPA_Integration_Document/Kochava_Integration1.png" width="70%" height="70%" /></div>

There are two options for this delivery method. ALL and Network only. If “ALL” is chosen, all advertisers postback events will be delivered.  

<div align=center><img src="https://github.com/YmSupportDoc/YmSupportDoc/blob/master/OCPA_Integration_Document/Kochava_Integration2.png" width="70%" height="70%" /></div>

<div align=center><img src="https://github.com/YmSupportDoc/YmSupportDoc/blob/master/OCPA_Integration_Document/Kochava_Integration3.png" width="70%" height="70%" /></div>