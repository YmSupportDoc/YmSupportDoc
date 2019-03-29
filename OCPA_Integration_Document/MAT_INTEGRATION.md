### MAT INTEGRATION
#### Field Mapping
Description|Yeahmobi Parameter|MAT Parameter
--|--|--
Event Category|event|{event_name}-->{event_type}
Transaction ID|transaction_id|{publisher_ref_id}
Tracking Source|event_source|mat
App ID|app_id|{package_name} for android and {store_app_id} for apple
App Version|app_ver|{package_app_version}
Click Time|click_time|{click_timestamp}
Installation Time|install_time|{install_timestamp} ps:{conversion_timestamp}Always consistent   with timestamp
Event Time|event_time|{timestamp}
Event content|event_value|{event_type}
Device ID|device_id|{android_id},{ios_ifa},{windows_aid}
Android ID|android_id|{android_id}
IOS ID|idfa|{ios_ifa}
Windows ID|win_aid|{windows_aid}
IMEI Code|imei|{device_id}
Mac Address|mac|{mac_address}
Google Play Advertising ID|google_adv_id|{google_aid}
Unique ID|unique_id|{firstnotempty({unid}|{tracking_id}|{transaction_id}|{android_id}|{ios_ifa})} 
Payment Amount|event_value|{amount} 

### MAT DOC:

<https://help.tune.com/marketing-console/macros-in-postback-urls/>

<https://help.tune.com/partner-center/advertising-partners-implementing-server-postbacks-for-reengagement-campaigns/#Basic>


### Advertiser Authorization for Event

1. Android configuration Postback Template Select YM_NEW_Event_Android_oCPA

2. IOS configuration is as shown above. postbackTemplates Select YM_NEW_Event_iOS_oCPA