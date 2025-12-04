[Main Menu](../README.md) | [Session 4](../session4/README.md) | [Exercise-4-3](../session4/Exercise-4-3.md)

# Exercise 4-3 

Drools Rules

| UEI                                                               | Group Alarm    |
|:------------------------------------------------------------------|:---------------|
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChange/panMotor| group5 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChangeClear/panMotor-clear| group5 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChange/tiltMotor| group5 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChangeClear/tiltMotor-clear| group5 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChange/zoomMotor| group5 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChangeClear/zoomMotor-clear| group5 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChange/apertureMotor| group5 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChangeClear/apertureMotor-clear| group5 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChange/focusMotor| group5 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChangeClear/focusMotor-clear| group5 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChange/wiperMotor| group6|
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChangeClear/wiperMotor-clear| group6|
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChange/heater| group6|
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChangeClear/heater-clear| group6|
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChange/fluidLevel| group6|
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChangeClear/fluidLevel-clear| group6|
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChange/videoSignal| group4|
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChangeClear/videoSignal-clear| group4|
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChange/housingTamper| group6|
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChangeClear/housingTamper-clear| group6 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChange/washerMotorFault| group6|
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChangeClear/washerMotorFault-clear| group6 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChange/configPlugFault| group2|
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChangeClear/configPlugFault-clear| group2 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChange/tvbuCameraCommsFault| group3|
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChangeClear/tvbuCameraCommsFault-clear| group3 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/healthChangeClear| group1 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/tamperDetectedCleared| group1 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/logicInputChange| group1 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/logicInputChangeCleared| group1 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/commsStateChange| group1 |
| uei.opennms.org/traps/CHUBB-TVBS-CAMERA-MIB/commsStateChangeClear| group1 |


You should use the docker compose project under the `drools-corellation` folder for this exercise
[session4/drools-correlation/minimal-minion-activemq/](../session4/drools-correlation/minimal-minion-activemq/).


We also looked in [Session 2](../session2/README.md) at how business servicing monitoring can build a graph of services which allows us to determine the business impact of a monitored service failure.

