# Cloud REST API

http requests following auth are sent with Connection keep-alive

## Auth

`GET https://cms.lamarzocco.io/oauth/v2/token`

application/x-www-form-urlencoded

client_id: 7_1xwei9rtkuckso44ks4o8s0c0oc4swowo00wgw0ogsok84kosg   \\ Static secret
client_secret: 2mgjqpikbfuok8g4s44oo4gsw0ks44okk4kc4kkkko0c8soc8s \\ Static secret
grant_type: password
username: {user_email}
password: {user_password}


```json
{
    "access_token": "xxx",
    "expires_in": 3600,
    "token_type": "bearer",
    "scope": null,
    "refresh_token": "xxx"
}
```

## Refresh token

tbc

## La Marzocco customer account information

`GET https://cms.lamarzocco.io/api/professional/customer`


```json
{
    "status": true,
    "status_code": 200,
    "data": {
        "uuid": "xxx",
        "name": "api",
        "active": true,
        "country": {
            "uuid": "xxx",
            "name": "Other",
            "alpha2Code": "EN",
            "country": "ot_OT"
        },
        "email": "{user_email}",
        "image": null,
        "role": {
            "uuid": "xxx",
            "name": "Customer",
            "role": "ROLE_CUSTOMER",
            "description": "Default role for user registered with mobile application"
        },
        "username": "{xxx}",
        "authenticationType": "INTERNAL",
        "customerAuthenticationType": [],
        "birthday": "{account_creation_date}",
        "businessSector": null,
        "disposalCommercial": false,
        "disposalThirdParty": false,
        "disposalProfile": false,
        "emailConfirmed": true,
        "gender": "",
        "ownMachine": 1,
        "privacy": null,
        "socialNetworkId": null,
        "business": null,
        "businessType": null,
        "coffeeRoaster": null,
        "countryOther": null,
        "areaOperation": null,
        "brandServiced": null,
        "personOfContact": null,
        "phoneModel": null,
        "id": xxx,
        "phone": null,
        "mobile": null,
        "hobbiesProfessional": []
    }
}
```

## Get fleet information

`GET https://cms.lamarzocco.io/api/professional/fleet (optionally /get/{serialnumber})`

```json
{
    "status": true,
    "status_code": 200,
    "data": [
        {
            "uuid": "xxx",
            "name": "xxx",
            "communicationKey": "test-comunication-key",
            "customer": "{user_email}",
            "machine": {
                "uuid": "xxx",
                "name": null,
                "relayrDeviceId": "xxx",
                "edgehogDeviceId": 313,
                "model": {
                    "uuid": "xxx",
                    "name": "GB5",
                    "description": "GB5",
                    "slug": "gb5"
                },
                "ownerNumber": 3,
                "serialNumber": "xxx",
                "type": "MACHINE_INSTANCE"
            },
            "paringDate": "2024-07-12T18:45:36+00:00",
            "userType": "USERTYPE_ADMIN"
        }
    ]
}
```

### Get users on fleet machine

`GET https://cms.lamarzocco.io/api/professional/fleet/users/{{serial_number}}`

```json
{
    "status": true,
    "status_code": 200,
    "data": [
        {
            "uuid": "xxx",
            "image": null,
            "name": "xxx",
            "customerRole": "admin",
            "email": "{user0email}"
        },
        {
            "uuid": "xxx",
            "image": null,
            "name": "xxx",
            "customerRole": "admin",
            "email": "{user1email}"
        },
        {
            "uuid": "xxx",
            "image": null,
            "name": "axxx",
            "customerRole": "admin",
            "email": "{user2email}"
        }
    ]
}
```

### Latest measurement on fleet machine? The app doesn't appear to use this.

`GET https://cms.lamarzocco.io/api/professional/fleet/get/latest-measurement`

```json
{
    "status": false,
    "code": "machine_not_found",
    "errors": "Serial number provided don't return any machine"
}
```

### Fleet machine metrics - the app calls this every 30 seconds when in the foreground

`GET https://cms.lamarzocco.io/v1/professional/machines/awsproxy/{{serial_number}}/things/{{relayr_id}}/metrics`

expr:       COUNT
aggr_mode:  DAILY
from:       2024-07-13T23:00:00.000Z
to:         2024-07-14T23:00:00.000Z

```json
{
    "status": true,
    "data": {
        "FlushStoppedGroup2DoseBCounter": {
            "value": "399",
            "type": "number",
            "time": 1720788662474
        },
        "WaterConductivity": {
            "value": "303",
            "type": "number",
            "time": 1720796943866
        },
        "MachineConfiguration": {
            "value": {
                "subFamily": "AV",
                "machineCapabilities": [
                    {
                        "family": "GB5",
                        "groupsNumber": 2,
                        "coffeeBoilersNumber": 1,
                        "hasCupWarmer": false,
                        "hasCupWarmerButton": false,
                        "hasProportionalSteam": false,
                        "hasLowLevelSensor": true,
                        "hasBluetooth": false,
                        "hasMixingValue": false,
                        "coffeeBoilerSizeWatts": 1400,
                        "steamBoilerSizeWatts": 3000,
                        "cupWarmerHeaterSizeWatts": 150,
                        "machineVoltageVolts": 240,
                        "steamBoilersNumber": 1,
                        "teaDosesNumber": 1
                    }
                ],
                "groupCapabilities": [
                    {
                        "capabilities": {
                            "groupType": "AV_Group",
                            "groupNumber": "Group1",
                            "boilerId": "CoffeeBoiler1",
                            "hasScale": false,
                            "hasSolenoid": true,
                            "hasStraightInPortafilter": false,
                            "hasAutoCleanSolenoid": false,
                            "hasFlowmeter": true,
                            "hasNeckHeaterExists": false,
                            "hasRingHeaterExists": false,
                            "numberOfDoses": 4
                        },
                        "doses": [
                            {
                                "groupNumber": "Group1",
                                "doseIndex": "DoseA",
                                "doseType": "PulsesType",
                                "stopTarget": 95
                            },
                            {
                                "groupNumber": "Group1",
                                "doseIndex": "DoseB",
                                "doseType": "PulsesType",
                                "stopTarget": 332
                            },
                            {
                                "groupNumber": "Group1",
                                "doseIndex": "DoseC",
                                "doseType": "PulsesType",
                                "stopTarget": 550
                            },
                            {
                                "groupNumber": "Group1",
                                "doseIndex": "DoseD",
                                "doseType": "PulsesType",
                                "stopTarget": 275
                            }
                        ],
                        "doseMode": {
                            "groupNumber": "Group1",
                            "brewingType": "PulsesType"
                        }
                    },
                    {
                        "capabilities": {
                            "groupType": "AV_Group",
                            "groupNumber": "Group2",
                            "boilerId": "CoffeeBoiler1",
                            "hasScale": false,
                            "hasSolenoid": true,
                            "hasStraightInPortafilter": false,
                            "hasAutoCleanSolenoid": false,
                            "hasFlowmeter": true,
                            "hasNeckHeaterExists": false,
                            "hasRingHeaterExists": false,
                            "numberOfDoses": 4
                        },
                        "doses": [
                            {
                                "groupNumber": "Group2",
                                "doseIndex": "DoseA",
                                "doseType": "PulsesType",
                                "stopTarget": 95
                            },
                            {
                                "groupNumber": "Group2",
                                "doseIndex": "DoseB",
                                "doseType": "PulsesType",
                                "stopTarget": 332
                            },
                            {
                                "groupNumber": "Group2",
                                "doseIndex": "DoseC",
                                "doseType": "PulsesType",
                                "stopTarget": 550
                            },
                            {
                                "groupNumber": "Group2",
                                "doseIndex": "DoseD",
                                "doseType": "PulsesType",
                                "stopTarget": 275
                            }
                        ],
                        "doseMode": {
                            "groupNumber": "Group2",
                            "brewingType": "PulsesType"
                        }
                    }
                ],
                "boardDescriptor": [
                    {
                        "boardType": "GB5ButtonBoard",
                        "hardwareMajor": 3,
                        "hardwareMinor": 255,
                        "firmwareMajor": 255,
                        "firmwareMinor": 255,
                        "firmwareBugFix": 255
                    },
                    {
                        "boardType": "UniversalBoard24V",
                        "hardwareMajor": 0,
                        "hardwareMinor": 3,
                        "firmwareMajor": 0,
                        "firmwareMinor": 19,
                        "firmwareBugFix": 0
                    },
                    {
                        "boardType": "CDRWaterProbePosition2",
                        "hardwareMajor": 1,
                        "hardwareMinor": 255,
                        "firmwareMajor": 1,
                        "firmwareMinor": 24,
                        "firmwareBugFix": 0
                    },
                    {
                        "boardType": "Cortex5Board",
                        "hardwareMajor": 5,
                        "hardwareMinor": 255,
                        "firmwareMajor": 1,
                        "firmwareMinor": 2,
                        "firmwareBugFix": 0
                    }
                ],
                "serialNumber": [
                    {
                        "value": "xxx"
                    }
                ],
                "machineFirmwareVersion": [
                    {
                        "firmwareMajor": 1,
                        "firmwareMinor": 2,
                        "firmwareBugFix": 0,
                        "preRelease": ""
                    }
                ],
                "numberOfSettings": 249,
                "machineMode": "StandBy",
                "cupwarmerEnabled": false,
                "teaDoses": {
                    "DoseB": {
                        "doseIndex": "DoseB",
                        "stopTarget": 6
                    }
                },
                "teaDosesEnabled": true,
                "autoOnOffConfig": {
                    "onTimeHours": 7,
                    "onTimeMinutes": 15,
                    "offTimeHours": 16,
                    "offTimeMinutes": 0,
                    "closedDay": 0
                },
                "autoOnOffEnabled": true,
                "abrCoffeeMass": {
                    "Group1": 17,
                    "Group2": 17
                },
                "abrPortafilterMass": {
                    "Group1": 568.5,
                    "Group2": 568.5
                },
                "avModeBrewingPressure": {},
                "boilerTargetTemperature": {
                    "CoffeeBoiler1": 93.8,
                    "SteamBoiler": 122
                },
                "preinfusionModesAvailable": [
                    "ByGroup",
                    "ByDoseType"
                ],
                "preinfusionMode": {
                    "Group1": {
                        "groupNumber": "Group1",
                        "preinfusionStyle": "None"
                    },
                    "Group2": {
                        "groupNumber": "Group2",
                        "preinfusionStyle": "None"
                    }
                },
                "preinfusionSettings": {},
                "isLoaded": true
            },
            "type": "string",
            "time": 1720880609987
        },
        "FlushStoppedGroup2Time": {
            "value": "4.5",
            "type": "number",
            "time": 1720795957768
        },
        "presence": {
            "value": "connected",
            "type": "string",
            "time": 1720795566611
        },
        "TeaDoseEnabled": {
            "value": "true",
            "type": "string",
            "time": 1718386988770
        },
        "BrewingStoppedGroup2DoseBCounter": {
            "value": "390",
            "type": "number",
            "time": 1720793002489
        },
        "SettingAutoOnOffEnabled": {
            "value": "true",
            "type": "string",
            "time": 1718386988684
        },
        "SteamBoilerEnabled": {
            "value": "true",
            "type": "string",
            "time": 1718386988465
        },
        "FlushStoppedGroup2Volume": {
            "value": "186",
            "type": "number",
            "time": 1720795957810
        },
        "FlushStoppedGroup1Volume": {
            "value": "140",
            "type": "number",
            "time": 1720796953316
        },
        "FlushStoppedGroup2DoseCCounter": {
            "value": "73",
            "type": "number",
            "time": 1720795677783
        },
        "FlushStoppedGroup2DoseIndex": {
            "value": "DoseC",
            "type": "string",
            "time": 1720795677766
        },
        "SystemInfo": {
            "value": {
                "network_interfaces": [
                    {
                        "name": "wlan0",
                        "address": "10.10.10.2"
                    },
                    {
                        "name": "docker0",
                        "address": "172.17.0.1"
                    }
                ],
                "memory_info": {
                    "available": "7.0M",
                    "used": "483M",
                    "total": "490M"
                },
                "filesystem": {
                    "dir": "/usr/bin",
                    "available": "560M",
                    "used": "628M",
                    "total": "1.2G"
                },
                "uptime": "1 day,  3:02",
                "os_version": "20231102114141",
                "mac_addr": {
                    "eth0": "xxx",
                    "wlan": "xxx",
                    "bluetooth": "xxx"
                }
            },
            "type": "string",
            "time": 1720892868508
        },
        "BrewingStoppedGroup2DoseCCounter": {
            "value": "95",
            "type": "number",
            "time": 1720795895794
        },
        "SettingPreinfusionGroup1": {
            "value": "[{\"groupNumber\":\"Group1\",\"doseType\":\"ByGroup\",\"isPreWetTimeActive\":false,\"preWetTime\":0,\"isPreWetHoldTimeActive\":false,\"preWetHoldTime\":0},{\"groupNumber\":\"Group1\",\"doseType\":\"DoseA\",\"isPreWetTimeActive\":false,\"preWetTime\":0,\"isPreWetHoldTimeActive\":false,\"preWetHoldTime\":0},{\"groupNumber\":\"Group1\",\"doseType\":\"DoseB\",\"isPreWetTimeActive\":false,\"preWetTime\":0,\"isPreWetHoldTimeActive\":false,\"preWetHoldTime\":0},{\"groupNumber\":\"Group1\",\"doseType\":\"DoseC\",\"isPreWetTimeActive\":false,\"preWetTime\":0,\"isPreWetHoldTimeActive\":false,\"preWetHoldTime\":0},{\"groupNumber\":\"Group1\",\"doseType\":\"DoseD\",\"isPreWetTimeActive\":true,\"preWetTime\":5,\"isPreWetHoldTimeActive\":true,\"preWetHoldTime\":10}]",
            "type": "string",
            "time": 1706525074473
        },
        "FlushStoppedGroup2DoseDCounter": {
            "value": "30",
            "type": "number",
            "time": 1718289731617
        },
        "BrewingStoppedGroup1Time": {
            "value": "15.6",
            "type": "number",
            "time": 1720796792337
        },
        "BrewingStoppedGroup1DoseIndex": {
            "value": "DoseC",
            "type": "string",
            "time": 1720796429779
        },
        "BrewingStoppedGroup2DoseDCounter": {
            "value": "120",
            "type": "number",
            "time": 1720789799022
        },
        "FlushStoppedGroup1DoseACounter": {
            "value": "370",
            "type": "number",
            "time": 1720768192484
        },
        "gatewayFwVersion": {
            "value": "20231102114141",
            "type": "string",
            "time": 1720795568525
        },
        "BrewingStoppedGroup1DoseACounter": {
            "value": "2",
            "type": "number",
            "time": 1717622328133
        },
        "SettingAutoOnOffConfig": {
            "value": {
                "onTimeHours": 7,
                "onTimeMinutes": 15,
                "offTimeHours": 16,
                "offTimeMinutes": 0,
                "closedDay": 0
            },
            "type": "string",
            "time": 1718386988723
        },
        "FlushStoppedGroup1DoseBCounter": {
            "value": "219",
            "type": "number",
            "time": 1720698764963
        },
        "FlushStoppedGroup1Counter": {
            "value": "13874",
            "type": "number",
            "time": 1720795973289
        },
        "FlushStoppedGroup1Time": {
            "value": "3.7",
            "type": "number",
            "time": 1720796953275
        },
        "BrewingStoppedGroup1DoseContinuousCounter": {
            "value": "100",
            "type": "number",
            "time": 1720788748486
        },
        "CoffeeBoiler1UpdateSetPoint": {
            "value": "93.8",
            "type": "number",
            "time": 1720091842981
        },
        "SteamBoilerUpdateTemperature": {
            "value": "0",
            "type": "number",
            "time": 1720892920319
        },
        "BrewingStoppedGroup1DoseBCounter": {
            "value": "267",
            "type": "number",
            "time": 1720789789975
        },
        "FlushStoppedGroup1DoseCCounter": {
            "value": "66",
            "type": "number",
            "time": 1720795973289
        },
        "BrewingStoppedGroup2DoseContinuousCounter": {
            "value": "159",
            "type": "number",
            "time": 1720792320990
        },
        "FlushStoppedGroup2Counter": {
            "value": "16626",
            "type": "number",
            "time": 1720795677783
        },
        "BrewingStoppedGroup2DoseIndex": {
            "value": "DoseC",
            "type": "string",
            "time": 1720795895778
        },
        "BrewingStoppedGroup1DoseCCounter": {
            "value": "93",
            "type": "number",
            "time": 1720796429793
        },
        "TeaDoseSettings": {
            "value": {
                "doseIndex": "DoseB",
                "stopTarget": 6
            },
            "type": "string",
            "time": 1718386988813
        },
        "FlushStoppedGroup1DoseDCounter": {
            "value": "30",
            "type": "number",
            "time": 1717139157147
        },
        "WaterHardness": {
            "value": "139",
            "type": "number",
            "time": 1720796953817
        },
        "FlushStoppedGroup1DoseContinuousCounter": {
            "value": "86",
            "type": "number",
            "time": 1719397301642
        },
        "BrewingStoppedGroup1DoseDCounter": {
            "value": "56",
            "type": "number",
            "time": 1720442499953
        },
        "FlushStoppedGroup2DoseContinuousCounter": {
            "value": "118",
            "type": "number",
            "time": 1720524575289
        },
        "BrewingStoppedGroup1Volume": {
            "value": "561",
            "type": "number",
            "time": 1720796792385
        },
        "BrewingStoppedGroup2Volume": {
            "value": "561",
            "type": "number",
            "time": 1720795895855
        },
        "CoffeeBoiler1Enabled": {
            "value": "true",
            "type": "string",
            "time": 1718386988369
        },
        "CoffeeBoiler1UpdateTemperature": {
            "value": "0",
            "type": "number",
            "time": 1720892920774
        },
        "machineFwVersion": {
            "value": "1.2.0",
            "type": "string",
            "time": 1720795567121
        },
        "ABRPortafilterMassGroup2": {
            "value": "568.5",
            "type": "number",
            "time": 1718386988220
        },
        "ABRCoffeeMassGroup2": {
            "value": "17",
            "type": "number",
            "time": 1718386988130
        },
        "ABRPortafilterMassGroup1": {
            "value": "568.5",
            "type": "number",
            "time": 1718386988084
        },
        "ABRCoffeeMassGroup1": {
            "value": "17",
            "type": "number",
            "time": 1718386988047
        },
        "BrewingStoppedGroup1Counter": {
            "value": "2840",
            "type": "number",
            "time": 1720796429793
        },
        "BrewingSnapshotGroup2": {
            "value": {
                "groupConfiguration": {
                    "groupNumber": "Group2",
                    "capabilities": {
                        "groupType": "AV_Group",
                        "boilerId": "CoffeeBoiler1",
                        "boilerTemperature": 93.8,
                        "hasScale": false,
                        "hasSolenoid": true,
                        "hasStraightInPortafilter": false,
                        "hasAutoCleanSolenoid": false,
                        "hasFlowmeter": true,
                        "hasNeckHeaterExists": false,
                        "hasRingHeaterExists": false
                    },
                    "dose": {
                        "doseIndex": "DoseC",
                        "doseType": "PulsesType",
                        "stopTarget": 550
                    },
                    "doseMode": {
                        "brewingType": "PulsesType"
                    }
                },
                "waterProperties": {
                    "conductivity": 311,
                    "hardness": 144
                },
                "brewingInfo": {
                    "abrTarget": 0,
                    "abrCoffeeMass": 17,
                    "abrPortafilterMass": 568.5,
                    "doseIndex": "DoseC",
                    "mass": 0,
                    "stopReason": "Automatic",
                    "stopType": "Volumetric",
                    "time": 16,
                    "volume": 561
                }
            },
            "type": "string",
            "time": 1720795896002
        },
        "BrewingSnapshotGroup1": {
            "value": {
                "groupConfiguration": {
                    "groupNumber": "Group1",
                    "capabilities": {
                        "groupType": "AV_Group",
                        "boilerId": "CoffeeBoiler1",
                        "boilerTemperature": 90.41,
                        "hasScale": false,
                        "hasSolenoid": true,
                        "hasStraightInPortafilter": false,
                        "hasAutoCleanSolenoid": false,
                        "hasFlowmeter": true,
                        "hasNeckHeaterExists": false,
                        "hasRingHeaterExists": false
                    },
                    "dose": {
                        "doseIndex": "DoseC",
                        "doseType": "PulsesType",
                        "stopTarget": 550
                    },
                    "doseMode": {
                        "brewingType": "PulsesType"
                    }
                },
                "waterProperties": {
                    "conductivity": 285,
                    "hardness": 131
                },
                "brewingInfo": {
                    "abrTarget": 0,
                    "abrCoffeeMass": 17,
                    "abrPortafilterMass": 568.5,
                    "doseIndex": "DoseC",
                    "mass": 0,
                    "stopReason": "Automatic",
                    "stopType": "Volumetric",
                    "time": 15.6,
                    "volume": 561
                }
            },
            "type": "string",
            "time": 1720796792499
        },
        "BrewingStoppedGroup2Counter": {
            "value": "3551",
            "type": "number",
            "time": 1720795895794
        },
        "BrewingStoppedGroup2Time": {
            "value": "16",
            "type": "number",
            "time": 1720795895816
        },
        "FlushStoppedGroup1DoseIndex": {
            "value": "DoseC",
            "type": "string",
            "time": 1720795973272
        },
        "SteamBoilerUpdateSetPoint": {
            "value": "122",
            "type": "number",
            "time": 1718387307687
        },
        "FlushStoppedGroup2DoseACounter": {
            "value": "585",
            "type": "number",
            "time": 1720788788977
        },
        "BrewingStoppedGroup2DoseACounter": {
            "value": "3",
            "type": "number",
            "time": 1717622360159
        }
    }
}
```
### Fleet machine metrics between dates - The app uses this with a filter to update the group information periodically when active in that section (if no local websocket connection).

