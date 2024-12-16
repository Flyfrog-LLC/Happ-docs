# Routing

The app comes with pre-installed geo files, ensuring it's ready to use immediately after installation. The relevance of geo files is maintained by updating the core version within the app.

#### Adding Routing Rules

The app allows you to add routing rules automatically by using special links that can be created on the [https://routing.happ.su](https://routing.happ.su/) website.

The links can be transmitted in one of the following ways:

* Via clipboard.
* Using a deeplink.
* Through a QR code.
* As HTTP headers or subscription body.

For HTTP headers, the `routing` parameter is used, while for subscription bodies, simply including the link is sufficient.

#### Handling Download Errors

The app uses a geo file download manager that operates in the background.

* If the geo file download does not complete within 3 minutes, the process is stopped.
* An error message appears on the main screen.
* A red exclamation mark is displayed next to the problematic profile in the profile list.

#### Troubleshooting

The problematic profile state automatically resolves after:

* Successfully completing file downloads.
* Deleting the problematic profile.

If there are no more problematic profiles in the list, error notifications are removed.

#### Types of Links

* `happ://routing/add/{base64}`: Adds a profile to the profile list. The first added profile becomes active only after geo files are successfully downloaded. If a profile with the same name already exists, it is overwritten.
* `happ://routing/onadd/{base64}`: Adds and automatically activates a profile, even if other profiles are active. If a profile with the same name already exists, it is overwritten.

`{base64}` is a JSON profile converted into a Base64-encoded text format.

#### Profile Structure

The app uses routing profiles configured via JSON.

The default profile contains basic settings used to fill in missing or incorrect parameters.

**Example Default Profile:**

```json
{
  "Name": "Default",
  "GlobalProxy": "true",
  "RemoteDns": "1.1.1.1",
  "DomesticDns": "8.8.8.8",
  "Geoipurl": "https://github.com/v2fly/geoip/releases/latest/download/geoip.dat",
  "Geositeurl": "https://github.com/v2fly/domain-list-community/releases/latest/download/dlc.dat",
  "DnsHosts": {"domain:googleapis.cn": "googleapis.com"},
  "DomainStrategy": "IPifNonMatch",
  "DirectIp": [
    "10.0.0.0/8",
    "100.64.0.0/10",
    "172.16.0.0/12",
    "192.168.0.0/16",
    "169.254.0.0/16",
    "224.0.0.0/4",
    "255.255.255.255"
  ]
}
```

**Example Custom Profile:**

```json
{
  "Name": "China",
  "GlobalProxy": "true",
  "RemoteDns": "1.1.1.1",
  "DomesticDns": "223.5.5.5",
  "Geoipurl": "https://github.com/v2fly/geoip/releases/latest/download/geoip.dat",
  "Geositeurl": "https://github.com/v2fly/domain-list-community/releases/latest/download/dlc.dat",
  "DnsHosts": {},
  "DirectSites": ["geosite:cn", "geosite:geolocation-cn"],
  "DirectIp": ["geoip:cn"],
  "ProxySites": ["geosite:cn"],
  "ProxyIp": ["geoip:amazon"],
  "BlockSites": ["geosite:ads"],
  "BlockIp": ["geoip:ads"],
  "DomainStrategy": "IPifNonMatch"
}
```

#### Profile Management Features

* If a profile with the same name already exists, its data is updated.
* Geo files are updated no more than once a week, even if the profile is updated every hour.
