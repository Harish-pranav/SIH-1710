# Smart India Hackathon Workshop
# Date:17/09/2026
## Register Number:212225040117
## Name: HARISH PRANAV 
# SIH 1710: Enhancing Navigation for Railway Station Facilities and Locations

## Problem Statement

Large railway stations are complex environments containing multiple platforms, entrances, exits, ticket counters, waiting halls, restrooms, food courts, lifts, escalators, foot-over bridges, parking areas, and other passenger facilities. Passengers, particularly those unfamiliar with the station, elderly passengers, and persons with disabilities, may have difficulty locating these facilities and reaching their destinations efficiently.

The proposed solution is a comprehensive indoor navigation platform that provides real-time, step-by-step guidance within railway stations through mobile applications and interactive digital kiosks.

## Problem Creator

**Organization:** Ministry of Railways, Government of India

---

# Proposed Solution

## RailNav 360

RailNav 360 is an intelligent indoor railway station navigation system that creates a digital representation of the station and provides passengers with accurate, accessible, and real-time navigation.

The system combines:

* Interactive 2D/3D station maps
* Indoor positioning
* Turn-by-turn navigation
* Accessibility-aware route planning
* Voice-guided navigation
* Digital kiosks
* Real-time station updates
* AI-powered natural language assistance
* Multilingual support

Passengers can search for any station facility or destination and receive a route based on their current location and navigation preferences.

## Key Features

### 1. Interactive Station Map

The application provides a detailed digital map containing:

* Platforms
* Ticket counters
* Entrances and exits
* Restrooms
* Waiting halls
* Food courts
* Lifts
* Escalators
* Foot-over bridges
* Parking areas
* Medical facilities
* Other station facilities

The map can be displayed in 2D or 3D depending on the implementation.

### 2. Indoor Positioning

Since GPS accuracy is limited inside buildings, the system uses indoor positioning technologies such as:

* BLE Beacons
* QR Code Markers
* Wi-Fi-based positioning
* Smartphone sensors
* UWB for advanced deployments

For the MVP, QR-based location selection will be used as the primary positioning mechanism, with BLE treated as an optional extension.

### 3. Intelligent Route Planning

The station is represented as a graph:

```text
Node = Location or Facility
Edge = Walkable Path
Weight = Distance + Walking Time + Accessibility + Temporary Restrictions
```

The navigation engine uses algorithms such as A* or Dijkstra to calculate suitable routes.

The system can provide:

* Shortest route
* Fastest route
* Accessible route
* Alternative route
* Route avoiding closed areas

### 4. Accessibility-Aware Navigation

Passengers can select navigation preferences according to their requirements.

For example, wheelchair mode can avoid:

* Stairs
* Inaccessible corridors
* Restricted entrances

and prioritize:

* Lifts
* Ramps
* Accessible corridors
* Suitable entrances

Additional accessibility features include:

* Voice navigation
* Large text
* High-contrast interface
* Screen-reader compatibility
* Vibration alerts
* Simplified navigation

### 5. Voice-Guided Navigation

The system provides spoken instructions such as:

```text
Proceed straight for 20 metres.
Turn left at the ticket counter.
The lift is 8 metres ahead.
Platform 4 entrance is on your right.
```

This feature is particularly useful for visually impaired passengers and users who cannot continuously view their phone.

### 6. Digital Kiosk

Interactive kiosks placed throughout the railway station provide an alternative navigation interface.

Passengers can:

1. Select their current location.
2. Search for a destination.
3. View the route on the station map.
4. Receive directions.
5. Scan a QR code to transfer the route to their mobile phone.

### 7. Real-Time Updates

The navigation system supports dynamic updates to reflect changes in station conditions.

Examples include:

* Platform changes
* Temporary facility closures
* Lift or escalator outages
* Blocked corridors
* Temporary restricted areas
* Changes in facility locations

When a route becomes unavailable, the navigation engine automatically calculates an alternative path.

### 8. AI-Based Navigation Assistant

An AI assistant enables passengers to interact with the system using natural language.

Examples:

```text
"Where is the nearest restroom?"

"How do I reach Platform 7 without using stairs?"

"Find the nearest lift."

"How can I reach Platform 5 from the main entrance?"
```

The AI interprets the request and converts it into structured navigation parameters. The actual route calculation is performed by the deterministic navigation engine.

### 9. Multilingual Support

The system can support multiple Indian languages to improve accessibility for passengers from different regions.

The interface and voice instructions can be adapted to languages such as:

* English
* Hindi
* Tamil
* Telugu
* Kannada
* Malayalam
* Bengali
* Marathi

---
# Use Cases

## Use Case 1: Facility Search

A passenger searches for a facility such as a restroom, ticket counter, food court, lift, or waiting area.

The system identifies the nearest suitable facility and generates a route.

## Use Case 2: Platform Navigation

A passenger enters or selects a platform number.

The system calculates the route from the passenger's current location to the required platform.

## Use Case 3: Wheelchair Navigation

