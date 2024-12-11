TOP=../..

include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

#=============================
# Build the IOC application

PROD_IOC = ArduinoCmd
# ArduinoCmd.dbd will be created and installed
DBD += ArduinoCmd.dbd

# ArduinoCmd.dbd will be made up from these files:
ArduinoCmd_DBD += base.dbd
ArduinoCmd_DBD += asyn.dbd # <--------- 追加(1)
ArduinoCmd_DBD += stream.dbd # <--------- 追加(2)
ArduinoCmd_DBD += drvAsynSerialPort.dbd # <--------- 追加(3)

# Include dbd files from all support applications:
#ArduinoCmd_DBD += xxx.dbd

# Add all the support libraries needed by this IOC
#ArduinoCmd_LIBS += xxx

# ArduinoCmd_registerRecordDeviceDriver.cpp derives from ArduinoCmd.dbd
ArduinoCmd_SRCS += ArduinoCmd_registerRecordDeviceDriver.cpp

# Build the main IOC entry point on workstation OSs.
ArduinoCmd_SRCS_DEFAULT += ArduinoCmdMain.cpp
ArduinoCmd_SRCS_vxWorks += -nil-

# Add support from base/src/vxWorks if needed
#ArduinoCmd_OBJS_vxWorks += $(EPICS_BASE_BIN)/vxComLibrary

# Finally link to the EPICS Base libraries
ArduinoCmd_LIBS += $(EPICS_BASE_IOC_LIBS)
ArduinoCmd_LIBS += asyn  # <--------- 追加(4)
ArduinoCmd_LIBS += stream  # <--------- 追加(5

#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE

