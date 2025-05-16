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
  - (Can also be customized)

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
    "0": { "speed": 312, "flTemp": 87.2, ... },
    "1": { ... }
  }
}
```

**How to access**:

It can only be accessed with Javascript, using this structure in SimHub:

```js
return JSON.parse($prop("F1ManagerPlotter.{carName}.History.Lap{x}")).Turns[{x}]
```

replace `{carName}` with the name of the care you want the data of, for example Ferrari1, and replace the `{x}` with the Lap/Turn Number you want to analyze.

The data is recorded at the Apex of every turn, with turn 0 being the data recorded at the start finish line.

This data can be insanely useful for on the fly analysis, as in total, the amount of data recorded can be upwards of **2 Millions** !

## 🛠️ Technical Highlights

| Feature            | Implementation Details                        | Performance Impact                    |
|--------------------|-----------------------------------------------|---------------------------------------|
|Memory-Mapped I/O   | Zero-copy data transfer via MemoryMappedFile  | <1ms latency                          |
|Thread-Safe Locks   | ConcurrentDictionary for historical data      | No UI freezing during heavy writes    |
|Dynamic Grids       | Auto-detects active cars (e.g., DNFs)         | Accurate gaps/positioning             |

## 📷 Camera Focus

Using a property called `CameraFocusedOn`, you can get the telemetry of whichever car you're currently looking at using clever Javascript writing! For example:

```js
return $prop("F1ManagerPlotter."+$prop("F1ManagerPlotter.CameraFocusedOn")+"_Speed")
```

In this example, you will get the speed of whatever car is currently focus on the camera! If you were looking at Ferrari1 (Charles Leclerc in a new save), it'd return his speed!

---

###### F1 Manager 2024 SimHub Plugin

###### Copyright: Thomas DEFRANCE - 2025