`GET https://cms.lamarzocco.io/v1/professional/machines/awsproxy/{{serial_number}}/things/{{relayr_id}}/aggregate-metrics?expr=COUNT&aggr_mode=DAILY&from=2024-07-11T21:19:20.567Z&to=2024-07-12T21:19:20.567Z`

expr: COUNT
aggr_mode: DAILY
from: YYYY-MM-DDThh:mm:sssZ
to: YYYY-MM-DDThh:mm:sssZ
filterOn:   FlushStoppedGroup1Time,FlushStoppedGroup2Time,BrewingStoppedGroup1Time,BrewingStoppedGroup2Time \\ etc.

// This is pretty slow to retrieve all metrics, and often seems to timeout if no filter is applied

```json
{
    "data": {
        "FlushStoppedGroup2Time": [
            {
                "value": "2",
                "type": "double",
                "time": 1720569600000
            }
        ],
        "BrewingStoppedGroup1Time": [
            {
                "value": "1",
                "type": "double",
                "time": 1720569600000
            }
        ],
        "FlushStoppedGroup1Time": [
            {
                "value": "1",
                "type": "double",
                "time": 1720569600000
            }
        ],
        "BrewingStoppedGroup2Time": [
            {
                "value": "4",
                "type": "double",
                "time": 1720569600000
            }
        ]
    },
    "status": true
}
```


