# Embedded Systems Course Project

## Network Audit Tool

---

## 1. Project Idea

The idea of this project is to build a small, handheld network scanner—referred to as a **Network Audit Tool** for flashiness.

The project’s hardware requirements call for:

- Sensors as inputs
- Physical outputs
- External outputs

Two possible hardware configurations are being considered:

1. A **bare-bones version**
2. A **full-suite version**

---

## 2. Hardware Plans

### 2.1 Bare-Bones Version

The current hardware plan for the bare-bones version includes:

- A Raspberry Pi Pico W
- A small LCD screen
- An LED light

#### Capabilities

The Raspberry Pi Pico W’s built-in Wi-Fi capabilities are sufficient for performing:

- Simple network sweeps
- Port scans
- Outputting the collected information to an external output

#### Limitations

The Raspberry Pi Pico W is unable to perform:

- Active radio-wave scanning
- Packet sniffing

---

### 2.2 Full-Suite Version

The current hardware plan for the full-suite version includes:

- A Raspberry Pi Pico W
- An ESP32-32U for co-processing
- A 2.4 GHz rubber duck antenna, which should be attachable to the ESP32
- A small LCD screen
- An LED light

While the Raspberry Pi Pico W has low-level Wi-Fi capabilities, the addition of a dedicated antenna allows the device to scan raw 802.11 radio waves from the air.

In theory, this should allow the device to perform both passive airwave scanning and active network enumeration.

---

## 3. Passive Airwave Scanning

The full-suite version should be able to perform the following passive scanning operations:

### 3.1 Access Point Discovery

  - Discover available wireless access points.

### 3.2 Signal Strength Mapping

  - Measure and map the signal strength of detected wireless networks.

### 3.3 Security Protocol Mapping

  - Identify the password and encryption standards used by detected networks.

### 3.4 Channel Analysis

  - Map the 2.4 GHz Wi-Fi channels from **1 through 13** and analyse their traffic congestion.

### 3.5 Promiscuous Device Detection

  - Scan 802.11 radio waves for management frames used for MAC addressing.

---

## 4. Active Network Enumeration

In addition to passive scanning, the device will be able to perform active network enumeration.

This would include the following operations:

### 4.1 Subnet Host Mapping

Identify every active device on the network.

### 4.2 Port and Service Discovery

Identify ports and their associated services.

---

## 5. Development and Build

### 5.1 Hardware Selection

The final hardware route will be decided based on the availability of components.

The project will use either:

- The bare-bones hardware version
- The full-suite hardware version

### 5.2 Programming Language

The software running on the device will be written in **MicroPython**.

MicroPython includes native modules such as:

- `network`
- `socket`

These modules make writing the scanning functionality relatively straightforward.

### 5.3 Why MicroPython?

C++ could provide additional speed and lower overhead. However, these advantages are unnecessary for a project of this scope.

For this reason, MicroPython will be used for the project.
