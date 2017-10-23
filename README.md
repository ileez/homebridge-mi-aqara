# homebridge-mi-aqara
[![npm version](https://badge.fury.io/js/homebridge-mi-aqara.svg)](https://badge.fury.io/js/homebridge-mi-aqara)

homebridge plugin for XiaoMi Aqara plugin.  
Thanks for [nfarina](https://github.com/nfarina)(the author of [homebridge](https://github.com/nfarina/homebridge)), [snOOrz](https://github.com/snOOrz)(the author of [homebridge-aqara](https://github.com/snOOrz/homebridge-aqara)), [licuhui](https://github.com/licuhui), [攀旺智能](https://pwzn.taobao.com/), [瀚思彼岸论坛](https://bbs.hassbian.com/), all other developer and testers.   

**Note: I have only a part of these devices, so some devices don't have tested. If you find bugs, please submit them to [issues](https://github.com/YinHangCode/homebridge-mi-aqara/issues) or [QQ Group: 107927710](//shang.qq.com/wpa/qunwpa?idkey=8b9566598f40dd68412065ada24184ef72c6bddaa11525ca26c4e1536a8f2a3d).**

This repository contains the Aqara plugin for homebridge.  
Aqara is a ZigBee gateway with a few sensors.  

![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/Gateway.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/ContactSensor.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/MotionSensor.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/Button.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/TemperatureAndHumiditySensor.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/SingleSwitch.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/DuplexSwitch.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/SingleSwitchLN.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/DuplexSwitchLN.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/SingleButton86.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/DuplexButton86.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/PlugBase.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/PlugBase86.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/MagicSquare.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/SmokeDetector.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/NatgasDetector.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/ElectricCurtain.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/ContactSensor2.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/MotionSensor2.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/Button2.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/TemperatureAndHumiditySensor2.jpg)
![](https://raw.githubusercontent.com/YinHangCode/homebridge-mi-aqara/master/images/WaterDetector.jpg)

## Supported Devices
1.Gateway(网关)   
2.ContactSensor(门磁感应)   
3.MotionSensor(人体感应)   
4.Button(按钮)   
5.TemperatureAndHumiditySensor(温度湿度传感器)   
6.SingleSwitch(单按钮墙壁开关)   
7.DuplexSwitch(双按钮墙壁开关)   
8.SingleSwitchLN(单按钮墙壁开关零火版)   
9.DuplexSwitchLN(双按钮墙壁开关零火版)   
10.SingleButton86(86型无线单按钮开关)   
11.DuplexButton86(86型无线双按钮开关)   
12.PlugBase(插座)   
13.PlugBase86(86型墙壁插座)   
14.MagicSquare(魔方)   
15.SmokeDetector(烟雾报警器)   
16.NatgasDetector(天然气报警器)   
17.ElectricCurtain(电动窗帘)   
18.ContactSensor2(门磁感应第二代)   
19.MotionSensor2(人体感应第二代)   
20.Button2(按钮第二代)   
21.TemperatureAndHumiditySensor2(温度湿度传感器第二代)   
22.WaterDetector(水浸传感器)   

## Pre-Requirements
1. Make sure you have V2 of the gateway. V1 has limited space so can't support this feature.  
2. Update gateway firmware to **1.4.1_150.0143** or later. You can contact [@babymoney666](https://github.com/babymoney666) if your firmware is not up to date.  

## Installation
1. Install HomeBridge, please follow it's [README](https://github.com/nfarina/homebridge/blob/master/README.md).  
If you are using Raspberry Pi, please read [Running-HomeBridge-on-a-Raspberry-Pi](https://github.com/nfarina/homebridge/wiki/Running-HomeBridge-on-a-Raspberry-Pi).  
2. Make sure you can see HomeBridge in your iOS devices, if not, please go back to step 1.  
3. Download homebridge-mi-aqara to your local folder.  

## Configuration
1. Open Aqara gateway's settings, enable [local network protocol](https://github.com/louisZL/lumi-gateway-local-api).  
Please follow the steps in this thread: http://bbs.xiaomi.cn/t-13198850. It's in Chinese so you might need a translator to read it.  
2. To control the devices, put gateway's MAC address (**lower case without colon**) and password (**keep original and case sensitive**) to ~/.homebridge/config.json.   
```
{
    "platforms": [{
        "platform": "MiAqaraPlatform",
        "gateways": {
            "6409802da3b3": "02i44k56zrgg578b"
        }
    }]
}
```
If you have more than one gateways, fill them in right order, like below.  
```
{
    "platforms": [{
        "platform": "MiAqaraPlatform",
        "gateways": {
            "6409802da3b3": "02i44k56zrgg578b",
            "f0b4299a5b2b": "2F92E7DA90C66B86",
            "f0b4299a77dd": "syu3oasva3uqd5qd"
        }
    }]
}
```
If you want to specify the default name of the device, add a mapping table to your config.json like this.   
For more information about default name, Please refer to file `sampleConfig.json`.   
```
{
    "platforms": [{
        "platform": "MiAqaraPlatform",
        "gateways": {
            "6409802da3b3": "02i44k56zrgg578b",
            "f0b4299a5b2b": "2F92E7DA90C66B86",
            "f0b4299a77dd": "syu3oasva3uqd5qd"
        },
        "defaultValue": {
            "158d0001000001": {
                "ContactSensor_ContactSensor": {
                    "name": "entrance door"
                }
            },
            "158d0001000002": {
                "MotionSensor2_MotionSensor": {
                    "name": "study room motion sensor"
                },
                "MotionSensor2_LightSensor": {
                    "name": "study room light sensor"
                }
            },
            "158d0001000004": {
                "TemperatureAndHumiditySensor_TemperatureSensor": {
                    "name": "living room temperature"
                },
                "TemperatureAndHumiditySensor_HumiditySensor": {
                    "name": "living room humidity"
                }
            }
        }
    }]
}
```
If you like to use Light Bulb type for Light Switch to make grandma Siri happy, like snOOrz, you can set the following in the config.   
Currently only supported: SingleSwitch, DuplexSwitch, SingleSwitchLN, DuplexSwitchLN.   
**If you changed serviceType config, Please [clear register accessories](#clear-register-accessories).**   
```
{
    "platforms": [{
        "platform": "MiAqaraPlatform",
        "gateways": {
            "6409802da3b3": "02i44k56zrgg578b",
            "f0b4299a5b2b": "2F92E7DA90C66B86",
            "f0b4299a77dd": "syu3oasva3uqd5qd"
        },
        "defaultValue": {
            "158d0001000007": {
                "SingleSwitch_Switch": {
                    "name": "living room light",
                    "serviceType": "Lightbulb"
                }
            },
            "158d0001000008": {
                "DuplexSwitch_Switch_Left": {
                    "name": "master bedroom room light",
                    "serviceType": "Lightbulb"
                },
                "DuplexSwitch_Switch_Right": {
                    "name": "study room light",
                    "serviceType": "Lightbulb"
                }
            }
        }
    }]
}
```
If you want to disable accessories, you can add disable attribute to config.   
```
{
    "platforms": [{
        "platform": "MiAqaraPlatform",
        "gateways": {
            "6409802da3b3": "02i44k56zrgg578b",
            "f0b4299a5b2b": "2F92E7DA90C66B86",
            "f0b4299a77dd": "syu3oasva3uqd5qd"
        },
        "defaultValue": {
            "158d0001000007": {
                "SingleSwitch_Switch": {
                    "name": "living room light",
                    "serviceType": "Lightbulb"
                }
            },
            "158d0001000008": {
                "DuplexSwitch_Switch_Left": {
                    "name": "master bedroom room light",
                    "serviceType": "Lightbulb",
                    "disable": false
                },
                "DuplexSwitch_Switch_Right": {
                    "name": "study room light",
                    "serviceType": "Lightbulb",
                    "disable": true
                }
            },
            "158d0001000004": {
                "TemperatureAndHumiditySensor_TemperatureSensor": {
                    "name": "living room temperature"
                },
                "TemperatureAndHumiditySensor_HumiditySensor": {
                    "name": "living room humidity",
                    "disable": true
                }
            },
            "158d0001000012": {
                "DuplexButton86_StatelessProgrammableSwitch_Left": {
                    "name": "dining room 86 button left"
                },
                "DuplexButton86_Switch_VirtualSinglePress_Left": {
                    "name": "dining room 86 button left virtual single press",
                    "disable": true
                },
                "DuplexButton86_StatelessProgrammableSwitch_Right": {
                    "name": "dining room 86 button right"
                },
                "DuplexButton86_Switch_VirtualSinglePress_Right": {
                    "name": "dining room 86 button right virtual single press",
                    "disable": true
                },
                "DuplexButton86_StatelessProgrammableSwitch_Both": {
                    "name": "dining room 86 button both"
                },
                "DuplexButton86_Switch_VirtualSinglePress_Both": {
                    "name": "dining room 86 button both virtual single press",
                    "disable": true
                }
            },
            "158d0001000015": {
                "MagicSquare_StatelessProgrammableSwitch_Flip90": {
                    "name": "study room magic square flip90",
                    "disable": true
                },
                "MagicSquare_Switch_VirtualFlip90": {
                    "name": "study room magic square virtual flip90"
                },
                "MagicSquare_StatelessProgrammableSwitch_Flip180": {
                    "name": "study room magic square flip180",
                    "disable": true
                },
                "MagicSquare_Switch_VirtualFlip180": {
                    "name": "study room magic square virtual flip180"
                },
                "MagicSquare_StatelessProgrammableSwitch_Move": {
                    "name": "study room magic square move",
                    "disable": true
                },
                "MagicSquare_Switch_VirtualMove": {
                    "name": "study room magic square virtual move"
                },
                "MagicSquare_StatelessProgrammableSwitch_TapTwice": {
                    "name": "study room magic square tapTwice",
                    "disable": true
                },
                "MagicSquare_Switch_VirtualTapTwice": {
                    "name": "study room magic square virtual tapTwice"
                },
                "MagicSquare_StatelessProgrammableSwitch_ShakeAir": {
                    "name": "study room magic square shakeAir",
                    "disable": true
                },
                "MagicSquare_Switch_VirtualShakeAir": {
                    "name": "study room magic square virtual shakeAir"
                },
                "MagicSquare_StatelessProgrammableSwitch_Rotate": {
                    "name": "study room magic square rotate",
                    "disable": true
                }
            }
        }
    }]
}
```
   
## Some explanation
Button/Button2 StatelessProgrammableSwitch support SinglePress, DoublePress, LongPress.   
SingleButton86/DuplexButton86(Left, Right, Both) StatelessProgrammableSwitch only support SinglePress.   
MagicSquare(Flip90, Flip180, Move, TapTwice, ShakeAir, Rotate) StatelessProgrammableSwitch only support SinglePress.   
    
## Run it
homebridge -D   
   
## Clear register accessories
cd ~/.homebridge/accessories/   
mv cachedAccessories cachedAccessories_\`date '+%Y%m%d_%H%M%S'\`.bak   
echo [] > cachedAccessories   

## Version Logs
### 0.6.2
1.fixed bug that MotionSensor motion sonser accessory status is error.   
2.fixed bug that MotionSensor2 motion sonser accessory status is error.   
### 0.6.1
1.fixed bug that MotionSensor2 light sonser accessory value is error.   
### 0.6.0
1.refactoring code.   
2.add feedback when control accessory.   
3.synchronization value when homebridge call the get function. (only electrify device)   
4.optimizing program structure, send fewer packets.   
5.optimizing config item name, easier to read.   
6.fixed some bug.   
7.add Button(single press, double press) virtual switch accessory.   
8.add Button2(single press, double press) virtual switch accessory.   
9.add SingleButton86(single press) virtual switch accessory.   
10.add DuplexButton86(left button single press, right button single press, both press) virtual switch accessory.   
11.add MagicSquare(flip90, flip180, move, tapTwice, shakeAir) virtual switch accessory.   
### 0.5.3
1.optimized code.   
### 0.5.2
1.fixed bug that gateway light brightness is 100 when it light up.   
### 0.5.1
1.fixed bug that natgas detector is not alarm.   
### 0.5.0
1.add support for water detector accessory.   
2.fixed bug that natgas detector is not alarm.   
3.fixed bug that smoke detector is not alarm.   
### 0.4.4
1.add log content that show plugin version when homebridge started.   
2.fixed bug that run homebridge error there is no MiAqaraPlatform in config.json file.   
### 0.4.3
1.fixed bug that gateway light sensor not support when value is 0;   
2.fixed bug that motion sensor version 2 light sensor not support when value is 0;   
### 0.4.2
1.adjustment gateway light sensor value(subtract 279).   
2.delete PlugBase, PlugBase86, SingleSwitch, DuplexSwitch, SingleSwitchLN, DuplexSwitchLN battery information.   
3.add motion sensor version 2 light sensor battery information.   
4.add setting accessory disable feature.   
5.fixed bug that electric curtain can't work, but there is no current operation state information now.   
### 0.4.1
1.code collation.   
### 0.4.0
1.add support for electric curtain accessory.   
2.add support for contact sensor version 2 accessory.   
3.add support for motion sensor version 2 accessory.   
4.add support for button version 2 accessory.   
5.add support for temperature and humidity sensor version 2 accessory.   
6.optimize log content.   
7.add setting default name feature.   
8.add setting default service type feature.   
9.fixed motion sensor bug that wrong trigger when homebridge start.   
10.adjustment gateway light sensor value(subtract 300).   
### 0.3.3
1.add single button 86 long press event.   
2.add duplex button 86 long press event.   
3.changed button click event value from Characteristic.ProgrammableSwitchEvent.CLICK back to Characteristic.ProgrammableSwitchEvent.SINGLE_PRESS.   
4.changed single button 86 click event value from Characteristic.ProgrammableSwitchEvent.CLICK back to Characteristic.ProgrammableSwitchEvent.SINGLE_PRESS.   
5.changed duplex button 86 click event value from Characteristic.ProgrammableSwitchEvent.CLICK back to Characteristic.ProgrammableSwitchEvent.SINGLE_PRESS.   
### 0.3.2
1.fixed bug that duplex switch LN charging state.   
2.fixed bug that single switch LN charging state.   
3.fixed bug that single button 86 charging state.   
4.changed button click event value from Characteristic.ProgrammableSwitchEvent.SINGLE_PRESS to Characteristic.ProgrammableSwitchEvent.CLICK.   
5.changed single button 86 click event value from Characteristic.ProgrammableSwitchEvent.SINGLE_PRESS to Characteristic.ProgrammableSwitchEvent.CLICK.   
6.changed duplex button 86 click event value from Characteristic.ProgrammableSwitchEvent.SINGLE_PRESS to Characteristic.ProgrammableSwitchEvent.CLICK.   
7.fixed bug that natgas detector is not alarm.   
8.fixed bug that smoke detector is not alarm.   
### 0.3.1
1.code collation.   
### 0.3.0
1.add support for single switch LN accessory.   
2.add support for duplex switch LN accessory.   
3.add support for plug base 86 accessory.   
4.add support for smoke detector accessory.   
5.add support for natgas detector accessory.   
### 0.2.1
1.change accessory registration mechanism, fixed bug that new accessory can't correlate associated with gateway.   
### 0.2.0
1.add support for duplex switch accessory.   
2.add support for single button 86 accessory.   
3.add support for duplex button 86 accessory.   
### 0.1.0
1.add support for plug base accessory.   
2.add support for magic square accessory.   
### 0.0.6
1.add some logs.
### 0.0.5
1.fixed bug.
### 0.0.4
1.fixed bug.
### 0.0.3
1.add support for gateway accessory: light sensor, hue light.
### 0.0.2
1.add support for single switch accessory.   
### 0.0.1
1.supported contact sensor accessory.   
2.supported motion sensor accessory.   
3.supported button accessory.   
4.supported temperature and humidity sensor accessory.   
