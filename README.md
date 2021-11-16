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

#### Complete code :

```config

/* Magic Mirror Config Sample
 *
 * By Michael Teeuw https://michaelteeuw.nl
 * MIT Licensed.
 *
 * For more information on how you can configure this file
 * see https://docs.magicmirror.builders/getting-started/configuration.html#general
 * and https://docs.magicmirror.builders/modules/configuration.html
 */
let config = {
	address: "localhost", 	// Address to listen on, can be:
							// - "localhost", "127.0.0.1", "::1" to listen on loopback interface
							// - another specific IPv4/6 to listen on a specific interface
							// - "0.0.0.0", "::" to listen on any interface
							// Default, when address config is left out or empty, is "localhost"
	port: 8080,
	basePath: "/", 	// The URL path where MagicMirror is hosted. If you are using a Reverse proxy
					// you must set the sub path here. basePath must end with a /
	ipWhitelist: ["127.0.0.1", "::ffff:127.0.0.1", "::1"], 	// Set [] to allow all IP addresses
															// or add a specific IPv4 of 192.168.1.5 :
															// ["127.0.0.1", "::ffff:127.0.0.1", "::1", "::ffff:192.168.1.5"],
															// or IPv4 range of 192.168.3.0 --> 192.168.3.15 use CIDR format :
															// ["127.0.0.1", "::ffff:127.0.0.1", "::1", "::ffff:192.168.3.0/28"],

	useHttps: false, 		// Support HTTPS or not, default "false" will use HTTP
	httpsPrivateKey: "", 	// HTTPS private key path, only require when useHttps is true
	httpsCertificate: "", 	// HTTPS Certificate path, only require when useHttps is true

	language: "en",
	locale: "en-US",
	logLevel: ["INFO", "LOG", "WARN", "ERROR"], // Add "DEBUG" for even more logging
	timeFormat: 24,
	units: "metric",
	// serverOnly:  true/false/"local" ,
	// local for armv6l processors, default
	//   starts serveronly and then starts chrome browser
	// false, default for all NON-armv6l devices
	// true, force serveronly mode, because you want to.. no UI on this device

	modules: [
		{
			module: "alert",
		},
		{
			module: "updatenotification",
			position: "top_bar"
		},
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
		{
			module: "calendar",
			header: "US Holidays",
			position: "top_left",
			config: {
				calendars: [
					{
						symbol: "Gujarat Holidays",
						url: "https://www.officeholidays.com/ics-clean/india/gujarat"
					}

				]
			}
		},
		{
			module: "compliments",
			position: "lower_third"
		},
		
		{
			module: "weather",
			header: "Vadodara",
			position: "top_right",
			config: {
				weatherProvider: "openweathermap",
				type: "current",
				location: "Vadodara",
				locationID: "1253573", 
				apiKey: "!!!!Enter-your-KEY!!!!"
				
			}
		},

		{
			module: "newsfeed",
			position: "bottom_bar",
			config: {
				feeds: [
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
	]
};

/*************** DO NOT EDIT THE LINE BELOW ***************/
if (typeof module !== "undefined") {module.exports = config;}




```