## Machine models

`GET https://cms.lamarzocco.io/api/machine-models`

```json
{
    "status": true,
    "status_code": 200,
    "data": [
        {
            "uuid": "19bd559a-f126-4a65-81c0-a96f7c27034f",
            "name": "GS3 AV",
            "description": "GS3 AV",
            "slug": "gs3_av",
            "image": "https://cms.lamarzocco.io/uploads/images/5dcab5ec2b8f6741902629.jpg"
        },
        {
            "uuid": "5751e453-febc-4f02-b04a-aeae4f5be701",
            "name": "GS3 MP",
            "description": "GS3 MP",
            "slug": "gs3_mp",
            "image": "https://cms.lamarzocco.io/uploads/images/5dcab5c84b659659205853.jpg"
        },
        {
            "uuid": "9c8752bb-1272-472b-a853-0786d5c4acce",
            "name": "Linea Mini",
            "description": "Linea Mini",
            "slug": "linea_mini",
            "image": "https://cms.lamarzocco.io/uploads/images/5dcab5a205652870795461.png"
        },
        {
            "uuid": "903d8906-22dd-4c2d-969e-a8fac299f0a1",
            "name": "GB5",
            "description": "GB5",
            "slug": "gb5",
            "image": "https://cms.lamarzocco.io/uploads/images/609d2aa264832035709393.png"
        },
        {
            "uuid": "58fb9611-eebc-496a-86e8-566f8d3d702d",
            "name": "KB90",
            "description": "KB90",
            "slug": "kb90",
            "image": "https://cms.lamarzocco.io/uploads/images/617161f5b676a091194575.png"
        },
        {
            "uuid": "750cd2cc-060b-49d0-8271-fdaae0948ea3",
            "name": "LineaPB",
            "description": "Linea PB model",
            "slug": "lineapb",
            "image": "https://cms.lamarzocco.io/uploads/images/620a37cf52c39277499087.png"
        },
        {
            "uuid": "d2ba1aa3-b4d3-4016-91a0-47653e6e3e30",
            "name": "LCR",
            "description": "Linea Classica Model",
            "slug": "lcr",
            "image": "https://cms.lamarzocco.io/uploads/images/62bd509bdf2d4611207957.png"
        },
        {
            "uuid": "005de228-77ac-49af-b2b7-359863af854f",
            "name": "Micra",
            "description": "Micra",
            "slug": "micra",
            "image": null
        },
        {
            "uuid": "3842d5de-09e8-4c97-a251-ebd8c25bf022",
            "name": "Linea Mini R",
            "description": "Linea Mini R",
            "slug": "linea_mini_r",
            "image": null
        },
        {
            "uuid": "dcc65b50-3561-4993-92ea-bc95b11a23bc",
            "name": "Pico Grinder",
            "description": "Pico Grinder",
            "slug": "pico_grinder",
            "image": null
        },
        {
            "uuid": "7e74409e-19bb-4b57-8d6a-adf66d8a8756",
            "name": "Strada X",
            "description": "Strada X",
            "slug": "strada_x",
            "image": "https://cms.lamarzocco.io/uploads/images/6560c00e015f2242560121.png"
        },
        {
            "uuid": "889da121-dbbb-411e-879d-a3c480547fe4",
            "name": "Strada AV",
            "description": "StradaS",
            "slug": "strada_av",
            "image": null
        },
        {
            "uuid": "e3d1e37c-8414-46e9-8264-126d1a2243c6",
            "name": "Strada S",
            "description": "Strada S model",
            "slug": "strada_s",
            "image": "https://cms.lamarzocco.io/uploads/images/65280a37232e2283259792.png"
        },
        {
            "uuid": "e395b934-657b-420e-9871-697a60ea40ac",
            "name": "Swan Grinder",
            "description": "Swan Grinder",
            "slug": "swan_grinder",
            "image": null
        }
    ]
}
```

