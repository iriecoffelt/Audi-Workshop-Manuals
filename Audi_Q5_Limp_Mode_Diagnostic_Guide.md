# Audi Q5 2.0L Limp Mode Diagnostic Guide

## 2019 Audi Q5 Premium Plus 2.0L TFSI (Non-Hybrid - Without High-Voltage System)

## Issue: 3800 RPM Limitation After Thermostat/Coolant Housing Replacement

### Problem Summary

After replacing the water cooler/thermostat housing without disconnecting the battery, the vehicle is in limp mode (emergency mode) limiting RPMs to 3800. This is a protective mode typically triggered by sensor/connector issues.

**⚠️ CRITICAL: The electronic throttle body REQUIRES an adaptation/reset after being disconnected or worked on. This is very likely the cause of your limp mode issue!**

---

## Key Connectors to Check Near Thermostat/Coolant Housing Area

**Note: All page numbers below are specific to 2019 Q5 2.0L without high-voltage system (non-hybrid models)**

Based on the workshop manual, these are the critical connectors that may have been disturbed during the thermostat/coolant housing replacement:

### 1. **Engine Speed Sender (Crank Position Sensor) -G28-**

- **PDF Page**: Shown in procedure on Page 2998-3010 (oil pressure switch removal for Audi A4/A5, Q5 without high-voltage system)
- **Location**: Near the thermostat housing area, connected to engine wiring harness
- **Critical**: This sensor tells the ECM the engine RPM. If this is faulty or has a bad connection, it can cause limp mode
- **Test**: Check connector for proper seating, corrosion, or bent pins
- **Resistance**: Refer to sensor specifications in manual

### 2. **Coolant Temperature Sender -G62-**

- **PDF Page**: 2739 (Procedure: "Removing and installing coolant temperature sender G62")
- **Location**: On cylinder head (gearbox end) - near thermostat housing
- **Test**: Check electrical connector -2- for proper connection

### 3. **Radiator Outlet Coolant Temperature Sender -G83-**

- **PDF Page**: 2835 (Procedure: "Removing and installing radiator outlet coolant temperature sender G83")
- **Location**: Varies by vehicle, connected near radiator/thermostat area
- **Test**: Check electrical connector for proper seating

### 4. **Coolant Shortage Indicator Sender -G32-**

- **PDF Page**: 2998-3010 (shown in oil pressure switch procedure for Audi A4/A5, Q5 without high-voltage system)
- **Location**: On coolant expansion tank
- **Test**: Check connector -4- or -5- (depending on model)
- **Note**: This sensor monitors coolant level

### 5. **Throttle Valve Module -GX3-**

- **PDF Page**: Referenced in 2.0L TFSI EA888evo4 engine section (starting Page 2557)
- **Location**: Connected to throttle body
- **CRITICAL**: The throttle body has multiple sensors that can cause limp mode if disconnected or damaged
- **⚠️ REQUIRES ADAPTATION**: The manual states "Adaptions must be performed after renewing throttle valve module" (PDF Page 2554). If the throttle body connector was unplugged during your repair, you MUST perform a throttle body adaptation using a diagnostic scanner.
- **Components**:
  - Throttle valve drive for electric throttle
  - Throttle valve drive angle sender 1
  - Throttle valve drive angle sender 2
- **Test**: Check main electrical connector on throttle body
- **Action Required**: Perform throttle body adaptation using Vehicle Diagnostic Tester (OBD-II scanner with Audi-specific capabilities)

### 6. **Charge Pressure Sender (Turbo Boost Sensor) -G31-**

- **PDF Page**: Referenced in 2.0L TFSI EA888evo4 engine section (starting Page 2557)
- **Location**: Connected near intake/throttle body area
- **Test**: Check electrical connector -1-

### 7. **Stage 3 Oil Pressure Switch -F447-**

- **PDF Page**: 2998-3010 (Audi A4/A5, Q5 without high-voltage system)
- **Location**: Near thermostat housing, connected to oil filter bracket
- **Test**: Check electrical connector -2-
- **Note**: Procedure shows connectors that must be unplugged near thermostat area (including engine speed sender -G28- and coolant connectors)

