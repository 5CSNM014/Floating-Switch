# SPDX-FileCopyrightText: 2003 Argonne National Laboratory
#
# SPDX-License-Identifier: EPICS

TOP=../..

include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

#=============================
# Build the IOC application

PROD_IOC = ASwitch
# ASwitch.dbd will be created and installed
DBD += ASwitch.dbd

# ASwitch.dbd will be made up from these files:
ASwitch_DBD += base.dbd
ASwitch_DBD += asyn.dbd # <--------- 追加(1)
ASwitch_DBD += stream.dbd # <--------- 追加(2)
ASwitch_DBD += drvAsynSerialPort.dbd # <--------- 追加(3)

# Include dbd files from all support applications:
#ASwitch_DBD += xxx.dbd

# Add all the support libraries needed by this IOC
#ASwitch_LIBS += xxx

# ASwitch_registerRecordDeviceDriver.cpp derives from ASwitch.dbd
ASwitch_SRCS += ASwitch_registerRecordDeviceDriver.cpp

# Build the main IOC entry point on workstation OSs.
ASwitch_SRCS_DEFAULT += ASwitchMain.cpp
ASwitch_SRCS_vxWorks += -nil-

# Add support from base/src/vxWorks if needed
#ASwitch_OBJS_vxWorks += $(EPICS_BASE_BIN)/vxComLibrary

# Finally link to the EPICS Base libraries
ASwitch_LIBS += $(EPICS_BASE_IOC_LIBS)
ASwitch_LIBS += asyn  # <--------- 追加(4)
ASwitch_LIBS += stream  # <--------- 追加(5)

#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE

