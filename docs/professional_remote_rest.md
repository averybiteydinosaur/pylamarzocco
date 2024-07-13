# Cloud REST API

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

### Latest measurement on fleet machine?

`GET https://cms.lamarzocco.io/api/professional/fleet/get/latest-measurement`

```json
{
    "status": false,
    "code": "machine_not_found",
    "errors": "Serial number provided don't return any machine"
}
```

### Fleet machine metrics

`GET https://cms.lamarzocco.io/v1/professional/machines/awsproxy/{{serial_number}}/things/{{relayr_id}}/metrics`

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
### Fleet machine metrics between dates

`GET https://cms.lamarzocco.io/v1/professional/machines/awsproxy/{{serial_number}}/things/{{relayr_id}}/aggregate-metrics?expr=COUNT&aggr_mode=DAILY&from=2024-07-11T21:19:20.567Z&to=2024-07-12T21:19:20.567Z`

expr: COUNT
aggr_mode: DAILY
from: YYYY-MM-DDThh:mm:sssZ
to: YYYY-MM-DDThh:mm:sssZ

```json
to come, sometimes seems to time out 524 cloudflare
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
                "description": "<p>La Marzocco Home app v3.1.0 has been released!</p>\r\n\r\n<p>This version allows you to update your machine's gateway to 3.4-rc5. Follow the notification in the information section of the app to update your machine.</p>\r\n\r\n<p>These new updates bring some exciting features to La Marzocco Home App, such as a new Auto Standby Logic, the Power Options, and Automatic Daylight Saving Time Management.</p>\r\n\r\n<p>The new Auto Standby Logic will allow you to instruct your machine to go into standby after a specific time following the end of a brew or from when the machine was turned on. The specific amount of time is customizable, and is an optional feature allowing for energy savings.</p> \r\n\r\n<p>The Power Options replace the Weekly Schedule.</p>\r\n<p>You can now set up to 25 different on/off slots for your machine, also allowing you to decide whether your steam boiler also needs to turn on. During a programmed power-on slot, the auto standby logic will not be enabled to ensure your machine is ready to brew according to your schedule.</p>\r\n\r\n<p>The latest gateway firmware update also includes Automatic Daylight Saving Time Management. This allows your machine to automatically be in sync with your timezone and ready for daylight saving time changes. Once your machine is updated, connect to it \"locally\" (green line at the top of the screen with the Wi-Fi symbol on the right) to enable it.</p>",
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
                "description": "<p>Connect your smartphone with your Linea Micra and learn about all of the built-in features including pre-infusion, pre-brewing, boiler control</p>",
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
                "description": "<p>Preventive maintenance is important to keep your machine in good condition and running. Learn how to replace the shower screen and gasket in this easy step-by-step guide.</p>",
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
                "description": "<p>Take advantage of quick control access of your Linea Micra via the La Marzocco Home app.</p>\r\n\r\n<p>Adjust temperature, control settings, use auto-backflush, and power your machine on and off with a custom schedule.</p>\r\n\r\n<p>Learn how to connect your Linea Micra by following this easy step by step guide.</p>",
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
                "description": "<p>Linea Micra&#39;s three-in-one convertible portafilter is easy to clean with a design that allows you to quickly change between a single-spout, double-spout, and bottomless portafilter.</p>\r\n\r\n<p>The removable spout attachments are made of Radel&mdash;a special hi-tech polymer&mdash;that is resistant to heat, acid, aging, abrasion, and staining​.</p>",
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
                "description": "<p>With this shoutout and new product - taking inspiration from an industry icon, true to the spirit and heritage of La Marzocco -&nbsp;we are thrilled to announce the release&nbsp;of Linea Micra: yet another step in&nbsp;furthering coffee knowledge, professionalism, and cup quality with all aficionados around the globe!</p>\r\n\r\n<p>Our team of engineers have worked hard and passionately to design an espresso machine that would be worthy of caf&eacute; status and culture.</p>\r\n\r\n<p>With its sleek contour and charming, simple-to-use form, Linea Micra raises the bar in the kitchen and in the everyday coffee ritual.&nbsp;</p>\r\n\r\n<p>A scaled-down reflection of La Marzocco&#39;s legendary Linea Classic... the younger and more compact version, the Linea Micra, embodies style, performance, Florentine craft, and world class innovation.</p>\r\n\r\n<p>Join us as we present product news, brand highlights, lifestyle content and community gatherings such as the &quot;Open House&quot; events - respectively online across our blog, newsletter, Instagram handle, and via &quot;Live&quot; onsite format in beautiful showrooms and&nbsp;major cities&nbsp;from New York to London, Paris to Auckland, or Florence to Singapore just to name a few ...&nbsp;</p>\r\n\r\n<p>The La Marzocco team invites you to learn more about the latest Home machine, combining a dynamic feature set and small body that allows you to explore all things espresso.&nbsp;</p>\r\n\r\n<p><br />\r\nBring the cafe home!&nbsp;Linea Micra is here.</p>\r\n\r\n<p><br />\r\nVisit our dedicated <a href=\"https://international.lamarzoccohome.com/en/linea-micra\">web page</a> to learn more about the product features.</p>\r\n\r\n<p>&nbsp;</p>",
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
                "description": "<p>Introducing Pre-Infusion on the Linea Mini, Auto-Backflush, Boiler Control, and more.</p>\r\n\r\n<p>We&rsquo;re excited to announce that La Marzocco Home App 2.0 is now live. This version introduces Pre-Infusion on plumbed-in Linea Minis, Auto-Backflush on all connected machines, Boiler Control, and more. Update the app to take control of your machine, and get all the latest features on your connected La Marzocco home espresso machine.</p>\r\n\r\n<p style=\"margin-left:360px\"><strong>Overview of Features</strong></p>\r\n\r\n<p>&nbsp;</p>",
                "createdAt": "2022-10-25T12:46:11+00:00",
                "updatedAt": "2022-10-25T14:28:02+00:00",
                "subtitle": "Introducing Pre-Infusion on the Linea Mini, Auto-Backflush, Boiler Control, and more.",
                "image": "https://cms.lamarzocco.io/uploads/images/6357ddc89b783286612576.png",
                "videoUri": "https://www.youtube.com/embed/_AfBYkDbbpQ",
                "descriptionSecond": "<p>In addition to these new features, connected machine owners will have access to the following<strong>:</strong></p>\r\n\r\n<p>&ndash; Remote ability to turn the machine on or off</p>\r\n\r\n<p>&ndash; Creation of an on/off schedule</p>\r\n\r\n<p>&ndash; Boiler temperature status and control</p>\r\n\r\n<p>&ndash; Enabling and setting pre-brewing on/off times</p>\r\n\r\n<p>&ndash; Machine Stats &amp; Total Shot Counter</p>\r\n\r\n<p>&ndash; Setting of auto-volumetrics on the GS3 by number of &ldquo;pulses&rdquo;</p>\r\n\r\n<p>&nbsp;</p>\r\n\r\n<p><em>Linea Minis with serial numbers starting with&nbsp;<strong>LM015906</strong>&nbsp;and GS3s starting with serial number&nbsp;<strong>GS012984</strong>&nbsp;come standard with the new connected board.</em></p>\r\n\r\n<p>&nbsp;</p>\r\n\r\n<p>&nbsp;</p>\r\n\r\n<p style=\"margin-left:400px\"><br />\r\n&nbsp;</p>"
            },
            {
                "uuid": "1f41ccef-1ad6-4320-b793-27a82d123fba",
                "name": "a new recipe and a good coffee: welcome home!",
                "description": "<p>Dried fruits and nuts are great snacks for controlling your appetite throughout the day, whilst also providing a valuable source of vitamins and natural antioxidants.</p>\r\n\r\n<p>For a great coffee pairing, we suggest an Ethiopian, naturally processed, coffee with fruity acidic notes and smooth chocolate aftertaste- brewed with the Linea Mini. Follow the recipe and&hellip;Welcome Home!</p>\r\n\r\n<p><strong>GRANOLA RECIPE</strong></p>\r\n\r\n<p><strong>Ingredients:</strong></p>\r\n\r\n<ul>\r\n\t<li>3 cups BIO rolled oats</li>\r\n\t<li>1 1&frasl;2 &nbsp;cups high quality nuts (such as PGI Piemonte hazelnuts, almonds or nuts)</li>\r\n\t<li>1 cup seeds (sunflowers, squash and sesame)</li>\r\n\t<li>1&frasl;2 cup dried fruit (cranberries, raspberries or coconut or banana)</li>\r\n\t<li>1&frasl;2 cup BIO chestnut honey</li>\r\n\t<li>2 tablespoons whole brown sugar</li>\r\n\t<li>1&frasl;4 cup sesame oil or extra virgin olive oil</li>\r\n</ul>\r\n\r\n<p>Chop the nuts coarsely and preheat the oven to 260&deg;.<br />\r\nIn a large skillet melt the honey along with the oil, then toast the oats, chopped nuts and seeds. Add the sugar and the dried fruits and mix well for a few minutes.</p>\r\n\r\n<p>Place a sheet of baking paper in the base of baking tray, and cook for about 40 minutes, stirring once during the cooking process. Once cooled, you can keep the granola in an airtight container for about 10 days.</p>\r\n\r\n<p>This dish is excellent for a healthy morning boost but served with yogurt, fresh fruits and accompanied by a good espresso, it really elevates it to sheer breakfast excellence!</p>",
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
                "description": "<p>My first memories are about espresso machines. Coffee came later.<br />\r\nWhen I was a kid I just needed to go downstairs to be in the workshop. Getting to know mechanics was way easier than learning to recognize a good espresso. I used to join my father and uncle for machine installations around Tuscany and those are the first coffees I remember drinking. That&rsquo;s also because when you are a kid, you usually just drink caffellatte. When I was 14, I went with my uncle to install a lever machine at a caf&egrave; and two usual customers were there to assist the entire installation. Once we were done, my uncle offered them an espresso.</p>\r\n\r\n<p>He asked them if they found the coffee tasty and they replied that they preferred the one brewed with the old machine. Then the caf&egrave; owner grabbed a portafilter with some old coffee grounds and added some new grounds. The two customers found it excellent. Caffeine gives you addiction so when you get used to a certain blend, it is hard to change. That episode taught me not to ask how the coffee tastes, but instead to say something like &ldquo;It&rsquo;s good. Isn&rsquo;t it?&rdquo;; this way I express my thought on a certain blend and I tend to encourage a positive opinion.</p>",
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

