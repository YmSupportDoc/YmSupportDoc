## Google Play Data Structure
Field|Description
--|--
language|The language of the app
app_category_primary|Primary category of the app
app_category_secondary|Secondary category of the app
app_description|App description
current_version|Current version of the app
free|If it is a free app
iap|If there is in app purchase
price|App’s price if it is not a free app
rating_average|The average rating of the app
rating_current_version|The rating of the current version
rating_counts_average|How many users reviewed the app
content_rating|The rating of the app content
file_size_bytes|The size of the app package in bytes
created|The created time of the app, e.g. 10 June 2015
updated|The update time of the app, e.g. 2 March 2016
downloads|The total download of the app, e.g. 10,000,000 - 50,000,000
what_is_new|The release note of the new version
permissions|The required permission on os when installing the app
min_os_version|The minimum os version of the app
supported_devices|The supported devices of the app
supported_languages|The supported languages of the app 
screenshots|The app screenshots grouped by size
icons|The app icons grouped by size
videos|The app videos grouped by size

Sample:
```
"google_play": [
    {
        "language": "en",
        "app_category_primary": "game",
        "app_category_secondary": [
            "strategy", "RPG"
        ],
        "app_description": "This is a hot game.",
        "current_version": "8.12",
        "free": false,
        "iap": true,
        "price": 20.3,
        "rating_average": 4.5,
        "rating_current_version": 4.1,
        "rating_counts_average": 3000,
        "content_rating": "17+",
        "file_size_bytes": 64004745,
        "created": "",
        "updated": "December 14, 2015",
        "downloads": "10,000,000 - 50,000,000",
        "what_is_new": "",
        "permissions": "",
        "min_os_version": "7.0",
        "supported_devices": [],
        "supported_languages": [
            "AR", "EN"
        ],
        "screenshots": [],
        "icons": [],
        "videos": []
    },
    {
        ...
    }
]
```