# Audi Q5 2.0L Limp Mode Diagnostic Guide

## Issue: 3800 RPM Limitation After Thermostat/Coolant Housing Replacement

### Problem Summary

After replacing the water cooler/thermostat housing without disconnecting the battery, the vehicle is in limp mode (emergency mode) limiting RPMs to 3800. This is a protective mode typically triggered by sensor/connector issues.

---

## Key Connectors to Check Near Thermostat/Coolant Housing Area

Based on the workshop manual, these are the critical connectors that may have been disturbed during the thermostat/coolant housing replacement:

### 1. **Engine Speed Sender (Crank Position Sensor) -G28-**

- **PDF Page**: ~828, ~2839, ~3585, ~4317, ~5333, ~5825, ~10442, ~15686
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

- **PDF Page**: ~2998, ~3020, ~3021, ~4108, ~4115 (shown in oil pressure switch procedures for Q5)
- **Location**: On coolant expansion tank
- **Test**: Check connector -4- or -5- (depending on model)
- **Note**: This sensor monitors coolant level

### 5. **Throttle Valve Module -GX3-**

- **PDF Page**: ~2635, ~7360, ~10761, ~10762, ~11286, ~15473 (Throttle valve module references)
- **Location**: Connected to throttle body
- **Critical**: The throttle body has multiple sensors that can cause limp mode if disconnected or damaged
- **Components**:
  - Throttle valve drive for electric throttle
  - Throttle valve drive angle sender 1
  - Throttle valve drive angle sender 2
- **Test**: Check main electrical connector on throttle body

### 6. **Charge Pressure Sender (Turbo Boost Sensor) -G31-**

- **PDF Page**: ~3403, ~4204, ~5063, ~11977 (Procedure: "Removing and installing charge pressure sender G31")
- **Location**: Connected near intake/throttle body area
- **Test**: Check electrical connector -1-

### 7. **Stage 3 Oil Pressure Switch -F447-**

- **PDF Page**: 2999-3016 (Q5 with high-voltage system), ~14906, ~14907 (Q5 oil pressure switch procedures)
- **Location**: Near thermostat housing, connected to oil filter bracket
- **Test**: Check electrical connector -2-
- **Note**: Procedure shows connectors that must be unplugged near thermostat area

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

- **PDF Page**: See references above (~828, ~2839, ~3585, etc.)
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

### 1. **Engine Speed Sender -G28- (CRANK POSITION SENSOR)**

- **PDF Page**: ~828, ~2839, ~3585, ~4317, ~5333, ~5825, ~10442, ~15686
- **Why**: If this sensor has a poor connection, the ECM can't properly determine engine speed, triggering limp mode
- **Action**: Check this connector FIRST - it's often located near the thermostat area and easy to damage

### 2. **Throttle Body Connection**

- **Why**: The throttle body has multiple sensors. If any connection is loose, limp mode activates
- **Action**: Disconnect and reconnect the throttle body connector, ensuring it clicks into place

### 3. **Coolant Temperature Sensor -G62-**

- **PDF Page**: 2739
- **Why**: False temperature readings can cause protective limiting
- **Action**: Check connector and test resistance values

---

## Manual References

### Key Sections in the Workshop Manual (PDF Page Numbers):

- **Page 2557-2558**: 2.0L TFSI EA888evo4 engine section - Table of contents
- **Page 2739**: Removing and installing coolant temperature sender G62
- **Page 2835**: Removing and installing radiator outlet coolant temperature sender G83
- **Page 2999-3016**: Stage 3 oil pressure switch procedures for Q5 (shows all connectors unplugged near thermostat area)
- **Page 3082-3091**: Coolant pump/thermostat assembly overview for Q5
- **Page 13101**: Assembly overview - coolant pump/thermostat
- **Page 14906-14907**: Q5 oil pressure switch procedures (with high-voltage system)

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

1. **Battery Disconnection**: Since you didn't disconnect the battery, the ECM may have stored fault codes when connectors were unplugged with key on. Consider:

   - Disconnecting battery for 30 minutes to reset ECM
   - Clearing codes with OBD-II scanner
   - Re-checking all connectors after reset

2. **Connector Cleaning**: If connectors got wet or dirty during repair:

   - Clean with electrical contact cleaner
   - Ensure connectors are completely dry before reconnecting

3. **Wiring Damage**: Check for wires that may have been:

   - Pinched during reassembly
   - Pulled or stretched
   - Cut by sharp edges

4. **Testing Order**: Start with visual inspection, then check most critical sensors (G28, throttle body) before moving to others.

---

## Quick Reference: Connector Locations Near Thermostat

When removing the thermostat/coolant housing on a 2019 Q5 2.0L, these connectors typically need to be unplugged:

1. Engine speed sender -G28- connector (PDF Page ~828, ~2839, ~3585, etc.)
2. Coolant temperature sender -G62- connector (PDF Page 2739)
3. Radiator outlet temp sender -G83- connector (PDF Page 2835)
4. Oil pressure switch -F447- connector (PDF Page 2999-3016)
5. Throttle valve module connector (PDF Page ~2635, ~7360, etc.)
6. Charge pressure sender -G31- connector (PDF Page ~3403, ~4204, ~5063)
7. Coolant shortage indicator sender -G32- connector (PDF Page ~2998, ~3020)
8. Various coolant pump connectors (PDF Page 3082-3091, 13101)
9. Engine wiring harness connections

**Check ALL of these for proper connection and damage!**

---

_Generated from Audi Workshop Manual 2017-2023 for Q5/SQ5/RSQ5_
_Manual available at: https://github.com/iriecoffelt/Audi-Workshop-Manuals_
