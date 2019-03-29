## Icons/Creatives/Videos Data Structure
Field|Description
--|--
url|CDN Url, which can be directly used for promotion
language|If it is from the market, indicates the language of the Icons/Creatives/Videos
countries|For Icons/Creatives/Videos from offers only, indicates which countries can be applied. It is the same as the targeting countries of the source offer.

Sample:
```
"icons": {
    "72*72": [
        {
            "url": "http://ymcdn.co/offer_single_files/lIhIYmlUP0iV3F.jpeg",
            "language": "EN",
            "countries": ["US", "HK", "SG", "SA"]
        },
        {
            "url": "http://ymcdn.co/offer_single_files/5IMkflo3LIMKGnpGwe.jpeg",
            "language": "EN",
            "countries": ["US", "JP", "HK"]
        }
    ],
    "128*128": [{
            "url": " http://ymcdn.co/offer_single_files/flo3LIM5IMkGnpGwe.jpeg ",
            "language": "EN"
        }
    ]
}
```