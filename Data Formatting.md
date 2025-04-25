<div align="right">
    <h4>F1 Manager 2024 Logger</h1>
    <img src="https://i.imgur.com/sHKYZTk.png" width="100">
</div>

---

# Data Formatting

Some data points require some type of formatting, since their format might not be what you expect.
The list data in specific formats are displayed below:

## Time Speed

The data returned is plain and simple, the time multiplier for the Sim-Rate in game.
But, when switching speeds since the data is computed by comparing in-game time and real-time, the data might take one or two cycles to stabilize.

## Time Elapsed

The data is the number of seconds that passed since the start of the session.

## Time Remaining

(only when applicable)
The data is the number of seconds remaining in a session.

## Best Session Time

The data is the best lap time of the session in seconds and milliseconds
For example: `92.123` is `1 minutes, 32 seconds and 123 milliseconds`.

## Rubber State

The data is the a float value between 0 and 1 representing the amount of rubber on track.

- `0` is 0%
- `1` is 100%

## Distance Travelled

The data is the number of meters and centimeters travelled by the car in their current lap.
For example: `304.1234` meters.

## Current Lap Time

The data is the number of seconds of that driver's current lap.
For example: `64.123` is `1 minute, 6 seconds and 123 milliseconds`.

## Driver Best Lap

The data is the best lap time of that driver in seconds and milliseconds
For example: `92.123` is `1 minutes, 32 seconds and 123 milliseconds`.

## Last Lap Time

The data is the last lap time of that driver in seconds and milliseconds
For example: `92.123` is `1 minutes, 32 seconds and 123 milliseconds`.

## Last S1/2/3 Time

The data is the last Sector 1/2/3 time of that driver in seconds and milliseconds
For example: `32.123` is `32 seconds and 123 milliseconds`.

## Charge

The data is a float value between 0 and 1 representing the current ERS Charge.

- `0` is 0%
- `1` is 100%

## Tire Age

The data is a integer value between that represents how old the tires are.
This value is calculated when the session is started, so if you load a session at lap 23, it will shows a tire age of 1 on the next lap.

## Energy Harvested

The data is a float value between 0 and 1 representing the amount of ERS Charge Harvested during that lap.

- `0` is 0 MegaJoules
- `1` is 4 MegaJoules

**During a normal first season, the max amount of Charge harvested during a lap is 2 MegaJoules, so that value will never go above 0.5.**

## Energy Deployed

The data is a float value between 0 and 1 representing the amount of ERS Charge Deployed during that lap.

- `0` is 0 MegaJoules
- `1` is 4 MegaJoules

## Tire/Component Wear

All Tire wear data (FL, FR, RL, RR) and Component wear (Engine, ERS, Gearbox) are a float value between 0 and 1 representing their current state.

- `1` is 100% (Max Durability)
- `0` is 0% (Minimum Durability)

## Gap Behind/Ahead/To Leader

This data will differ between different session types:

In Races (Sprint and Normal) the data will be the on track gap in seconds to the cars.

In every other sessions (Practices and Qualifying) the data will the gap between these two driver's best laps.

---

###### F1 Manager 2024 SimHub Plugin

###### Copyright: Thomas DEFRANCE - 2025