## Get countries

`GET https://cms.lamarzocco.io/api/countries`

```json
{
    "status": true,
    "status_code": 200,
    "data": [
        {
            "uuid": "dd4dce8a-3a24-47d2-a1bc-06f9d012d29f",
            "name": "Italia",
            "alpha2Code": "IT",
            "country": "it_IT"
        },
        {
            "uuid": "6750cd9e-5e8c-4286-aff8-01af43850a18",
            "name": "USA",
            "alpha2Code": "US",
            "country": "en_US"
        },
        {
            "uuid": "3cd1793e-240d-4af6-96bc-17556c9bd81f",
            "name": "United Kingdom",
            "alpha2Code": "UK",
            "country": "en_GB"
        },
        {
            "uuid": "0af14faf-d362-4039-82d4-c162250d3553",
            "name": "Germany",
            "alpha2Code": "DE",
            "country": "de_DE"
        },
        {
            "uuid": "798b2b78-e52c-4c13-a6fa-93b43f750eb9",
            "name": "Spain",
            "alpha2Code": "ES",
            "country": "es_ES"
        },
        {
            "uuid": "1705498d-55fd-46bf-bd09-a4c9491ad75a",
            "name": "Australia",
            "alpha2Code": "AU",
            "country": "en_AU"
        },
        {
            "uuid": "286e5255-10bc-4478-9faa-7ae325324a23",
            "name": "New Zealand",
            "alpha2Code": "NZ",
            "country": "en_NZ"
        },
        {
            "uuid": "b2452033-36a7-41b6-8112-16e07076c0b4",
            "name": "Other",
            "alpha2Code": "EN",
            "country": "ot_OT"
        },
        {
            "uuid": "b6535af9-6c34-46fb-b452-839610c5a8d0",
            "name": "China",
            "alpha2Code": "CN",
            "country": "zh_CN"
        },
        {
            "uuid": "96d1c4e3-e9e4-4a62-9d89-3503662ef263",
            "name": "South Korea",
            "alpha2Code": "KR",
            "country": "ko_KR"
        },
        {
            "uuid": "7bb13a8b-bf58-42ac-9696-63d9d70ebc28",
            "name": "Kuwait",
            "alpha2Code": "KW",
            "country": "ar_KW"
        },
        {
            "uuid": "4e928cc7-c629-4573-b1ad-434874aaf055",
            "name": "Qatar",
            "alpha2Code": "QA",
            "country": "ar_QA"
        },
        {
            "uuid": "c91824fc-1121-4534-ad00-e9a46362f1fd",
            "name": "United Arab Emirates",
            "alpha2Code": "AE",
            "country": "ar_AE"
        },
        {
            "uuid": "f1ebdd3a-9139-4991-b39a-c6d2fae347aa",
            "name": "Saudi Arabia",
            "alpha2Code": "SA",
            "country": "ar_SA"
        },
        {
            "uuid": "eec9865b-0e2a-4ae6-b7bb-ac4c99e6c434",
            "name": "Bahrein",
            "alpha2Code": "BH",
            "country": "ar_BH"
        },
        {
            "uuid": "a0bedece-f058-4106-a049-73045e25d5af",
            "name": "Russia",
            "alpha2Code": "RU",
            "country": "en_RU"
        },
        {
            "uuid": "df507afb-ebda-4b2b-a75a-f839f335cfe1",
            "name": "Cyprus",
            "alpha2Code": "CY",
            "country": "el_CY"
        },
        {
            "uuid": "a1bf34e2-a5f1-4528-bfae-d4daad213d8a",
            "name": "Israel",
            "alpha2Code": "IL",
            "country": "en_IL"
        },
        {
            "uuid": "d73b3872-985d-4b0b-8934-a41358495af8",
            "name": "France",
            "alpha2Code": "FR",
            "country": "fr_FR"
        },
        {
            "uuid": "6ada7f47-e349-4058-8731-5aa2e461cea2",
            "name": "Ireland",
            "alpha2Code": "IE",
            "country": "en_IE"
        },
        {
            "uuid": "70d42ed9-46b0-4b3b-9821-617d7da9a190",
            "name": "South Africa",
            "alpha2Code": "ZA",
            "country": "en_ZA"
        },
        {
            "uuid": "6990d341-f087-4744-bc14-550a240870c8",
            "name": "Norway",
            "alpha2Code": "NO",
            "country": "en_NO"
        },
        {
            "uuid": "a83cdc0b-a233-4962-ba53-fa72023eee13",
            "name": "Denmark",
            "alpha2Code": "DK",
            "country": "en_DK"
        },
        {
            "uuid": "8967c21d-160d-42e2-a682-8a50952cefa8",
            "name": "Austria",
            "alpha2Code": "AT",
            "country": "de_AT"
        }
    ]
}
```

