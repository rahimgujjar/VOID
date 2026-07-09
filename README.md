# VOID . *clarity in chaos*

**VOID** is a high-performance, local-first mobile application designed to resolve complex desktop scheduling constraints on mobile devices. 

*Note: This repository serves as an architectural overview and release hub for the compiled APK. The underlying C++ parsing engine and proprietary Flutter UI source code are currently closed-source.*

## 📥 Download & Installation
The latest compiled Android APK is available in the [Releases](../../releases) tab.

## 🏗️ System Architecture

VOID is engineered with a strict "local-first" data processing philosophy to ensure absolute user privacy regarding sensitive educational documents.

* **Frontend Framework:** Flutter / Dart
* **Parsing Engine:** Native C++ accessed via Dart Foreign Function Interface (FFI)
* **Authentication & OTA Routing:** Google Firebase & Supabase

### Core Technical Features

#### 1. Zero-Upload PDF Heuristic Engine
Traditional timetable applications upload user documents to a cloud server for parsing. VOID eliminates this data exposure risk by utilizing a custom C++ heuristic engine that processes and normalizes complex university PDF schedules entirely offline. No personal document ever leaves the physical device.

#### 2. Cross-Language Bindings (Dart FFI)
To achieve the raw computational speed required to parse unstructured PDF data natively on a mobile CPU without UI thread blocking, the core logic is written in C++ and communicates with the Flutter frontend via strict memory-safe FFI bindings.

#### 3. Secure Over-The-Air (OTA) Updates
Dynamic timetable changes are routed securely using unique, anonymized User IDs via Firebase/Supabase, ensuring that cloud synchronization occurs without compromising the local-first architecture of the parsed PDF data.

## 🔐 Security & Privacy Controls
Designed with data governance and privacy by default:
* **Data Isolation:** Parsed schedules and SQLite databases are strictly sandboxed within the local device storage.
* **Telemetry Minimization:** Cloud connections are limited solely to authentication states, crash logging, and OTA routing.
* **Absolute Eradication:** Engineered a "Local Wipe" trigger that permanently purges all local databases, parsed schedules, and session tokens directly from the hardware.

For full data handling procedures, please refer to the official [VOID Privacy Policy](https://github.com/rahimgujjar/VOID-legal/blob/main/privacy-policy.md).