### 8. **Engine Control Unit -J623- Main Harness**

- **PDF Page**: Multiple references throughout manual
- **Location**: Main ECM connector
- **Note**: If any wires were pulled or stressed near the thermostat area, check for loose connections at the ECM

---

## Diagnostic Steps

### Step 1: Visual Inspection of All Connectors

1. **Check every connector** that was unplugged during the thermostat replacement
2. Look for:
   - Corrosion or moisture
   - Bent or damaged pins
   - Connectors not fully seated (listen for "click" when connecting)
   - Worn or damaged wiring insulation
   - Loose wire terminals inside connectors

### Step 2: Resistance Testing (Ohms)

For sensors, you'll need to check resistance values. Here's what to look for:

#### **Engine Speed Sender -G28-**

- **PDF Page**: 2998-3010 (shown in procedure for Q5 without high-voltage system)
- Disconnect the connector
- Measure resistance between pins (specific values will be in wiring diagrams)
- Typical range for hall sensors: Check for open circuit (OL) or short circuit (0 ohms) - both indicate failure

#### **Coolant Temperature Sender -G62-**

- **PDF Page**: 2739
- This is typically a negative temperature coefficient (NTC) thermistor
- Resistance decreases as temperature increases
- At room temperature (~20°C): Should read around 2000-3000 ohms
- At operating temperature (~80°C): Should read around 200-400 ohms
- Check for open circuit or short circuit

#### **Throttle Body Sensors**

- Check for continuity between pins
- Test throttle position sensors for proper resistance ranges
- Look for shorts or opens

### Step 3: Check for Diagnostic Trouble Codes (DTCs)

Even if the check engine light isn't on, there may be pending codes:

1. Use an OBD-II scanner to read all codes
2. Look for codes related to:
   - P-codes for throttle position sensors
   - Crank/cam position sensor codes
   - Coolant temperature sensor codes
   - Turbo boost sensor codes

### Step 4: Sensor Signal Testing (Voltage)

With the engine running or key on:

- Check sensor signal voltages
- Crank position sensor should show AC voltage signal when cranking
- Coolant temp sensor should show variable voltage based on temperature
- Throttle position sensors should change voltage as throttle opens/closes

---

## Most Likely Culprits Based on Your Symptoms

### 1. **⚠️ THROTTLE BODY ADAPTATION REQUIRED (MOST LIKELY CAUSE)**

- **PDF Page**: 2554 ("Performing adaptions after renewing a component")
- **Why**: If the throttle body connector was unplugged during your repair, the ECM has lost its learned throttle position calibration. Without adaptation, the ECM doesn't know the correct throttle positions and will activate limp mode for safety.
- **Action**: **Perform throttle body adaptation using an OBD-II scanner with Audi-specific diagnostic capabilities** (like VCDS, OBDeleven, or professional scan tool). This MUST be done after any throttle body disconnection.
- **Manual Reference**: The workshop manual explicitly states "Adaptions must be performed after renewing throttle valve module" (found in multiple locations, including procedures around PDF Page 2554+).

### 2. **Engine Speed Sender -G28- (CRANK POSITION SENSOR)**

- **PDF Page**: 2998-3010 (shown in oil pressure switch procedure for Q5 without high-voltage system)
- **Why**: If this sensor has a poor connection, the ECM can't properly determine engine speed, triggering limp mode
- **Action**: Check this connector - it's often located near the thermostat area and easy to damage

### 3. **Throttle Body Connection**

- **Why**: The throttle body has multiple sensors. If any connection is loose, limp mode activates
- **Action**: Disconnect and reconnect the throttle body connector, ensuring it clicks into place, THEN perform throttle body adaptation

### 4. **Coolant Temperature Sensor -G62-**

- **PDF Page**: 2739
- **Why**: False temperature readings can cause protective limiting
- **Action**: Check connector and test resistance values

---

## Manual References

### Key Sections in the Workshop Manual (PDF Page Numbers - 2019 Q5 2.0L Without High-Voltage System):