## Get pro app news

`GET https://cms.lamarzocco.io/api/professional/news`

```json
{
    "status": true,
    "status_code": 200,
    "data": {
        "news": [
            {
                "uuid": "379c6abe-71c7-4c9b-96ba-13378a3654e3",
                "name": "La Marzocco Home App v3.1.0 is out!",
                "description": "<p>snip</p>",
                "createdAt": "2023-07-24T12:44:04+00:00",
                "updatedAt": "2024-03-29T08:56:50+00:00",
                "subtitle": null,
                "image": "https://cms.lamarzocco.io/uploads/images/65f946fd99609846154779.PNG",
                "videoUri": null,
                "descriptionSecond": null
            },
            {
                "uuid": "3e480bfd-67e0-4b61-b15e-24d971f38d16",
                "name": "Linea Micra_How to use the La Marzocco Home app",
                "description": "<p>snip</p>",
                "createdAt": "2023-01-12T15:20:26+00:00",
                "updatedAt": "2023-02-20T10:08:32+00:00",
                "subtitle": null,
                "image": "https://cms.lamarzocco.io/uploads/images/63c0253a47644275613921.jpg",
                "videoUri": "https://www.youtube.com/embed/Icjf9Gwp9CI",
                "descriptionSecond": null
            },
            {
                "uuid": "6de83f6d-d692-42ce-a9e6-6759f53cdfc1",
                "name": "Unboxing your Linea Micra",
                "description": "<p>Set up your Linea Micra and make it the centerpiece of your kitchen.</p>",
                "createdAt": "2023-01-12T15:17:25+00:00",
                "updatedAt": "2023-02-16T14:24:48+00:00",
                "subtitle": null,
                "image": "https://cms.lamarzocco.io/uploads/images/63c02485c7c79961557604.jpg",
                "videoUri": "https://www.youtube.com/embed/OYABu67FZAY",
                "descriptionSecond": null
            },
            {
                "uuid": "b686d8b6-4f25-4c25-85f9-9d7b51ae6dcc",
                "name": "Linea Micra_ How to replace shower screen and gasket",
                "description": "<p>snip</p>",
                "createdAt": "2023-01-12T15:12:57+00:00",
                "updatedAt": "2023-02-20T10:09:26+00:00",
                "subtitle": null,
                "image": "https://cms.lamarzocco.io/uploads/images/63c0237919498038645852.jpg",
                "videoUri": "https://www.youtube.com/embed/xhvaMHAejOE",
                "descriptionSecond": null
            },
            {
                "uuid": "07ebe0a6-846f-4d15-9ff0-fc757e2acaa6",
                "name": "How to connect your Linea Micra",
                "description": "<p>snip</p>",
                "createdAt": "2023-01-12T15:09:17+00:00",
                "updatedAt": "2023-02-20T10:10:03+00:00",
                "subtitle": null,
                "image": "https://cms.lamarzocco.io/uploads/images/63c0229ddb8df802814385.jpg",
                "videoUri": "https://www.youtube.com/embed/aP-DuqK4RNU",
                "descriptionSecond": null
            },
            {
                "uuid": "7cfffcb0-1119-4ef0-b234-01acda7860c5",
                "name": "Linea Micra, first installation",
                "description": "<p>A step-by-step guide to setting up the Linea Micra.</p>",
                "createdAt": "2023-01-12T14:53:57+00:00",
                "updatedAt": "2023-02-20T10:11:27+00:00",
                "subtitle": null,
                "image": "https://cms.lamarzocco.io/uploads/images/63c01f05a400b448603413.jpg",
                "videoUri": "https://www.youtube.com/embed/FF9EMEP5V6Y",
                "descriptionSecond": null
            },
            {
                "uuid": "901e5cca-2146-45d1-9515-243fc3afcbe1",
                "name": "Linea Micra, convertible portafilter",
                "description": "<p>snip</p>",
                "createdAt": "2023-01-12T14:47:45+00:00",
                "updatedAt": "2023-02-20T10:12:24+00:00",
                "subtitle": null,
                "image": "https://cms.lamarzocco.io/uploads/images/63c01d91b215e263631286.jpg",
                "videoUri": "https://www.youtube.com/embed/DV6r-65--ow",
                "descriptionSecond": null
            },
            {
                "uuid": "402a537d-5d3b-4315-8fea-ea6a28207ff8",
                "name": "Hello Linea Micra",
                "description": "<p>snip</p>",
                "createdAt": "2022-11-08T15:38:05+00:00",
                "updatedAt": "2023-02-20T10:13:58+00:00",
                "subtitle": "Bring the cafe home",
                "image": "https://cms.lamarzocco.io/uploads/images/636a77dd467a8319506044.JPG",
                "videoUri": "https://www.youtube.com/embed/AxWE91DuOw0",
                "descriptionSecond": null
            },
            {
                "uuid": "7728d8cb-89f1-4b1b-baf7-527a2bbadfdc",
                "name": "La Marzocco Home App V. 2 is Now Live",
                "description": "<p>snip</p>",
                "createdAt": "2022-10-25T12:46:11+00:00",
                "updatedAt": "2022-10-25T14:28:02+00:00",
                "subtitle": "Introducing Pre-Infusion on the Linea Mini, Auto-Backflush, Boiler Control, and more.",
                "image": "https://cms.lamarzocco.io/uploads/images/6357ddc89b783286612576.png",
                "videoUri": "https://www.youtube.com/embed/_AfBYkDbbpQ",
                "descriptionSecond": "<p>snip</p>"
            },
            {
                "uuid": "1f41ccef-1ad6-4320-b793-27a82d123fba",
                "name": "a new recipe and a good coffee: welcome home!",
                "description": "<p>snip</p>",
                "createdAt": "2019-05-22T13:03:47+00:00",
                "updatedAt": "2020-03-12T15:05:40+00:00",
                "subtitle": "A good espresso and an oats granola with berries to start your day differently. Here's a quick and healthy recipe for your breakfast",
                "image": "https://cms.lamarzocco.io/uploads/images/5e4a663a3ecd2881532285.jpg",
                "videoUri": null,
                "descriptionSecond": null
            },
            {
                "uuid": "22d164e3-31f8-458c-a2cf-497076fadd58",
                "name": "humans of la marzocco home: Piero Bambi story",
                "description": "<p>snip</p>",
                "createdAt": "2019-05-22T13:01:01+00:00",
                "updatedAt": "2020-03-12T15:05:03+00:00",
                "subtitle": "When did Piero Bambi, La Marzocco Honorary President, start building espresso machines?",
                "image": "https://cms.lamarzocco.io/uploads/images/5e4a5a851ce16042393387.jpg",
                "videoUri": null,
                "descriptionSecond": null
            }
        ],
        "tags": [
            {
                "uuid": "91ebc080-dee3-486c-9bfc-73fbbdcbba60",
                "name": "food",
                "description": "food"
            },
            {
                "uuid": "673f6536-e51b-4e9d-b9da-42d8401c7a3d",
                "name": "lifestyle",
                "description": "lifestyle"
            }
        ],
        "currentTag": null
    }
}
```

## Latest privacy policy

`GET https:/cms.lamarzocco.com/api/professional/privacy/latest-to-accept`

```json
{
    "status": true,
    "status_code": 200,
    "data": {
        "uuid": "8e22a214-9654-42ce-af99-f2bd6331ec66",
        "name": "2022.07.28",
        "privacyVersion": 2,
        "parentTranslate": null,
        "lang": null,
        "title": "2022.07.28",
        "mainTitle": "<p>&lt;p&gt;The &lt;a href=&quot;https://cms.lamarzocco.io/privacy&quot;&gt;Terms of Service&lt;/a&gt; and the &lt;a href=&quot;https://cms.lamarzocco.io/privacy&quot;&gt;Privacy Policy&lt;/a&gt;&amp;nbsp;have been updated. We ask you read the new documen",
        "textPrivacy": "<p>snip</p>",
        "labelDisposalCommercial": "Direct Marketing",
        "textDisposalCommercial": "<p>to receive information and promotional material concerning La Marzocco activities, products and services, and to be contacted for market surveys</p>",
        "labelDisposalThirdParty": "Disclosure to third parties",
        "textDisposalThirdParty": "<p>to the disclosure of my Data to third-party companies for their own direct marketing purposes</p>",
        "labelDisposalProfile": "Profiling",
        "textDisposalProfile": "<p>to the analysis of my interests, habits and choices (related to both purchasing and the use of La Marzocco digital services), even in order to receive customised information and promotional material</p>",
        "footerTextPrivacy": "<p>&lt;p&gt;By tapping update, you agree with our &lt;a href=&quot;https://cms.lamarzocco.io/privacy&quot;&gt;Terms of Service&lt;/a&gt; and &lt;a href=&quot;https://cms.lamarzocco.io/privacy&quot;&gt;Privacy Policy&lt;/a&gt;&lt;/p&gt;</p>"
    }
}
```
