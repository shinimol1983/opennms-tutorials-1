
## CAMERA CONTROLLER (CHUBB SNMP) Traps
This page contains example traps for the CAMERA CONTROLLER.

In this case the traps contain an additional FIRST varbind cameraIdentifier oid .1.3.6.1.4.1.52330.6.2.7.0

The remaining varbinds are the same as in the CHUBB-TVBS-CAMERA-MIB

I have included a comment at the end of each trap definition so that it is easy to see which traps have been sent from the terminal history


## Health Change notification

### Values
healthChange notification  oid .1.3.6.1.4.1.52330.6.2.0.1

varbind 1:  cameraIdentifier oid .1.3.6.1.4.1.52330.6.2.7.0

varbind 2:  healthChangeReason oid .1.3.6.1.4.1.52330.6.2.1.0

values  INTEGER {panMotor(0),tiltMotor(1),zoomMotor(2),apertureMotor(3),focusMotor(4),wiperMotor(5),heater(6),fluidLevel(7),
videoSignal(8), housingTamper(9), washerMotorFault(10), configPlugFault(11), tvbuCameraCommsFault(12) }

varbind 3: faultState oid .1.3.6.1.4.1.52330.6.2.5.0

values:  INTEGER {clear(0), triggered(1) }

### netsnmp healthChange notification test traps

#### panMotor raise
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 0  .1.3.6.1.4.1.52330.6.2.5.0 i 1    # panMotor raise
```

#### panMotor clear
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 0  .1.3.6.1.4.1.52330.6.2.5.0 i 0    # panMotor clear
```

#### tiltMotor raise
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 1  .1.3.6.1.4.1.52330.6.2.5.0 i 1    # tiltMotor raise
```

#### tiltMotor clear
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 1  .1.3.6.1.4.1.52330.6.2.5.0 i 0    # tiltMotor clear
```

#### zoomMotor raise
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 2  .1.3.6.1.4.1.52330.6.2.5.0 i 1    # zoomMotor raise
```

#### zoomMotor clear
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 2  .1.3.6.1.4.1.52330.6.2.5.0 i 0    # zoomMotor clear
```

#### apertureMotor raise
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 3  .1.3.6.1.4.1.52330.6.2.5.0 i 1    # apertureMotor raise
```

#### apertureMotor clear
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 3  .1.3.6.1.4.1.52330.6.2.5.0 i 0    # apertureMotor clear
```

#### focusMotor raise
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 4  .1.3.6.1.4.1.52330.6.2.5.0 i 1    # focusMotor raise
```

#### focusMotor clear
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 4  .1.3.6.1.4.1.52330.6.2.5.0 i 0    # focusMotor clear
```

#### wiperMotor raise
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 5  .1.3.6.1.4.1.52330.6.2.5.0 i 1    # wiperMotor raise
```

#### wiperMotor clear
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 5  .1.3.6.1.4.1.52330.6.2.5.0 i 0    # wiperMotor clear
```

#### heater raise
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 6  .1.3.6.1.4.1.52330.6.2.5.0 i 1    # heater raise
```
#### heater clear
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 6  .1.3.6.1.4.1.52330.6.2.5.0 i 0    # heater clear
```

#### fluidLevel raise
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 7  .1.3.6.1.4.1.52330.6.2.5.0 i 1    # fluidLevel raise
```
#### fluidlevel clear
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 7 .1.3.6.1.4.1.52330.6.2.5.0 i 0    # fluidlevel clear
```

#### videoSignal raise
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 8  .1.3.6.1.4.1.52330.6.2.5.0 i 1    # videoSignal raise
```

#### videoSignal clear
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 8  .1.3.6.1.4.1.52330.6.2.5.0 i 0    # videoSignal clear
```

#### housingTamper raise
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 9  .1.3.6.1.4.1.52330.6.2.5.0 i 1    # housingTamper raise
```

#### housingTamper clear
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 9  .1.3.6.1.4.1.52330.6.2.5.0 i 0    # housingTamper clear
```


