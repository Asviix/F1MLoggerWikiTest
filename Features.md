<div align="right">
    <h4>F1 Manager 2024 Logger</h1>
    <img src="https://i.imgur.com/sHKYZTk.png" width="100">
</div>

---

# Features

## 📡 Live Telemetry Data

**Real-time streaming of 1,100+ data points** from F1 Manager 2024 to SimHub, updated at **10ms intervals**.  
*(Powered by memory-mapped files for zero-lag performance.)*

### Key Metrics Tracked

| Category           | Examples                                  | Use Cases                          |
|--------------------|-------------------------------------------|------------------------------------|
| **Driver/Car**     | Speed, RPM, Gear, Fuel, ERS               | Pace analysis, Energy management   |
| **Tires**          | Temps (surface/core), Wear, Brake temps   | Pit strategy, Compound optimization|
| **Session**        | Track temp, Weather, Laps remaining       | Race simulation, AI behavior       |
| **Positioning**    | Gap to leader, Behind, In Front           | Racecraft training                 |

---

## 📂 Data Export

**CSV logging** for post-session analysis with **75+ fields per car**, including:  

```csv
timestamp, trackName, driverNumber, position, speed, flTemp, flDeg, gapToLeader...
```

**Customizable via**:

- Selective driver tracking (export only your team or rivals)

- Automatic folder structure: `Documents/F1ManagerTelemetry/{Track}/{SessionType}/{DriverName}/`

*(Example: Analyze Verstappen’s tire wear at Monaco Q3.)*

## 🕰️ Historical Data Storage

**Turn-by-turn snapshots** for **100 laps per car**, enabling:

**Lap comparison tools** (Sector times vs. tire wear)

**Track evolution analysis** (Rubber buildup effects)

**Machine learning prep** (Time series datasets)

**Data Structure:**

```json
{
  "LapNumber": 5,
  "Turns": {
    "1": { "speed": 312, "flTemp": 87.2, ... },
    "2": { ... }
  }
}
```

## 🛠️ Technical Highlights

| Feature            | Implementation Details                        | Performance Impact                    |
|--------------------|-----------------------------------------------|---------------------------------------|
|Memory-Mapped I/O   | Zero-copy data transfer via MemoryMappedFile  | <1ms latency                          |
|Thread-Safe Locks   | ConcurrentDictionary for historical data      | No UI freezing during heavy writes    |
|Dynamic Grids       | Auto-detects active cars (e.g., DNFs)         | Accurate gaps/positioning             |

---

###### F1 Manager 2024 SimHub Plugin

###### Copyright: Thomas DEFRANCE - 2025
