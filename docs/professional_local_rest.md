#

## The app attempts

## Get latest measurements (local)

`GET https://{local-ip}:8081/latest-measurement`
Authorization: Bearer {localtoken}

```json
[
    {
        "name": "FlushStoppedGroup2Volume",
        "recorded": "2024-07-12T14:52:43Z",
        "value": "186.000000"
    },
    {
        "name": "SteamBoilerUpdateSetPoint",
        "recorded": "2024-06-14T17:48:27Z",
        "value": "122.000000"
    },
    {
        "name": "BrewingUpdateGroup1Volume",
        "recorded": "2024-07-12T15:09:12Z",
        "value": "140.000000"
    },
    {
        "name": "BrewingStoppedGroup2StopReason",
        "recorded": "2024-07-12T14:51:35Z",
        "value": "Automatic"
    },
    {
        "name": "HotWaterStopReason",
        "recorded": "2024-07-12T14:52:46Z",
        "value": "ByButton"
    },
    {
        "name": "BrewingStartedGroup2TimeTarget",
        "recorded": "2024-07-03T20:35:05Z",
        "value": "120.000000"
    },
    {
        "name": "CoffeeBoiler1Enabled",
        "recorded": "2024-06-14T17:43:17Z",
        "value": "true"
    },
    {
        "name": "FlushSnapshotGroup1",
        "recorded": "2024-07-12T15:09:13Z",
        "value": "{\"groupConfiguration\":{\"groupNumber\":\"Group1\",\"capabilities\":{\"groupType\":\"AV_Group\",\"boilerId\":\"CoffeeBoiler1\",\"boilerTemperature\":94.49,\"hasScale\":false,\"hasSolenoid\":true,\"hasStraightInPortafilter\":false,\"hasAutoCleanSolenoid\":false,\"hasFlowmeter\":true,\"hasNeckHeaterExists\":false,\"hasRingHeaterExists\":false},\"dose\":{\"doseIndex\":\"DoseC\",\"doseType\":\"PulsesType\",\"stopTarget\":550},\"doseMode\":{\"brewingType\":\"PulsesType\"}},\"waterProperties\":{\"conductivity\":303,\"hardness\":140},\"flushInfo\":{\"abrTarget\":0,\"abrCoffeeMass\":17,\"abrPortafilterMass\":568.5,\"doseIndex\":\"DoseC\",\"mass\":0,\"time\":3.7,\"volume\":140}}"
    },
    {
        "name": "FlushStoppedGroup2FlowRate",
        "recorded": "2024-07-12T14:52:43Z",
        "value": "0.000000"
    },
    {
        "name": "TeaDoseEnabled",
        "recorded": "2024-06-14T17:43:17Z",
        "value": "true"
    },
    {
        "name": "FlushSnapshotGroup2",
        "recorded": "2024-07-12T14:52:43Z",
        "value": "{\"groupConfiguration\":{\"groupNumber\":\"Group2\",\"capabilities\":{\"groupType\":\"AV_Group\",\"boilerId\":\"CoffeeBoiler1\",\"boilerTemperature\":93.6,\"hasScale\":false,\"hasSolenoid\":true,\"hasStraightInPortafilter\":false,\"hasAutoCleanSolenoid\":false,\"hasFlowmeter\":true,\"hasNeckHeaterExists\":false,\"hasRingHeaterExists\":false},\"dose\":{\"doseIndex\":\"DoseC\",\"doseType\":\"PulsesType\",\"stopTarget\":550},\"doseMode\":{\"brewingType\":\"PulsesType\"}},\"waterProperties\":{\"conductivity\":297,\"hardness\":137},\"flushInfo\":{\"abrTarget\":0,\"abrCoffeeMass\":17,\"abrPortafilterMass\":568.5,\"doseIndex\":\"DoseC\",\"mass\":0,\"time\":4.5,\"volume\":186}}"
    },
    {
        "name": "ABRCoffeeMassGroup1",
        "recorded": "2024-06-14T17:43:17Z",
        "value": "17.000000"
    },
    {
        "name": "SettingPreinfusionGroup1Mode",
        "recorded": "2024-06-14T17:43:17Z",
        "value": "{\"groupNumber\":\"Group1\",\"preinfusionStyle\":\"None\"}"
    },
    {
        "name": "TeaStartedStoptype",
        "recorded": "2024-07-12T14:52:46Z",
        "value": "StopByTime"
    },
    {
        "name": "ABRPortafilterMassGroup2",
        "recorded": "2024-06-14T17:43:17Z",
        "value": "568.500000"
    },
    {
        "name": "Group1DoseSettings",
        "recorded": "2024-07-13T23:23:16Z",
        "value": "{\"groupMode\":\"Pulses\",\"dose\":{\"button\":\"DoseC\",\"targetPulses\":\"number\"}}"
    },
    {
        "name": "MachineConfiguration",
        "recorded": "2024-07-14T08:11:02Z",
        "value": "{\"subFamily\":\"AV\",\"machineCapabilities\":[{\"family\":\"GB5\",\"groupsNumber\":2,\"coffeeBoilersNumber\":1,\"hasCupWarmer\":false,\"hasCupWarmerButton\":false,\"hasProportionalSteam\":false,\"hasLowLevelSensor\":true,\"hasBluetooth\":false,\"hasMixingValue\":false,\"coffeeBoilerSizeWatts\":1400,\"steamBoilerSizeWatts\":3000,\"cupWarmerHeaterSizeWatts\":150,\"machineVoltageVolts\":240,\"steamBoilersNumber\":1,\"teaDosesNumber\":1}],\"groupCapabilities\":[{\"capabilities\":{\"groupType\":\"AV_Group\",\"groupNumber\":\"Group1\",\"boilerId\":\"CoffeeBoiler1\",\"hasScale\":false,\"hasSolenoid\":true,\"hasStraightInPortafilter\":false,\"hasAutoCleanSolenoid\":false,\"hasFlowmeter\":true,\"hasNeckHeaterExists\":false,\"hasRingHeaterExists\":false,\"numberOfDoses\":4},\"doses\":[{\"groupNumber\":\"Group1\",\"doseIndex\":\"DoseA\",\"doseType\":\"PulsesType\",\"stopTarget\":95},{\"groupNumber\":\"Group1\",\"doseIndex\":\"DoseB\",\"doseType\":\"PulsesType\",\"stopTarget\":332},{\"groupNumber\":\"Group1\",\"doseIndex\":\"DoseC\",\"doseType\":\"PulsesType\",\"stopTarget\":551},{\"groupNumber\":\"Group1\",\"doseIndex\":\"DoseD\",\"doseType\":\"PulsesType\",\"stopTarget\":275}],\"doseMode\":{\"groupNumber\":\"Group1\",\"brewingType\":\"PulsesType\"}},{\"capabilities\":{\"groupType\":\"AV_Group\",\"groupNumber\":\"Group2\",\"boilerId\":\"CoffeeBoiler1\",\"hasScale\":false,\"hasSolenoid\":true,\"hasStraightInPortafilter\":false,\"hasAutoCleanSolenoid\":false,\"hasFlowmeter\":true,\"hasNeckHeaterExists\":false,\"hasRingHeaterExists\":false,\"numberOfDoses\":4},\"doses\":[{\"groupNumber\":\"Group2\",\"doseIndex\":\"DoseA\",\"doseType\":\"PulsesType\",\"stopTarget\":95},{\"groupNumber\":\"Group2\",\"doseIndex\":\"DoseB\",\"doseType\":\"PulsesType\",\"stopTarget\":332},{\"groupNumber\":\"Group2\",\"doseIndex\":\"DoseC\",\"doseType\":\"PulsesType\",\"stopTarget\":550},{\"groupNumber\":\"Group2\",\"doseIndex\":\"DoseD\",\"doseType\":\"PulsesType\",\"stopTarget\":275}],\"doseMode\":{\"groupNumber\":\"Group2\",\"brewingType\":\"PulsesType\"}}],\"boardDescriptor\":[{\"boardType\":\"GB5ButtonBoard\",\"hardwareMajor\":3,\"hardwareMinor\":255,\"firmwareMajor\":255,\"firmwareMinor\":255,\"firmwareBugFix\":255},{\"boardType\":\"UniversalBoard24V\",\"hardwareMajor\":0,\"hardwareMinor\":3,\"firmwareMajor\":0,\"firmwareMinor\":19,\"firmwareBugFix\":0},{\"boardType\":\"CDRWaterProbePosition2\",\"hardwareMajor\":1,\"hardwareMinor\":255,\"firmwareMajor\":1,\"firmwareMinor\":24,\"firmwareBugFix\":0},{\"boardType\":\"Cortex5Board\",\"hardwareMajor\":5,\"hardwareMinor\":255,\"firmwareMajor\":1,\"firmwareMinor\":2,\"firmwareBugFix\":0}],\"serialNumber\":[{\"value\":\"GN000126\"}],\"machineFirmwareVersion\":[{\"firmwareMajor\":1,\"firmwareMinor\":2,\"firmwareBugFix\":0,\"preRelease\":\"\"}],\"numberOfSettings\":249,\"machineMode\":\"StandBy\",\"cupwarmerEnabled\":false,\"teaDoses\":{\"DoseB\":{\"doseIndex\":\"DoseB\",\"stopTarget\":6}},\"teaDosesEnabled\":true,\"autoOnOffConfig\":{\"onTimeHours\":7,\"onTimeMinutes\":15,\"offTimeHours\":16,\"offTimeMinutes\":0,\"closedDay\":0},\"autoOnOffEnabled\":true,\"abrCoffeeMass\":{\"Group1\":17,\"Group2\":17},\"abrPortafilterMass\":{\"Group1\":568.5,\"Group2\":568.5},\"avModeBrewingPressure\":{},\"boilerTargetTemperature\":{\"CoffeeBoiler1\":93.8,\"SteamBoiler\":122},\"preinfusionModesAvailable\":[\"ByGroup\",\"ByDoseType\"],\"preinfusionMode\":{\"Group1\":{\"groupNumber\":\"Group1\",\"preinfusionStyle\":\"None\"},\"Group2\":{\"groupNumber\":\"Group2\",\"preinfusionStyle\":\"None\"}},\"preinfusionSettings\":{},\"isLoaded\":true}"
    },
    {
        "name": "SteamBoilerAutoFillTime",
        "recorded": "2024-07-12T21:22:21Z",
        "value": "2.700000"
    },
    {
        "name": "SettingAutoOnOffEnabled",
        "recorded": "2024-06-14T17:43:17Z",
        "value": "true"
    },
    {
        "name": "BrewingStoppedGroup1StopReason",
        "recorded": "2024-07-12T15:06:32Z",
        "value": "Automatic"
    },
    {
        "name": "BrewingUpdateGroup1IsSolenoidOpen",
        "recorded": "2024-07-12T15:09:12Z",
        "value": "false"
    },
    {
        "name": "HotWaterStopTime",
        "recorded": "2024-07-12T14:52:46Z",
        "value": "0.290000"
    },
    {
        "name": "CoffeeBoiler1UpdateSetPoint",
        "recorded": "2024-07-04T11:17:22Z",
        "value": "93.800000"
    },
    {
        "name": "BrewingUpdateGroup2IsSolenoidOpen",
        "recorded": "2024-07-12T14:52:36Z",
        "value": "false"
    },
    {
        "name": "BrewingStartedGroup1VolumeTarget",
        "recorded": "2024-07-12T15:09:06Z",
        "value": "550.000000"
    },
    {
        "name": "SteamBoilerSettingTargetSetPoint",
        "recorded": "2023-06-14T15:12:02Z",
        "value": "124.000000"
    },
    {
        "name": "TotalEnergyConsumption",
        "recorded": "2024-07-14T07:45:48Z",
        "value": "0.000000"
    },
    {
        "name": "CoffeeBoiler1UpdateTemperature",
        "recorded": "2024-07-14T08:11:02Z",
        "value": "0.000000"
    },
    {
        "name": "BrewingUpdateGroup1Time",
        "recorded": "2024-07-12T15:09:12Z",
        "value": "3.700000"
    },
    {
        "name": "SteamBoilerAutoFillStopType",
        "recorded": "2024-07-12T21:22:21Z",
        "value": "byBrewingStarting"
    },
    {
        "name": "FlushStoppedGroup1FlowRate",
        "recorded": "2024-07-12T15:09:13Z",
        "value": "0.000000"
    },
    {
        "name": "SettingAutoOnOffConfig",
        "recorded": "2024-06-14T17:43:17Z",
        "value": "{\"onTimeHours\":7,\"onTimeMinutes\":15,\"offTimeHours\":16,\"offTimeMinutes\":0,\"closedDay\":0}"
    },
    {
        "name": "SteamBoilerSettingEnableState",
        "recorded": "2023-06-14T15:12:02Z",
        "value": "BoilerEnabled"
    },
    {
        "name": "BrewingUpdateGroup1FlowRate",
        "recorded": "2024-07-12T15:09:12Z",
        "value": "0.000000"
    },
    {
        "name": "BrewingStoppedGroup2Time",
        "recorded": "2024-07-12T14:51:35Z",
        "value": "16.000000"
    },
    {
        "name": "BrewingStoppedGroup1StopType",
        "recorded": "2024-07-12T15:06:32Z",
        "value": "Volumetric"
    },
    {
        "name": "ABRCoffeeMassGroup2",
        "recorded": "2024-06-14T17:43:17Z",
        "value": "17.000000"
    },
    {
        "name": "BrewingStoppedGroup1Time",
        "recorded": "2024-07-12T15:06:32Z",
        "value": "15.600000"
    },
    {
        "name": "WaterTDS",
        "recorded": "2024-07-12T15:09:13Z",
        "value": "193.280000"
    },
    {
        "name": "BrewingStoppedGroup2DoseIndex",
        "recorded": "2024-07-12T14:51:35Z",
        "value": "DoseC"
    },
    {
        "name": "CupwarmerStatus",
        "recorded": "2024-06-14T17:43:17Z",
        "value": "false"
    },
    {
        "name": "TeaDoseSettings",
        "recorded": "2024-06-14T17:43:17Z",
        "value": "{\"doseIndex\":\"DoseB\",\"stopTarget\":6}"
    },
    {
        "name": "BrewingUpdateGroup1InPostBrew",
        "recorded": "2024-07-12T15:09:12Z",
        "value": "true"
    },
    {
        "name": "FlushStoppedGroup1Volume",
        "recorded": "2024-07-12T15:09:13Z",
        "value": "140.000000"
    },
    {
        "name": "SystemInfo",
        "recorded": "2024-07-14T08:09:48Z",
        "value": "{\"network_interfaces\":[{\"name\":\"wlan0\",\"address\":\"10.10.10.2\"},{\"name\":\"docker0\",\"address\":\"172.17.0.1\"}],\"memory_info\":{\"available\":\"8.3M\",\"used\":\"481M\",\"total\":\"490M\"},\"filesystem\":{\"dir\":\"/usr/bin\",\"available\":\"560M\",\"used\":\"628M\",\"total\":\"1.2G\"},\"uptime\":\"1 day, 17:24\",\"os_version\":\"20231102114141\",\"mac_addr\":{\"eth0\":\"xxx\",\"wlan\":\"xxx\",\"bluetooth\":\"xxx\"}}"
    },
    {
        "name": "HotWaterButtonUsed",
        "recorded": "2024-07-12T14:52:46Z",
        "value": "LongPressTeaDose"
    },
    {
        "name": "BrewingUpdateGroup2Volume",
        "recorded": "2024-07-12T14:52:36Z",
        "value": "186.000000"
    },
    {
        "name": "BrewingStoppedGroup2Volume",
        "recorded": "2024-07-12T14:51:35Z",
        "value": "561.000000"
    },
    {
        "name": "BrewingStoppedGroup2TimeTarget",
        "recorded": "2024-07-03T20:35:25Z",
        "value": "120.000000"
    },
    {
        "name": "BrewingStoppedGroup1TimeTarget",
        "recorded": "2024-07-04T07:47:19Z",
        "value": "120.000000"
    },
    {
        "name": "UserInitiatedEventType",
        "recorded": "2024-07-12T14:48:20Z",
        "value": "G2CleaningCyclePerformed"
    },
    {
        "name": "FlushStoppedGroup1DoseIndex",
        "recorded": "2024-07-12T15:09:13Z",
        "value": "DoseC"
    },
    {
        "name": "BrewingStoppedGroup1Volume",
        "recorded": "2024-07-12T15:06:32Z",
        "value": "561.000000"
    },
    {
        "name": "FlushStoppedGroup1Time",
        "recorded": "2024-07-12T15:09:13Z",
        "value": "3.700000"
    },
    {
        "name": "SteamBoilerEnabled",
        "recorded": "2024-06-14T17:43:17Z",
        "value": "true"
    },
    {
        "name": "BrewingSnapshotGroup2",
        "recorded": "2024-07-12T14:51:35Z",
        "value": "{\"groupConfiguration\":{\"groupNumber\":\"Group2\",\"capabilities\":{\"groupType\":\"AV_Group\",\"boilerId\":\"CoffeeBoiler1\",\"boilerTemperature\":93.8,\"hasScale\":false,\"hasSolenoid\":true,\"hasStraightInPortafilter\":false,\"hasAutoCleanSolenoid\":false,\"hasFlowmeter\":true,\"hasNeckHeaterExists\":false,\"hasRingHeaterExists\":false},\"dose\":{\"doseIndex\":\"DoseC\",\"doseType\":\"PulsesType\",\"stopTarget\":550},\"doseMode\":{\"brewingType\":\"PulsesType\"}},\"waterProperties\":{\"conductivity\":311,\"hardness\":144},\"brewingInfo\":{\"abrTarget\":0,\"abrCoffeeMass\":17,\"abrPortafilterMass\":568.5,\"doseIndex\":\"DoseC\",\"mass\":0,\"stopReason\":\"Automatic\",\"stopType\":\"Volumetric\",\"time\":16,\"volume\":561}}"
    },
    {
        "name": "BrewingStoppedGroup1VolumeTarget",
        "recorded": "2024-07-12T15:06:32Z",
        "value": "550.000000"
    },
    {
        "name": "ABRPortafilterMassGroup1",
        "recorded": "2024-06-14T17:43:17Z",
        "value": "568.500000"
    },
    {
        "name": "SettingPreinfusionGroup2Mode",
        "recorded": "2024-06-14T17:43:17Z",
        "value": "{\"groupNumber\":\"Group2\",\"preinfusionStyle\":\"None\"}"
    },
    {
        "name": "BrewingStartedGroup2StopType",
        "recorded": "2024-07-12T14:52:29Z",
        "value": "Volumetric"
    },
    {
        "name": "BrewingUpdateGroup2InPostBrew",
        "recorded": "2024-07-12T14:52:36Z",
        "value": "true"
    },
    {
        "name": "BrewingStartedGroup1TimeTarget",
        "recorded": "2024-07-04T07:46:56Z",
        "value": "120.000000"
    },
    {
        "name": "BrewingSnapshotGroup1",
        "recorded": "2024-07-12T15:06:32Z",
        "value": "{\"groupConfiguration\":{\"groupNumber\":\"Group1\",\"capabilities\":{\"groupType\":\"AV_Group\",\"boilerId\":\"CoffeeBoiler1\",\"boilerTemperature\":90.41,\"hasScale\":false,\"hasSolenoid\":true,\"hasStraightInPortafilter\":false,\"hasAutoCleanSolenoid\":false,\"hasFlowmeter\":true,\"hasNeckHeaterExists\":false,\"hasRingHeaterExists\":false},\"dose\":{\"doseIndex\":\"DoseC\",\"doseType\":\"PulsesType\",\"stopTarget\":550},\"doseMode\":{\"brewingType\":\"PulsesType\"}},\"waterProperties\":{\"conductivity\":285,\"hardness\":131},\"brewingInfo\":{\"abrTarget\":0,\"abrCoffeeMass\":17,\"abrPortafilterMass\":568.5,\"doseIndex\":\"DoseC\",\"mass\":0,\"stopReason\":\"Automatic\",\"stopType\":\"Volumetric\",\"time\":15.6,\"volume\":561}}"
    },
    {
        "name": "SteamBoilerAutoFillInProgress",
        "recorded": "2024-07-12T21:22:18Z",
        "value": "true"
    },
    {
        "name": "TeaStartedStopTarget",
        "recorded": "2024-07-12T14:52:46Z",
        "value": "6"
    },
    {
        "name": "BrewingStartedGroup2VolumeTarget",
        "recorded": "2024-07-12T14:52:29Z",
        "value": "550.000000"
    },
    {
        "name": "BrewingStoppedGroup2TimeSinceStart",
        "recorded": "2024-07-12T14:51:35Z",
        "value": "19.000000"
    },
    {
        "name": "WaterConductivity",
        "recorded": "2024-07-12T15:09:13Z",
        "value": "302.000000"
    },
    {
        "name": "Group2DoseSettings",
        "recorded": "2024-07-04T07:55:52Z",
        "value": "{\"groupMode\":\"Pulses\",\"dose\":{\"button\":\"DoseD\",\"targetPulses\":\"number\"}}"
    },
    {
        "name": "BrewingStartedGroup1PreWetHoldTime",
        "recorded": "2024-05-14T11:18:37Z",
        "value": "1000.000000"
    },
    {
        "name": "Settings",
        "recorded": "2024-07-14T08:11:02Z",
        "value": "{\"Settings\":[{\"Hash\":24545312,\"Value\":\"AgAAAA==\"},{\"Hash\":42981347,\"Value\":\"AAAAAA==\"},{\"Hash\":110444511,\"Value\":\"AABwQg==\"},{\"Hash\":133744451,\"Value\":\"AQAAAA==\"},{\"Hash\":135806560,\"Value\":\"AADIQw==\"},{\"Hash\":146027975,\"Value\":\"AAAAAA==\"},{\"Hash\":159116807,\"Value\":\"AQAAAA==\"},{\"Hash\":197206951,\"Value\":\"AACIQQ==\"},{\"Hash\":242743250,\"Value\":\"AAAAAA==\"},{\"Hash\":255049536,\"Value\":\"AgAAAA==\"},{\"Hash\":275696402,\"Value\":\"AAAAAA==\"},{\"Hash\":319528944,\"Value\":\"PAAAAA==\"},{\"Hash\":325996636,\"Value\":\"AABwQg==\"},{\"Hash\":331848676,\"Value\":\"AAAAQA==\"},{\"Hash\":344977420,\"Value\":\"AAAAAA==\"},{\"Hash\":346033799,\"Value\":\"AACgQA==\"},{\"Hash\":346517689,\"Value\":\"AAAAAA==\"},{\"Hash\":353194907,\"Value\":\"AAAAAA==\"},{\"Hash\":354173276,\"Value\":\"AADwQQ==\"},{\"Hash\":359872125,\"Value\":\"AAAAAA==\"},{\"Hash\":382349916,\"Value\":\"AABIQg==\"},{\"Hash\":383563939,\"Value\":\"AABIRA==\"},{\"Hash\":388140904,\"Value\":\"AAAAAA==\"},{\"Hash\":410526556,\"Value\":\"AADIQQ==\"},{\"Hash\":423447656,\"Value\":\"AAAgQQ==\"},{\"Hash\":431124964,\"Value\":\"AAAAAA==\"},{\"Hash\":452226719,\"Value\":\"AMAJRA==\"},{\"Hash\":463983154,\"Value\":\"AAAAAA==\"},{\"Hash\":490160801,\"Value\":\"AAAAAA==\"},{\"Hash\":502333892,\"Value\":\"AAAAAA==\"},{\"Hash\":508581482,\"Value\":\"AACIQQ==\"},{\"Hash\":585742189,\"Value\":\"AAAAAA==\"},{\"Hash\":591460521,\"Value\":\"AQAAAA==\"},{\"Hash\":620716005,\"Value\":\"AAAAAA==\"},{\"Hash\":626078681,\"Value\":\"AADIQQ==\"},{\"Hash\":632277994,\"Value\":\"AAC9Qg==\"},{\"Hash\":637537139,\"Value\":\"AgAAAA==\"},{\"Hash\":643583762,\"Value\":\"AAAAQA==\"},{\"Hash\":649165042,\"Value\":\"AABgQA==\"},{\"Hash\":684455938,\"Value\":\"AACAPw==\"},{\"Hash\":696674017,\"Value\":\"MTIzMzIx\"},{\"Hash\":713143409,\"Value\":\"AAAAQA==\"},{\"Hash\":715025200,\"Value\":\"AAAAAA==\"},{\"Hash\":755396448,\"Value\":\"AABIQw==\"},{\"Hash\":761735343,\"Value\":\"AAAAQA==\"},{\"Hash\":779028130,\"Value\":\"AAAAAA==\"},{\"Hash\":795196741,\"Value\":\"AAAgQQ==\"},{\"Hash\":799289048,\"Value\":\"AQAAAA==\"},{\"Hash\":800486879,\"Value\":\"AAD0Qg==\"},{\"Hash\":804649232,\"Value\":\"AAAAQA==\"},{\"Hash\":819714240,\"Value\":\"AACAQA==\"},{\"Hash\":885897902,\"Value\":\"AAAAAA==\"},{\"Hash\":890767579,\"Value\":\"AAAgQQ==\"},{\"Hash\":909583334,\"Value\":\"AAAAAA==\"},{\"Hash\":923941606,\"Value\":\"AQAAAA==\"},{\"Hash\":925980204,\"Value\":\"AQAAAA==\"},{\"Hash\":999945238,\"Value\":\"AAAAAA==\"},{\"Hash\":1011853904,\"Value\":\"AQAAAA==\"},{\"Hash\":1055187810,\"Value\":\"AADAPw==\"},{\"Hash\":1067895459,\"Value\":\"AAAAAA==\"},{\"Hash\":1071816607,\"Value\":\"AACmQw==\"},{\"Hash\":1131189375,\"Value\":\"AAAAAA==\"},{\"Hash\":1148278678,\"Value\":\"AAAAAA==\"},{\"Hash\":1172484317,\"Value\":\"AACgQg==\"},{\"Hash\":1232437844,\"Value\":\"R04wMDAxMjY=\"},{\"Hash\":1249749884,\"Value\":\"AgAAAA==\"},{\"Hash\":1289204954,\"Value\":\"AAAAAA==\"},{\"Hash\":1295882172,\"Value\":\"AAAAAA==\"},{\"Hash\":1300089973,\"Value\":\"AAAAQA==\"},{\"Hash\":1319573986,\"Value\":\"AABIRA==\"},{\"Hash\":1349626584,\"Value\":\"XjwBAA==\"},{\"Hash\":1353748332,\"Value\":\"AAAAAA==\"},{\"Hash\":1356762788,\"Value\":\"AAAAAA==\"},{\"Hash\":1358235859,\"Value\":\"AACAQA==\"},{\"Hash\":1369908189,\"Value\":\"AAAAAA==\"},{\"Hash\":1408341271,\"Value\":\"AABwQQ==\"},{\"Hash\":1408341304,\"Value\":\"AADHQA==\"},{\"Hash\":1408341337,\"Value\":\"AABwQQ==\"},{\"Hash\":1408341370,\"Value\":\"AABwQQ==\"},{\"Hash\":1408365318,\"Value\":\"AACWQw==\"},{\"Hash\":1411847667,\"Value\":\"AABAQA==\"},{\"Hash\":1439968275,\"Value\":\"AABgQA==\"},{\"Hash\":1455589644,\"Value\":\"AAAAAA==\"},{\"Hash\":1480402973,\"Value\":\"AQAAAA==\"},{\"Hash\":1484069242,\"Value\":\"AAAAAA==\"},{\"Hash\":1502125449,\"Value\":\"npm7Qg==\"},{\"Hash\":1582990864,\"Value\":\"AAAAQA==\"},{\"Hash\":1588469295,\"Value\":\"AAAAAA==\"},{\"Hash\":1591219347,\"Value\":\"AADIQg==\"},{\"Hash\":1603128778,\"Value\":\"LQAAAA==\"},{\"Hash\":1618697882,\"Value\":\"AAAAAA==\"},{\"Hash\":1625904753,\"Value\":\"AAAAQA==\"},{\"Hash\":1632218463,\"Value\":\"ACAORA==\"},{\"Hash\":1636117716,\"Value\":\"AAAAAA==\"},{\"Hash\":1640394998,\"Value\":\"DwAAAA==\"},{\"Hash\":1641645660,\"Value\":\"AAAgQQ==\"},{\"Hash\":1646317035,\"Value\":\"BgAAAA==\"},{\"Hash\":1671334243,\"Value\":\"AQAAAA==\"},{\"Hash\":1674496687,\"Value\":\"AAAAQA==\"},{\"Hash\":1685801693,\"Value\":\"AABwQg==\"},{\"Hash\":1691406495,\"Value\":\"AABIQw==\"},{\"Hash\":1698505742,\"Value\":\"AAAAAA==\"},{\"Hash\":1713978333,\"Value\":\"AADwQQ==\"},{\"Hash\":1714972457,\"Value\":\"TEFNQVJaT0NDTw==\"},{\"Hash\":1726781407,\"Value\":\"AAAgQQ==\"},{\"Hash\":1726781412,\"Value\":\"CtcjPQ==\"},{\"Hash\":1726781419,\"Value\":\"MzNzQA==\"},{\"Hash\":1729680405,\"Value\":\"AAAAAA==\"},{\"Hash\":1742154973,\"Value\":\"AABIQg==\"},{\"Hash\":1802572816,\"Value\":\"AAAAAA==\"},{\"Hash\":1815299225,\"Value\":\"AAAAAA==\"},{\"Hash\":1817087643,\"Value\":\"AAAAAA==\"},{\"Hash\":1826777626,\"Value\":\"AAAAAA==\"},{\"Hash\":1833454844,\"Value\":\"AABAQA==\"},{\"Hash\":1836445737,\"Value\":\"AACIQQ==\"},{\"Hash\":1868201597,\"Value\":\"AAAAAA==\"},{\"Hash\":1878118198,\"Value\":\"AAAAAA==\"},{\"Hash\":1893491796,\"Value\":\"AAAAAA==\"},{\"Hash\":1897611647,\"Value\":\"MTIzMTIz\"},{\"Hash\":1932757822,\"Value\":\"ACAORA==\"},{\"Hash\":1939163874,\"Value\":\"AADIQw==\"},{\"Hash\":1957023130,\"Value\":\"AAAAAA==\"},{\"Hash\":1957707098,\"Value\":\"AADwQQ==\"},{\"Hash\":1966875268,\"Value\":\"AACgQA==\"},{\"Hash\":1968930652,\"Value\":\"AADIQQ==\"},{\"Hash\":1985883738,\"Value\":\"AADIQQ==\"},{\"Hash\":1991818502,\"Value\":\"DwAAAA==\"},{\"Hash\":2007826654,\"Value\":\"AACmQw==\"},{\"Hash\":2024824507,\"Value\":\"AAAAAA==\"},{\"Hash\":2092625884,\"Value\":\"AAAAAA==\"},{\"Hash\":2104686124,\"Value\":\"AAAAAA==\"},{\"Hash\":2109935039,\"Value\":\"AQAAAA==\"},{\"Hash\":2124474294,\"Value\":\"AAAAAA==\"},{\"Hash\":2160427261,\"Value\":\"AAAAAA==\"},{\"Hash\":2167488394,\"Value\":\"AABAQA==\"},{\"Hash\":2177736416,\"Value\":\"AQAAAA==\"},{\"Hash\":2199431580,\"Value\":\"AAAAAA==\"},{\"Hash\":2231892219,\"Value\":\"AAAAAA==\"},{\"Hash\":2233297181,\"Value\":\"ACAORA==\"},{\"Hash\":2245537793,\"Value\":\"AQAAAA==\"},{\"Hash\":2255584033,\"Value\":\"AICJQw==\"},{\"Hash\":2255742597,\"Value\":\"AAAAQA==\"},{\"Hash\":2313339170,\"Value\":\"AQAAAA==\"},{\"Hash\":2325437099,\"Value\":\"AAAAAA==\"},{\"Hash\":2327985812,\"Value\":\"AAAgQg==\"},{\"Hash\":2380756235,\"Value\":\"TscAAA==\"},{\"Hash\":2414054722,\"Value\":\"AAAAAA==\"},{\"Hash\":2421628222,\"Value\":\"DAAAAA==\"},{\"Hash\":2447160274,\"Value\":\"AAAAQA==\"},{\"Hash\":2455717520,\"Value\":\"EAAAAA==\"},{\"Hash\":2495752208,\"Value\":\"AAAAQA==\"},{\"Hash\":2505716910,\"Value\":\"AQAAAA==\"},{\"Hash\":2530661563,\"Value\":\"x7UAAA==\"},{\"Hash\":2533836540,\"Value\":\"ACAORA==\"},{\"Hash\":2544344142,\"Value\":\"AAAAQA==\"},{\"Hash\":2544609926,\"Value\":\"AAAAAA==\"},{\"Hash\":2553866996,\"Value\":\"AAAAAA==\"},{\"Hash\":2582534096,\"Value\":\"AAAAAA==\"},{\"Hash\":2627416542,\"Value\":\"AAC+Qg==\"},{\"Hash\":2641775086,\"Value\":\"AQAAAA==\"},{\"Hash\":2659754560,\"Value\":\"ZmbmPw==\"},{\"Hash\":2659754565,\"Value\":\"mbsWOw==\"},{\"Hash\":2659754572,\"Value\":\"exQuPg==\"},{\"Hash\":2665690452,\"Value\":\"AAAAAA==\"},{\"Hash\":2691064129,\"Value\":\"AAAAAA==\"},{\"Hash\":2700655607,\"Value\":\"AAAAAA==\"},{\"Hash\":2702922051,\"Value\":\"AAAAQA==\"},{\"Hash\":2758335117,\"Value\":\"AAAAQA==\"},{\"Hash\":2762787673,\"Value\":\"AAAAAA==\"},{\"Hash\":2769464891,\"Value\":\"AABAQA==\"},{\"Hash\":2776142109,\"Value\":\"AAAAAA==\"},{\"Hash\":2781497983,\"Value\":\"BQAAAA==\"},{\"Hash\":2833477255,\"Value\":\"AAAAAA==\"},{\"Hash\":2861891546,\"Value\":\"l4YAAA==\"},{\"Hash\":2875173921,\"Value\":\"AADIQw==\"},{\"Hash\":2913333685,\"Value\":\"AACAPw==\"},{\"Hash\":2991789380,\"Value\":\"AAAAAA==\"},{\"Hash\":2995275019,\"Value\":\"AADwQg==\"},{\"Hash\":3004455346,\"Value\":\"AQAAAA==\"},{\"Hash\":3045606750,\"Value\":\"AABwQg==\"},{\"Hash\":3060484341,\"Value\":\"AAAAAA==\"},{\"Hash\":3073783390,\"Value\":\"AADwQQ==\"},{\"Hash\":3082324756,\"Value\":\"AAAAAA==\"},{\"Hash\":3095269212,\"Value\":\"AECcRQ==\"},{\"Hash\":3138891010,\"Value\":\"AAAAAA==\"},{\"Hash\":3154701486,\"Value\":\"AAAAAA==\"},{\"Hash\":3164309992,\"Value\":\"AACIQQ==\"},{\"Hash\":3178777905,\"Value\":\"AAAAAA==\"},{\"Hash\":3187550380,\"Value\":\"AAC9Qg==\"},{\"Hash\":3191594080,\"Value\":\"AICJQw==\"},{\"Hash\":3192825007,\"Value\":\"AAAAAA==\"},{\"Hash\":3195284554,\"Value\":\"AAAAAA==\"},{\"Hash\":3202025008,\"Value\":\"AAAgQQ==\"},{\"Hash\":3243062258,\"Value\":\"AABAQA==\"},{\"Hash\":3268415795,\"Value\":\"AAAAQA==\"},{\"Hash\":3280656709,\"Value\":\"AAAAAA==\"},{\"Hash\":3289335515,\"Value\":\"AADwQQ==\"},{\"Hash\":3293802110,\"Value\":\"AAAAAA==\"},{\"Hash\":3316932914,\"Value\":\"BwAAAA==\"},{\"Hash\":3317007729,\"Value\":\"AAAAQA==\"},{\"Hash\":3317512155,\"Value\":\"AADwQQ==\"},{\"Hash\":3345688795,\"Value\":\"AADIQQ==\"},{\"Hash\":3362525872,\"Value\":\"BgAAQA==\"},{\"Hash\":3365599663,\"Value\":\"AAAAQA==\"},{\"Hash\":3366819611,\"Value\":\"AADIQg==\"},{\"Hash\":3397569308,\"Value\":\"AQAAAA==\"},{\"Hash\":3412821028,\"Value\":\"AQAAAA==\"},{\"Hash\":3414191597,\"Value\":\"AAAAQA==\"},{\"Hash\":3434221942,\"Value\":\"GAAAAA==\"},{\"Hash\":3451377328,\"Value\":\"AAAAAA==\"},{\"Hash\":3483224513,\"Value\":\"AQAAAA==\"},{\"Hash\":3488224333,\"Value\":\"AAAgQQ==\"},{\"Hash\":3488224338,\"Value\":\"CtcjPQ==\"},{\"Hash\":3488224345,\"Value\":\"MzNzQA==\"},{\"Hash\":3494763809,\"Value\":\"AADIQw==\"},{\"Hash\":3511874002,\"Value\":\"AAAAAA==\"},{\"Hash\":3563426589,\"Value\":\"AAC+Qg==\"},{\"Hash\":3576598897,\"Value\":\"AAAAAA==\"},{\"Hash\":3594202165,\"Value\":\"AAAAAA==\"},{\"Hash\":3601700499,\"Value\":\"AAAAAA==\"},{\"Hash\":3667875604,\"Value\":\"AAAAAA==\"},{\"Hash\":3692516554,\"Value\":\"AQAAAA==\"},{\"Hash\":3698797720,\"Value\":\"AAAAAA==\"},{\"Hash\":3705474938,\"Value\":\"AABAQA==\"},{\"Hash\":3712152156,\"Value\":\"AAAAAA==\"},{\"Hash\":3718180909,\"Value\":\"AAAAAA==\"},{\"Hash\":3718829374,\"Value\":\"AAAAAA==\"},{\"Hash\":3740981564,\"Value\":\"AAAAAA==\"},{\"Hash\":3741567921,\"Value\":\"PAAAAA==\"},{\"Hash\":3801571303,\"Value\":\"AAAAAA==\"},{\"Hash\":3811183968,\"Value\":\"AIAJRA==\"},{\"Hash\":3891289897,\"Value\":\"AACgQA==\"},{\"Hash\":3938656658,\"Value\":\"AQAAAA==\"},{\"Hash\":3955521327,\"Value\":\"AAAAAA==\"},{\"Hash\":3986367088,\"Value\":\"AAAAAA==\"},{\"Hash\":3996494388,\"Value\":\"AgAAAA==\"},{\"Hash\":4036284638,\"Value\":\"AACgQg==\"},{\"Hash\":4045153960,\"Value\":\"AACgQA==\"},{\"Hash\":4057397835,\"Value\":\"AAC9Qg==\"},{\"Hash\":4085214377,\"Value\":\"AAAAAA==\"},{\"Hash\":4101581028,\"Value\":\"AAAAQA==\"},{\"Hash\":4102332411,\"Value\":\"AAAgQQ==\"},{\"Hash\":4108397092,\"Value\":\"BQAAAA==\"},{\"Hash\":4113293475,\"Value\":\"AAAAAA==\"},{\"Hash\":4138263250,\"Value\":\"AAAAQA==\"},{\"Hash\":4139278997,\"Value\":\"AQAAAA==\"},{\"Hash\":4153329105,\"Value\":\"AABgQA==\"},{\"Hash\":4186855184,\"Value\":\"AAAAQA==\"},{\"Hash\":4235447118,\"Value\":\"AAAAQA==\"}]}"
    },
    {
        "name": "TeaStartedDoseIndex",
        "recorded": "2024-07-12T14:52:46Z",
        "value": "DoseB"
    },
    {
        "name": "BrewingStartedGroup1PreWetWetTime",
        "recorded": "2024-05-14T11:18:37Z",
        "value": "500.000000"
    },
    {
        "name": "FlushStoppedGroup2Time",
        "recorded": "2024-07-12T14:52:43Z",
        "value": "4.500000"
    },
    {
        "name": "BrewingUpdateGroup2FlowRate",
        "recorded": "2024-07-12T14:52:36Z",
        "value": "0.000000"
    },
    {
        "name": "SteamBoilerUpdateTemperature",
        "recorded": "2024-07-14T08:11:01Z",
        "value": "0.000000"
    },
    {
        "name": "BrewingStartedGroup1StopType",
        "recorded": "2024-07-12T15:09:06Z",
        "value": "Volumetric"
    },
    {
        "name": "BrewingStoppedGroup2VolumeTarget",
        "recorded": "2024-07-12T14:51:35Z",
        "value": "550.000000"
    },
    {
        "name": "BrewingStoppedGroup2StopType",
        "recorded": "2024-07-12T14:51:35Z",
        "value": "Volumetric"
    },
    {
        "name": "CoffeeBoiler1SettingTargetSetPoint",
        "recorded": "2023-07-06T07:38:46Z",
        "value": "96.500000"
    },
    {
        "name": "HotWaterInProgress",
        "recorded": "2024-07-12T14:52:46Z",
        "value": "true"
    },
    {
        "name": "SettingPreinfusionGroup1",
        "recorded": "2024-01-29T10:44:34Z",
        "value": "[{\"groupNumber\":\"Group1\",\"doseType\":\"ByGroup\",\"isPreWetTimeActive\":false,\"preWetTime\":0,\"isPreWetHoldTimeActive\":false,\"preWetHoldTime\":0},{\"groupNumber\":\"Group1\",\"doseType\":\"DoseA\",\"isPreWetTimeActive\":false,\"preWetTime\":0,\"isPreWetHoldTimeActive\":false,\"preWetHoldTime\":0},{\"groupNumber\":\"Group1\",\"doseType\":\"DoseB\",\"isPreWetTimeActive\":false,\"preWetTime\":0,\"isPreWetHoldTimeActive\":false,\"preWetHoldTime\":0},{\"groupNumber\":\"Group1\",\"doseType\":\"DoseC\",\"isPreWetTimeActive\":false,\"preWetTime\":0,\"isPreWetHoldTimeActive\":false,\"preWetHoldTime\":0},{\"groupNumber\":\"Group1\",\"doseType\":\"DoseD\",\"isPreWetTimeActive\":true,\"preWetTime\":5,\"isPreWetHoldTimeActive\":true,\"preWetHoldTime\":10}]"
    },
    {
        "name": "BrewingStartedGroup2DoseIndex",
        "recorded": "2024-07-12T14:52:29Z",
        "value": "DoseC"
    },
    {
        "name": "BrewingStartedGroup1DoseIndex",
        "recorded": "2024-07-12T15:09:06Z",
        "value": "DoseC"
    },
    {
        "name": "BrewingStoppedGroup1TimeSinceStart",
        "recorded": "2024-07-12T15:06:32Z",
        "value": "18.500000"
    },
    {
        "name": "CoffeeBoiler1SettingEnableState",
        "recorded": "2023-06-14T15:12:02Z",
        "value": "BoilerEnabled"
    },
    {
        "name": "FlushStoppedGroup2DoseIndex",
        "recorded": "2024-07-12T14:52:43Z",
        "value": "DoseC"
    },
    {
        "name": "BrewingStoppedGroup1DoseIndex",
        "recorded": "2024-07-12T15:06:32Z",
        "value": "DoseC"
    },
    {
        "name": "BrewingUpdateGroup2Time",
        "recorded": "2024-07-12T14:52:36Z",
        "value": "4.500000"
    },
    {
        "name": "WaterHardness",
        "recorded": "2024-07-12T15:09:13Z",
        "value": "139.000000"
    },
    {
        "name": "SettingPreinfusionGroup2",
        "recorded": "2023-06-14T15:12:02Z",
        "value": "[{\"groupNumber\":\"Group2\",\"doseType\":\"ByGroup\",\"isPreWetTimeActive\":false,\"preWetTime\":0,\"isPreWetHoldTimeActive\":false,\"preWetHoldTime\":0}]"
    }
]
```


## Get config (local)

`GET https://{local-ip}:8081/config`
Authorization: Bearer {localtoken}

```json
{
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
                    "stopTarget": 551
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
            "value": "GN000126"
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
}
```