A passenger selects wheelchair mode.

The system avoids stairs and inaccessible pathways and generates a suitable route using lifts, ramps, and accessible corridors.

## Use Case 4: Voice Navigation

A passenger enables voice guidance.

The system provides spoken instructions throughout the journey.

## Use Case 5: Digital Kiosk Navigation

A passenger uses a touchscreen kiosk to find a destination and transfers the generated route to their phone using a QR code.

## Use Case 6: Dynamic Route Recalculation

A previously generated route becomes unavailable due to construction, crowd control, equipment failure, or operational changes.

The backend receives the update and recalculates an alternative route.

## Use Case 7: Multilingual Assistance

The passenger selects a preferred language and receives navigation instructions and interface content in that language.

---

# Technology Stack

## Mobile Application

* Flutter
* Dart
* Android/iOS
* Mapbox or custom map renderer
* QR Scanner
* Bluetooth/BLE integration
* Speech-to-Text
* Text-to-Speech

## Backend

* Python
* FastAPI
* Uvicorn
* REST API
* WebSocket
* Pydantic

## Database

* PostgreSQL
* PostGIS
* Redis

PostGIS can be used for spatial data, while Redis can support caching and fast access to frequently changing data.

## Navigation Engine

* Graph-based station representation
* A* Algorithm
* Dijkstra Algorithm
* Accessibility-aware routing
* Dynamic route recalculation

## AI and NLP

* Large Language Model API or local LLM
* Natural Language Processing
* Speech-to-Text
* Text-to-Speech
* Intent Detection
* Query-to-Navigation Parameter Mapping

## Digital Twin and 3D

* Blender
* GLTF/GLB
* Unity / Unreal Engine / Web-based 3D rendering

For a lightweight prototype, a 2D vector-based map with 3D-style visualization can also be used.

## Kiosk

* Flutter or Web Application
* Touchscreen
* QR Scanner
* Speaker
* Windows or Android-based kiosk hardware

---

# Dependencies

## Software Dependencies

### Mobile Application

* Flutter SDK
* Dart SDK
* Android Studio
* Map rendering SDK
* QR scanning library
* Bluetooth/BLE library
* Speech-to-Text library/API
* Text-to-Speech library/API

### Backend

* Python 3.x
* FastAPI
* Uvicorn
* PostgreSQL
* PostGIS
* Redis
* WebSocket support
* Pydantic

### AI

* LLM API or local LLM
* Speech Recognition
* Text-to-Speech service
* NLP framework where required

### 3D

* Blender
* GLTF/GLB assets
* Unity, Unreal Engine, or WebGL framework

---

# Hardware Dependencies

For a real-world railway deployment:

* BLE Beacons
* Wi-Fi infrastructure
* QR markers
* Digital kiosks
* Touchscreens
* Speakers
* QR scanners
* Optional UWB anchors

For passengers:

* Smartphone
* Camera
* Bluetooth support
* Internet connection

---

# External Data Dependencies

A production deployment would require authorized railway data, including:

* Station floor plans
* Platform layouts
* Facility locations
* Entrance and exit information
* Accessibility information
* Platform updates
* Facility availability
* Temporary closures
* Station operational information
* Existing railway application or service APIs where available

For a hackathon prototype, a manually prepared or synthetic station dataset can be used.

---

# Prototype MVP

## MVP Objective

The Minimum Viable Product will demonstrate a **fully functional indoor navigation workflow for one railway station**, rather than attempting to support multiple stations or complete railway integration.


```

## MVP Environment

The prototype will use:

* **One selected railway station**
* A manually prepared digital station map
* A predefined set of facilities and walking paths
* Simulated or QR-based indoor positioning
* A local or cloud backend
* A mobile application
* A kiosk-style interface

The station dataset will contain representative locations such as:

```text
Main Entrance
Ticket Counter
Platform 1
Platform 2
Platform 3
Restroom
Waiting Hall
Food Court
Lift
Escalator
Exit
```

## MVP Features

### 1. Station Digital Map

A digital map representing one railway station with predefined:

* Nodes
* Walking paths
* Facilities
* Platforms
* Accessibility metadata

### 2. Current Location

The user can establish their location by:

* Selecting a location manually, or
* Scanning a QR marker placed at a known location

BLE positioning can be demonstrated as an optional enhancement.

### 3. Destination Search

The user can search for:

* Platform
* Restroom
* Ticket counter
* Food court
* Lift
* Waiting hall
* Exit
* Other configured facilities

### 4. Route Calculation

The system calculates a route using:

**A* or Dijkstra algorithm**

The route is displayed visually on the station map.

### 5. Step-by-Step Navigation

The application generates instructions such as:

```text
Start from Main Entrance.
Walk straight for 40 metres.
Turn right at Ticket Counter.
Take the lift to the next level.
Continue towards Platform 3.
```

### 6. Accessibility Mode

The MVP will include at least one accessibility profile:

**Wheelchair Mode**

The route engine will avoid stairs and prioritize configured accessible paths.

### 7. Voice Guidance

The mobile application converts navigation instructions into speech using Text-to-Speech.

### 8. Kiosk Interface

A kiosk prototype will allow a passenger to:

* Select current location
* Search destination
* View route
* Display a QR code containing the route

### 9. Mobile Route Handoff

The passenger scans the kiosk-generated QR code and opens the same route on the mobile application.

### 10. Simulated Real-Time Update

The MVP will demonstrate one dynamic event.

Example:


The closure can be triggered manually from an administrator/demo interface.

### 11. Basic AI Assistant

The MVP AI assistant will support a limited set of navigation queries, such as:

```text
"Where is Platform 3?"

