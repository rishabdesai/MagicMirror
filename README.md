# MagicMirror

* MagicMirror is a Open Source and free to use application. 
* official wesite : 
    > https://magicmirror.builders/
* Official Documentation Page :
    > https://docs.magicmirror.builders/
* Manual Installation steps :
    > https://docs.magicmirror.builders/getting-started/installation.html#manual-installation
* Alternative way- using Script :
    > https://github.com/sdetweil/MagicMirror_scripts

---
#### Screenshot: 

![mmm](https://user-images.githubusercontent.com/31618460/141990276-cf6e8806-655c-49cc-bd6d-56bf4ed646b5.png)
)
### Default Modules:
Default module list can be found in documentation at this [link](https://docs.magicmirror.builders/modules/introduction.html)

#### **Clock**
```config
{
module: "clock",
position: "top_left",
    config: {
    displaySeconds: true,
    displayType: "both",
    analogSize: "200px",
    analogFace: "face-002"   
    }
},
```

#### **Calendar**
```config
{
module: "calendar",
header: "My Calendar",
position: "top_left",
config: 
    {
  calendars:
        [
            {
            symbol: "Gujarat Holidays",
            url: "https://www.officeholidays.com/ics-clean/india/gujarat"
            }
        ]
    }
},

```

#### **Weatjer**
```config
{
module: "weather",
header: "Vadodara",
position: "top_right",
config: {
    weatherProvider: "openweathermap",
    type: "current",
    location: "Vadodara",
    locationID: "1253573", 
    apiKey: "Your-API-KEY"
		}
},
```

#### **Compliments**
```config
# To add/modify existing compliments,make changes in file-
# /home/pi/MagicMirror/modules/default/compliments 

{
    module: "compliments",
    position: "lower_third"
},

```

#### **News Feed**
```config
{
module: "newsfeed",
position: "bottom_bar",
config: 
    {
    feeds: 
        [
            {
            title: "Times Of India News",
            url: "http://timesofindia.indiatimes.com/rssfeeds/-2128936835.cms"
            },
            {
            title: "The Hindu",
            url: "https://www.thehindu.com/business/feeder/default.rss"
            },
        ],
    showSourceTitle: true,
    showPublishDate: false,
    broadcastNewsFeeds: true,
    broadcastNewsUpdates: true
    }
},

```

#### 3rd Party Modules :
* Varous 3rd party modules can be fount at following link:
    > https://github.com/MichMich/MagicMirror/wiki/3rd-party-modules

---

