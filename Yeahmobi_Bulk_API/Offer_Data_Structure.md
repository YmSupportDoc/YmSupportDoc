## Offer Data Structure


Field|Description
--|--
offer_name|Name of the offer
offer_id|offer id
offer_category|The category of the offer, the possible values are:- Adult/Sexy<br>- App Download-iOS<br>- Dating<br>- Email/Zip Submit<br>- Entertainment Subscription<br>- Anti-Virus Subscription<br>- Sweepstakes Subscription<br>- Health&Beauty<br>- Incentive<br>- App Download-Android<br>- Gambling<br>- CPS<br>- PC Download<br>- Windows Download<br>- Online APK Package/DDL<br>- Offline APK Package/DDL<br>- App Download-Game
offer_description|Description of the offer
is_incent|Indicate if it is an incentive offer
tracking_link|Tracking Url specified for publisher’s requesting app.
conversion_flow|The conversion flow of the offer. For App Download：- CPI Download,Install&Open<br>- CPE Download,Install,Open&Active Engagement<br>- CPS Download,Install, Register(optional)&Purchas<br>- For Mobile Content：<br>- Download Client <br>- Email Confirmation (DOI) <br>- MSISDN Recognition <br>- Multiple Page Signup <br>- One Page Sign-Up <br>- PIN-Submit (MT) <br>- Single Click Flow <br>- Single Opt-In (SOI) <br>- SMS Confirmation (MO)
targeting|The targeting information of the offer, including platform, device, country and carrier. Detail fields referred to the Targeting Structure below
traffic|The allowed and forbidden traffic source. Detail fields referred to the Traffic Data Structure below
financials|The payout and caps of the offer, together with the remaining caps. Detail fields referred to the Financial Structure below

Sample:
```
"offers": [{
        "offer_id": 10002,
        "offer_name": "App Download - iOS(AT) - Non incentive",
        "offer_category": [
            "App Download-iOS"
        ],
        "offer_description": "<p>WEEP is a simple fun way to discover the stories next door!</p>",
        "tracking_link": "http://global.ymtracking.com/trace?offer_id=10002&app_id=2&type=6fa8fda400000028",
        "conversion_flow": [
            "CPI Download,Install&Open"
        ],
        "targeting": {},
        "traffic": {},
        "financials": {}
    },
    {
        "offer_id": 10042,
        "offer_name": "App Download - iOS(AT) - incentive",
        "offer_category": [
            "App Download-iOS"
        ],
        "offer_description": "<p>WEEP is a simple fun way to discover the stories next door!</p>",
        "tracking_link": "http://global.ymtracking.com/trace?offer_id=10042&app_id=2&type=6fa8fda400000028",
        "conversion_flow": [
            "CPI Download,Install&Open"
        ],
        "targeting": {},
        "traffic": {},
        "financials": {}
    }
]
```

***Targeting Data Structure:***

Field|Description
--|--
platforms|The targeting platform of the offer
devices|The targeting devices of the offer, including device brand and model
device_os|The targeting device os of the offer
countries|The targeting country code of the offer which conform to ISO-3166-1
carriers|The targeting carriers of the offer

Sample:
```
"targeting": {
    "platforms": ["Android"],
    "devices": ["HTC ],
        "device_os": [
            "Android 1.6",
            " Android 2.1"
        ],
        "countries": [
            "US", "CK"
        ],
        "carriers": ["Vodafone"]
    }
```

***Traffic Data Structure:***

Field|Description
--|--
forbidden|The forbidden traffic sources, the available values are the same as above
allowed|The allowed traffic sources. It there is no ‘allowed’ field, it indicates there is no restrictions on traffic.<br>The available traffic sources include:<br>- Wifi Traffic<br>- Absolutely no Incentivization<br>- Gateway/Content Lock Traffic<br>- Usage of words like "Free"<br>- 16+<br>- 3G/4G<br>- 18+<br>- Incentivization needs Approval<br>- Invalid or duplicate leads unaccepted<br>- App Discovery Traffic<br>- Desktop Traffic<br>- Email with Opt-Out only<br>- E-Mailings<br>- Facebook Traffic<br>- Adult Content<br>- Hard-Incentivized<br>- Icon-Drop Traffic<br>- Illegal Filesharing<br>- Opera Traffic<br>- Pop Traffic<br>- Push Notifications<br>- Search<br>- Social Networks<br>- Virtual Currency Traffic<br>- Redirect Traffic<br>- Cash-Backs / GPT<br>- Co-Reg<br>- Display traffic<br>- Google Adwords Traffic<br>- In - App Display traffic<br>- SMS Traffic

Sample:
```
"traffic": {
    "allowed": ["Wifi Traffic", "3G/4G"],
    "forbidden": [
        "Hard-Incentivized"
    ]
}
```

***Financials Data Structure:***

Field|Description
--|--
payout|The payout of the offer
currency|The currency of the payout
cap_shared|If the cap is shared among all publishers.
cap_daily|Daily cap configured for the offer
cap_monthly|Monthly cap configured for the offer
remaing_cap_daily|The amount of daily cap remaining for today. The offer which has no cap remaining will not be returned. The returning value of '-1' indicates there is no daily cap limitation for this offer.

Sample:
```
"financials": {
    "payout": 2.0,
    "currency": "USD",
    "cap_shared": true,
    "cap_daily": 128,
    "cap_monthly": 1000,
    "remaining_cap_daily": 100
}
```