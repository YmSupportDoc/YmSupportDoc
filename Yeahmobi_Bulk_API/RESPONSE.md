## RESPONSE
The successful response will return all available products together with a success flag. When there is error, the response will show flag “fail” and a detail message.

msg|Description
--|--
illegal request|The request URL is wrong
bad token|The token is with wrong format, make sure the API token is correct
publisher not found|Can’t find the publisher by API token, make sure the API token is correct
publisher is not active|The account is either pending or deleted. Contact the account manager to activate it.
can not found appId|The app id in the request URL is wrong
appId: xxx of publisher: xxx is not active|The status of the app in the request URL is not active. Contact the account manager to activate it.

#### FIELDS
**If the field is blank or not shown in the result, it indicates there is no value set up for that field.**

##### General Data Structure
Field|Description
--|--
product_category|Main category of the product, indicating the product is App Download or Mobile Content
product_category_secondary|Secondary category of the product: For App Download:<br>- Google Play<br>- Itune<br>- Online DDL<br>- Other
app_id|The internal product app id in Yeahmobi
app_name|For APP Download product only,
pkg_name|For APP Download only, the package name of the app. For example, ‘com.android.lordsmobile’ for apps in Google Play and ‘id945274928’ for apps in itune
app_short_description|For APP Download only, the short description of the app.
app_url|For APP Download only, the preview URL of the app. If it is in the market, it shows market URL.
google_play|For Google Play product only. All market information will be grouped together by app language. If the app supports multi- language, there will multiple sections. Detail fields referred to Google Play Data Structure below.
itune|For itune product only. All market information will be grouped together. Detail fields referred to itune Data Structure below.
icons|Grouped by size, from market and offers. Detail fields referred to the Icons/Creatives/Videos Data Structure below
creatives|Grouped by size, from market and offers. Detail fields referred to the Icons/Creatives/Videos Data Structure below
videos|Grouped by size, from market and offers. Detail fields referred to the Icons/Creatives/Videos Data Structure below
offers|Available offers which are promoting the same app and the specific publisher’s app is qualified for promotion. Detail fields referred to the Offer Data Structure below

Sample:
```
{
    "flag": "success",
    "data": [{
            "app_id": 248,
            "app_name": "Super Mobile",
            "pkg_name": "com.android.supermobile",
            "app_short_description": "",
            "app_url": "https://play.google.com/store/apps/details?id=com.android.supermobile",
            "product_category": "App Download",
            "product_category_secondary": "Google Play",
            "google_play": [],
            "icons": {},
            "creatives": {},
            "videos": {},
            "offers": []
        },
        {
            "app_id": 12,
            "app_name": "Smart Tool",
            "pkg_name": "id945274945",
            "app_short_description": "",
            "app_url": "https://itunes.apple.com/app/id945274945?mt=8",
            "product_category": "App Download",
            "product_category_secondary": "Itune",
            "itune": [],
            "icons": {},
            "creatives": {},
            "videos": {},
            "offers": []
        }
    ]
}
```