- **Page 2554**: ⚠️ **CRITICAL**: "Performing adaptions after renewing a component" - Includes throttle body adaptation procedure
- **Page 2557-2558**: 2.0L TFSI EA888evo4 engine section - Table of contents
- **Page 2739**: Removing and installing coolant temperature sender G62 (all 2.0L models)
- **Page 2835**: Removing and installing radiator outlet coolant temperature sender G83 (all 2.0L models)
- **Page 2998-3010**: Stage 3 oil pressure switch procedures for Audi A4/A5, Q5 without high-voltage system (shows all connectors unplugged near thermostat area)
- **Page 3024**: Connection diagram - coolant hoses, Audi A4/A5, Q5 without high-voltage system
- **Page 3084-3091**: Assembly overview - electric coolant pump, Audi A4/A5, Q5 without high-voltage system
- **Page 3108**: Removing and installing coolant circulation pump V50 - Audi A4/A5, Q5 without high-voltage system
- **Page 3114**: Removing and installing continued coolant circulation pump V51 - Audi A4/A5, Q5 without high-voltage system

### To Find in Manual:

Search the markdown file for:

- "Q5" AND "coolant pump"
- "unplug electrical connector"
- "G28" (engine speed sender)
- "G62" (coolant temp sender)
- "G83" (radiator outlet temp sender)
- "throttle valve module"

---

## Important Notes

1. **⚠️ THROTTLE BODY ADAPTATION (CRITICAL - DO THIS FIRST!)**:

   - If you unplugged the throttle body connector during the thermostat replacement, you MUST perform a throttle body adaptation
   - The manual explicitly requires this: "Adaptions must be performed after renewing throttle valve module"
   - Use an OBD-II scanner with Audi diagnostic capabilities:
     - **VCDS** (VAG-COM) - popular for DIY
     - **OBDeleven** - mobile app-based
     - **Professional scan tool** - at a shop or dealership
   - The adaptation procedure calibrates the throttle position sensors so the ECM knows the correct throttle angles
   - Without this, the ECM will limit RPMs for safety (limp mode)
   - **This is very likely the cause of your 3800 RPM limitation!**

2. **Battery Disconnection**: Since you didn't disconnect the battery, the ECM may have stored fault codes when connectors were unplugged with key on. Consider:

   - Disconnecting battery for 30 minutes to reset ECM
   - Clearing codes with OBD-II scanner
   - Re-checking all connectors after reset

3. **Connector Cleaning**: If connectors got wet or dirty during repair:

   - Clean with electrical contact cleaner
   - Ensure connectors are completely dry before reconnecting

4. **Wiring Damage**: Check for wires that may have been:

   - Pinched during reassembly
   - Pulled or stretched
   - Cut by sharp edges

5. **Testing Order**: Start with visual inspection, then check most critical sensors (G28, throttle body) before moving to others.

---

## Quick Reference: Connector Locations Near Thermostat

When removing the thermostat/coolant housing on a 2019 Q5 2.0L, these connectors typically need to be unplugged:

1. Engine speed sender -G28- connector (shown in PDF Page 2998-3010 procedure)
2. Coolant temperature sender -G62- connector (PDF Page 2739)
3. Radiator outlet temp sender -G83- connector (PDF Page 2835)
4. Oil pressure switch -F447- connector (PDF Page 2998-3010 - Audi A4/A5, Q5 without high-voltage system)
5. Throttle valve module connector (2.0L engine section)
6. Charge pressure sender -G31- connector (2.0L engine section)
7. Coolant shortage indicator sender -G32- connector (shown in PDF Page 2998-3010 procedure)
8. Coolant circulation pump connectors (PDF Page 3084-3091, 3108, 3114 - Q5 without high-voltage system)
9. Engine wiring harness connections

**Check ALL of these for proper connection and damage!**

---

_Generated from Audi Workshop Manual 2017-2023 for Q5/SQ5/RSQ5_
_Manual available at: https://github.com/iriecoffelt/Audi-Workshop-Manuals_
_**Important**: All page numbers are specific to 2019 Audi Q5 2.0L Premium Plus (non-hybrid, without high-voltage system)_
