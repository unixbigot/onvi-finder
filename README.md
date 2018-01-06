# onvi-finder
Discover and operate cameras that support the ONVIF profiles

# Setup

```
npm install
```

# Use

```
  Usage: of [options] [command]


  Options:

    -V, --version  output the version number
        -h, --help     output usage information


  Commands:

    list                  List discovered cameras
    info [options] <cam>  Fetch information about a particular camera
    snap [options] <cam>  Save a snapshot from a particular camera
```


## Find cameras

```
chris@pickaxe:~/src/onvi-finder$ ./of list
Listing discovered cameras (takes a few seconds).
5 devices were found.
- urn:uuid:48534d41-5254-4c49-4e4b-FF-37-B2-B9-4D-E0
  - NETCAM
  - http://192.168.3.13:10080/onvif/device_service
- urn:uuid:48534d41-5254-4c49-4e4b-E2-B0-4E-0C-43-00
  - NETCAM
  - http://192.168.3.10:10080/onvif/device_service
- urn:uuid:48534d41-5254-4c49-4e4b-98-61-07-02-2C-48
  - NETCAM
  - http://192.168.3.12:10080/onvif/device_service
- urn:uuid:48534d41-5254-4c49-4e4b-D9-C0-63-0C-43-00
  - NETCAM
  - http://192.168.3.11:10080/onvif/device_service
- urn:uuid:5f5a69c2-e0ae-504f-829b-08EA40EFAF47
  - IPCAM
  - http://192.168.3.191:8080/onvif/devices
[
  {
    "urn": "urn:uuid:48534d41-5254-4c49-4e4b-FF-37-B2-B9-4D-E0",
    "name": "NETCAM",
    "hardware": "MODEL",
    "location": "ShenZhen",
    "types": [
      "dn:NetworkVideoTransmitter"
    ],
    "xaddrs": [
      "http://192.168.3.13:10080/onvif/device_service"
    ],
    "scopes": [
      "onvif://www.onvif.org/type/video_encoder",
      "onvif://www.onvif.org/type/audio_encoder",
      "onvif://www.onvif.org/location/city/ShenZhen",
      "onvif://www.onvif.org/hardware/MODEL",
      "onvif://www.onvif.org/name/NETCAM",
      "onvif://www.onvif.org/VENDOR_MODEL",
      "onvif://www.onvif.org/Profile/Streaming",
      ""
    ]
  },
  {
    "urn": "urn:uuid:48534d41-5254-4c49-4e4b-E2-B0-4E-0C-43-00",
    "name": "NETCAM",
    "hardware": "MODEL",
    "location": "ShenZhen",
    "types": [
      "dn:NetworkVideoTransmitter"
    ],
    "xaddrs": [
      "http://192.168.3.10:10080/onvif/device_service"
    ],
    "scopes": [
      "onvif://www.onvif.org/type/video_encoder",
      "onvif://www.onvif.org/type/audio_encoder",
      "onvif://www.onvif.org/location/city/ShenZhen",
      "onvif://www.onvif.org/hardware/MODEL",
      "onvif://www.onvif.org/name/NETCAM",
      "onvif://www.onvif.org/VENDOR_MODEL",
      "onvif://www.onvif.org/Profile/Streaming",
      ""
    ]
  },
  {
    "urn": "urn:uuid:48534d41-5254-4c49-4e4b-98-61-07-02-2C-48",
    "name": "NETCAM",
    "hardware": "MODEL",
    "location": "ShenZhen",
    "types": [
      "dn:NetworkVideoTransmitter"
    ],
    "xaddrs": [
      "http://192.168.3.12:10080/onvif/device_service"
    ],
    "scopes": [
      "onvif://www.onvif.org/type/video_encoder",
      "onvif://www.onvif.org/type/audio_encoder",
      "onvif://www.onvif.org/location/city/ShenZhen",
      "onvif://www.onvif.org/hardware/MODEL",
      "onvif://www.onvif.org/name/NETCAM",
      "onvif://www.onvif.org/VENDOR_MODEL",
      "onvif://www.onvif.org/Profile/Streaming",
      ""
    ]
  },
  {
    "urn": "urn:uuid:48534d41-5254-4c49-4e4b-D9-C0-63-0C-43-00",
    "name": "NETCAM",
    "hardware": "MODEL",
    "location": "ShenZhen",
    "types": [
      "dn:NetworkVideoTransmitter"
    ],
    "xaddrs": [
      "http://192.168.3.11:10080/onvif/device_service"
    ],
    "scopes": [
      "onvif://www.onvif.org/type/video_encoder",
      "onvif://www.onvif.org/type/audio_encoder",
      "onvif://www.onvif.org/location/city/ShenZhen",
      "onvif://www.onvif.org/hardware/MODEL",
      "onvif://www.onvif.org/name/NETCAM",
      "onvif://www.onvif.org/VENDOR_MODEL",
      "onvif://www.onvif.org/Profile/Streaming",
      ""
    ]
  },
  {
    "urn": "urn:uuid:5f5a69c2-e0ae-504f-829b-08EA40EFAF47",
    "name": "IPCAM",
    "hardware": "",
    "location": "china",
    "types": [
      "dn:NetworkVideoTransmitter"
    ],
    "xaddrs": [
      "http://192.168.3.191:8080/onvif/devices"
    ],
    "scopes": [
      "onvif://www.onvif.org/Profile/Streaming",
      "onvif://www.onvif.org/model/C9F0SeZ0N0P0L0",
      "onvif://www.onvif.org/name/IPCAM",
      "onvif://www.onvif.org/location/country/china"
    ]
  }
]
```

## Get camera info

```
chris@pickaxe:~/src/onvi-finder$ ./of info -s 8080 192.168.3.191
doInfo 192.168.3.191
   service=8080 user=admin pass=admin
Device: {
  "Manufacturer": "IPCAM",
  "Model": "C9F0SeZ0N0P0L0",
  "FirmwareVersion": "V9.1.6.1.16-20170311",
  "SerialNumber": "08EA40EFAF47",
  "HardwareId": "V9.1.6.1.16-20170311"
}
Profile: {
  "token": "MainProfileToken",
  "name": "MainProfile",
  "snapshot": "http://192.168.3.191:80/web/auto.jpg?-usr=admin&-pwd=admin&",
  "stream": {
    "udp": "rtsp://192.168.3.191:554/11",
    "http": "http://192.168.3.191:80/iphone/11?admin:admin&",
    "rtsp": "rtsp://192.168.3.191:554/11"
  },
  "video": {
    "source": {
      "token": "video_source_cfg_token",
      "name": "video_source_cfg",
      "bounds": {
        "width": 1280,
        "height": 720,
        "x": 0,
        "y": 0
      }
    },
    "encoder": {
      "token": "main_video_encoder_cfg_token",
      "name": "main_video_encoder_cfg",
      "resolution": {
        "width": 1280,
        "height": 720
      },
      "quality": 3,
      "framerate": 25,
      "bitrate": 1536,
      "encoding": "H264"
    }
  },
  "audio": {
    "source": {
      "token": "audio_source_cfg_token",
      "name": "audio_source_cfg"
    },
    "encoder": {
      "token": "g711_audio_encoder_cfg_token",
      "name": "g711_audio_encoder_cfg",
      "bitrate": 16,
      "samplerate": 8,
      "encoding": "G711"
    }
  },
  "ptz": {
    "range": {
      "x": {
        "min": -1,
        "max": 1
      },
      "y": {
        "min": -1,
        "max": 1
      },
      "z": {
        "min": -1,
        "max": 1
      }
    }
  }
}
```