"Find the nearest restroom."

"Take me to Platform 2 without stairs."

"Where is the nearest lift?"
```

The AI will convert the query into structured navigation information. The route itself will be calculated by the navigation engine.

---



---

# MVP Demo Scenario

The complete SIH demonstration can be presented using one realistic passenger scenario.

### Scenario

A passenger enters the station through the main entrance and needs to reach Platform 3.

The passenger:

1. Opens RailNav 360.
2. Selects the station.
3. Scans a QR marker at the entrance.
4. Searches for Platform 3.
5. Receives the shortest route.
6. Enables wheelchair mode.
7. The system removes the staircase route and selects the accessible route.
8. Voice instructions are activated.
9. During navigation, an administrator marks one corridor as closed.
10. The backend updates the path.
11. The navigation engine calculates an alternative route.
12. The passenger continues using the updated route.

This single scenario demonstrates the core value of the system:

**Location → Search → Routing → Accessibility → Voice Guidance → Real-Time Recalculation**

---

# What Is Included in the MVP

| Component                   | MVP Status |
| --------------------------- | ---------- |
| Single railway station      | Included   |
| Digital station map         | Included   |
| Facility search             | Included   |
| Platform navigation         | Included   |
| QR-based positioning        | Included   |
| A*/Dijkstra routing         | Included   |
| Step-by-step navigation     | Included   |
| Wheelchair routing          | Included   |
| Voice guidance              | Included   |
| Kiosk prototype             | Included   |
| QR kiosk-to-mobile transfer | Included   |
| Simulated path closure      | Included   |
| Dynamic route recalculation | Included   |
| Basic AI navigation queries | Included   |
| Multiple-station support    | Future     |
| Railway production APIs     | Future     |
| Full BLE/UWB positioning    | Future     |
| Nationwide deployment       | Future     |
| Advanced crowd prediction   | Future     |

---

# MVP Success Criteria

The prototype will be considered successful when a user can complete the following workflow without manual intervention:


The MVP therefore focuses on demonstrating a **complete working navigation cycle** rather than maximizing the number of advanced technologies or railway integrations.

---

# Future Scope

After validating the MVP, the system can be extended with:

* BLE/UWB-based high-precision positioning
* Multiple railway stations
* Live Indian Railways data integration
* Real-time train and platform information
* Crowd-density-aware routing
* Computer vision for indoor localization
* Advanced 3D digital twins
* More Indian languages
* Offline navigation
* Dedicated accessibility profiles
* Central railway administration dashboard
* Nationwide deployment

---

# Innovation

The proposed system combines multiple technologies into a single railway navigation platform:

1. **Indoor Navigation**
   Provides navigation where conventional GPS is unreliable.

2. **Digital Twin**
   Maintains a structured digital representation of the station.

3. **Accessibility-Aware Routing**
   Generates routes according to user accessibility requirements.

4. **AI Navigation Assistant**
   Allows passengers to communicate with the navigation system using natural language.

5. **Real-Time Route Recalculation**
   Automatically adapts navigation to station changes.

6. **Multi-Platform Support**
   Provides the same navigation service through mobile applications and digital kiosks.

7. **QR Route Handoff**
   Allows users to transfer a route from a kiosk to their smartphone.

8. **Multilingual and Voice Support**
   Improves usability for a broader range of passengers.

---

# Expected Impact

The solution aims to:

* Reduce passenger confusion inside large railway stations
* Reduce the time required to locate facilities
* Improve accessibility for persons with disabilities
* Support visually impaired passengers through voice navigation
* Provide more efficient passenger movement
* Reduce dependency on staff for basic navigation assistance
* Improve the overall passenger experience
* Provide railway authorities with a framework for managing dynamic station navigation data

---
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/1d892755-966e-47d8-96f3-611302745c7a" />

# Summary

RailNav 360 is designed as a scalable indoor navigation ecosystem for railway stations. The SIH MVP focuses on one station and demonstrates the complete core workflow: locating a passenger, searching for a destination, calculating a route, providing accessible and voice-guided navigation, transferring routes through kiosks, and dynamically recalculating routes when conditions change.

The MVP establishes the technical foundation for future integration with railway-authorized data, live station systems, advanced indoor positioning, and multi-station deployment.
