# improved-octo-meme
Programs and description for the simulation for ROB5 project - Automatic Laser Tool Changer


Program versions used:

RoboDK : 5.2

TExxxx | TC3 Engineering
3.1.4024.11

Unified Automation UaExpert v 1.5.1

# TwinCat setup
The variables in MAIN should be declared as:

PROGRAM MAIN

VAR

	Count: INT;
	state: INT;
	STOP: PLC_Stop;
	lockValve AT %Q*: BOOL;
	unlockValve AT %Q*: BOOL;
	inSensor AT %I*: BOOL;
	Delay: TON;
	Delay1: TON;
	preSensor: BOOL;
	
END_VAR

In a GVLs a global variables list is created, named OPCVAR, with variables declared as:

{attribute 'qualified_only'}

VAR_GLOBAL

	{attribute 'OPC.UA.DA' := '1'}
	StationParameter: STRING;
	{attribute 'OPC.UA.DA' := '1'}
	StationValue: STRING;
	inPos1: INT;
	inPos2: INT;
	pistLock: INT;
	
END_VAR