#### washerMotorFault raise
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 10  .1.3.6.1.4.1.52330.6.2.5.0 i 1    # washerMotorFault raise
```

#### washerMotorFault clear
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 10  .1.3.6.1.4.1.52330.6.2.5.0 i 0    # washerMotorFault clear
```
 

#### configPlugFault raise
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 11  .1.3.6.1.4.1.52330.6.2.5.0 i 1     # configPlugFault raise
```

#### configPlugFault clear
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 11  .1.3.6.1.4.1.52330.6.2.5.0 i 0    # configPlugFault clear
```


#### tvbuCameraFault raise
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 12  .1.3.6.1.4.1.52330.6.2.5.0 i 1    # tvbuCameraFault raise
```

#### tvbuCameraFault clear
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.1        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.1.0 i 12  .1.3.6.1.4.1.52330.6.2.5.0 i 0    # tvbuCameraFault clear
```

## Tamper Detected notification

### Values

tamperDetected notification  oid .1.3.6.1.4.1.52330.6.2.0.2

varbind 1:  cameraIdentifier oid .1.3.6.1.4.1.52330.6.2.7.0

varbind 2:  tamperState oid .1.3.6.1.4.1.52330.6.2.2.0

values:  INTEGER {clear(0), triggered(1) }

### netsnmp tamperDetected notification test traps

#### tamperDetected raise
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.2        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.2.0 i 1    # tamperDetected raise
```

#### tamperDetected clear
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.2        .1.3.6.1.4.1.52330.6.2.7.0 s camera_008   .1.3.6.1.4.1.52330.6.2.2.0 i 0    # tamperDetected clear
```

## Logic Input Change notification

### Values

logicInputChange notification  oid .1.3.6.1.4.1.52330.6.2.0.3

varbind 1:  cameraIdentifier oid .1.3.6.1.4.1.52330.6.2.7.0

varbind 2:  logicInput oid .1.3.6.1.4.1.52330.6.2.3.0

varbind 3: logicInputState oid .1.3.6.1.4.1.52330.6.2.4.0

values:  INTEGER {clear(0), triggered(1) }

Note that in this case there is only one alarm definition but different alarms are created depending on the logic input selected (i.e. the integer value of the second varbind)

### netsnmp logicInputChange notification test traps

#### logicInputChange raise
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.3       .1.3.6.1.4.1.52330.6.2.7.0  s camera_008   .1.3.6.1.4.1.52330.6.2.3.0  i 0  .1.3.6.1.4.1.52330.6.2.4.0 i 0    # logicInputChange raise
```

#### logicInputChange clear
```
ssnmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.3       .1.3.6.1.4.1.52330.6.2.7.0  s camera_008   .1.3.6.1.4.1.52330.6.2.3.0  i 0  .1.3.6.1.4.1.52330.6.2.4.0 i 1    # logicInputChange clear
```

## Comms State Change notification

### Values

commsStateChange notification  oid .1.3.6.1.4.1.52330.6.2.0.4

varbind 1:  cameraIdentifier oid .1.3.6.1.4.1.52330.6.2.7.0

varbind 2:  commsStateReason oid  .1.3.6.1.4.1.52330.6.2.6

values:   INTEGER {good(0), faulty(1) }

Note that in this case there is only one alarm definition but different alarms are created depending on the logic input selected (i.e. the integer value of the second varbind)

### netsnmp commsStateChange notification test traps

#### commsStateChange  raise
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.4      .1.3.6.1.4.1.52330.6.2.7.0  s camera_008   .1.3.6.1.4.1.52330.6.2.6  i 1     # commsStateChange  raise 
```

#### commsStateChange  clear
```
snmptrap -v 2c -c public horizon:1162 ""  .1.3.6.1.4.1.52330.6.2.0.4       .1.3.6.1.4.1.52330.6.2.7.0  s camera_008   .1.3.6.1.4.1.52330.6.2.6  i 0     # commsStateChange  clear
```

