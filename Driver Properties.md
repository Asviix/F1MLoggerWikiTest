<div style="display: flex; align-items: center; justify-content: flex-end;">
    <h4 style="margin-right: 20px;">F1 Manager 2024 Logger</h1>
    <img src="https://i.imgur.com/sHKYZTk.png" width="100">
</div>

---

# F1 Manager 2024 Telemetry Properties Reference

## Car Table Reference

```c++
public readonly string[] carNames = new string[]
{
        "Ferrari1", "Ferrari2",
        "McLaren1", "McLaren2",
        "RedBull1", "RedBull2",
        "Mercedes1", "Mercedes2",
        "Alpine1", "Alpine2",
        "Williams1", "Williams2",
        "Haas1", "Haas2",
        "RacingBulls1", "RacingBulls2",
        "KickSauber1", "KickSauber2",
        "AstonMartin1", "AstonMartin2",
        "MyTeam1", "MyTeam2"
};
```

**In all instances, replace {name} with the name of car you want the data of, and replace Lap\<x> and Turns[x] with the corresponding Lap and Turn you want the data of.**

*If trying to access historical data that does not exist yet, the data returned will be null.*

More information on how to format the data in [[Data Formatting]].

| Property Name | Type | Live Telemetry | Historical Data | Using Car Focus | Description |
|--------------|------|----------------|-----------------|-----------------|-------------|
| CameraFocusedOn | string | `$prop('F1ManagerPlotter.CameraFocusedOn')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].CameraFocusedOn` | N/A | The car name the camera is focused on |
| TimeSpeed | float | `$prop('F1ManagerPlotter.TimeSpeed')` | N/A | N/A | Time fast-forward multiplicator |
| TimeElapsed | float | `$prop('F1ManagerPlotter.TimeElapsed')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].TimeElapsed` | N/A | Time elapsed in the session |
| LapsRemaining | float | `$prop('F1ManagerPlotter.LapsRemaining')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].LapsRemaining` | N/A | Laps remaining in the race |
| TimeRemaining | float | `$prop('F1ManagerPlotter.TimeRemaining')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].TimeRemaining` | N/A | Time remaining in the session |
| TrackName | string | `$prop('F1ManagerPlotter.TrackName')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].TrackName` | N/A | Track name |
| BestSessionTime | float | `$prop('F1ManagerPlotter.BestSessionTime')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].BestSessionTime` | N/A | Best time in the session |
| RubberState | float | `$prop('F1ManagerPlotter.RubberState')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].RubberState` | N/A | Rubber on track |
| SessionType | string | `$prop('F1ManagerPlotter.SessionType')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].SessionType` | N/A | Type of the session |
| SessionTypeShort | string | `$prop('F1ManagerPlotter.SessionTypeShort')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].SessionTypeShort` | N/A | Short type of the session |
| AirTemp | float | `$prop('F1ManagerPlotter.AirTemp')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].AirTemp` | N/A | Air temperature |
| TrackTemp | float | `$prop('F1ManagerPlotter.TrackTemp')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].TrackTemp` | N/A | Track temperature |
| Weather | string | `$prop('F1ManagerPlotter.Weather')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].Weather` | N/A | Weather condition |
| P1_Car to P22_Car | string | `$prop('F1ManagerPlotter.P1_Car')` to `$prop('F1ManagerPlotter.P22_Car')` | N/A | N/A | Car names in each position |
| {name}_Position | int | `$prop('F1ManagerPlotter.{name}_Position')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].Position` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_Position')` | Car's current position |
| {name}_DriverNumber | int | `$prop('F1ManagerPlotter.{name}_DriverNumber')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].DriverNumber` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_DriverNumber')` | Driver number |
| {name}_DriverFirstName | string | `$prop('F1ManagerPlotter.{name}_DriverFirstName')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].DriverFirstName` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_DriverFirstName')` | Driver first name |
| {name}_DriverLastName | string | `$prop('F1ManagerPlotter.{name}_DriverLastName')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].DriverLastName` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_DriverLastName')` | Driver last name |
| {name}_DriverTeamName | string | `$prop('F1ManagerPlotter.{name}_DriverTeamName')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].TeamName` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_DriverTeamName')` | Driver's team name |
| {name}_PitStopStatus | string | `$prop('F1ManagerPlotter.{name}_PitStopStatus')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].PitStopStatus` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_PitStopStatus')` | Pit stop status |
| {name}_TurnNumber | int | `$prop('F1ManagerPlotter.{name}_TurnNumber')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].TurnNumber` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_TurnNumber')` | Current turn number |
| {name}_CurrentLap | int | `$prop('F1ManagerPlotter.{name}_CurrentLap')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].CurrentLap` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_CurrentLap')` | Current lap number |
| {name}_DistanceTravelled | float | `$prop('F1ManagerPlotter.{name}_DistanceTravelled')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].DistanceTravelled` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_DistanceTravelled')` | Meters travelled in current lap |
| {name}_CurrentLapTime | float | `$prop('F1ManagerPlotter.{name}_CurrentLapTime')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].CurrentLapTime` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_CurrentLapTime')` | Current lap time |
| {name}_DriverBestLap | float | `$prop('F1ManagerPlotter.{name}_DriverBestLap')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].DriverBestLap` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_DriverBestLap')` | Driver's best lap time |
| {name}_LastLapTime | float | `$prop('F1ManagerPlotter.{name}_LastLapTime')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].LastLapTime` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_LastLapTime')` | Last lap time |
| {name}_LastS1Time | float | `$prop('F1ManagerPlotter.{name}_LastS1Time')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].LastS1Time` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_LastS1Time')` | Last sector 1 time |
| {name}_LastS2Time | float | `$prop('F1ManagerPlotter.{name}_LastS2Time')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].LastS2Time` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_LastS2Time')` | Last sector 2 time |
| {name}_LastS3Time | float | `$prop('F1ManagerPlotter.{name}_LastS3Time')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].LastS3Time` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_LastS3Time')` | Last sector 3 time |
| {name}_Speed | int | `$prop('F1ManagerPlotter.{name}_Speed')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].Speed` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_Speed')` | Speed in km/h |
| {name}_Rpm | int | `$prop('F1ManagerPlotter.{name}_Rpm')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].RPM` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_Rpm')` | Engine RPM |
| {name}_Gear | int | `$prop('F1ManagerPlotter.{name}_Gear')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].Gear` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_Gear')` | Current gear |
| {name}_Charge | float | `$prop('F1ManagerPlotter.{name}_Charge')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].Charge` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_Charge')` | ERS charge level |
| {name}_EnergyHarvested | float | `$prop('F1ManagerPlotter.{name}_EnergyHarvested')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].EnergyHarvested` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_EnergyHarvested')` | ERS energy harvested |
| {name}_EnergyDeployed | float | `$prop('F1ManagerPlotter.{name}_EnergyDeployed')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].EnergySpent` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_EnergyDeployed')` | ERS energy deployed |
| {name}_Fuel | float | `$prop('F1ManagerPlotter.{name}_Fuel')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].Fuel` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_Fuel')` | Current fuel level |
| {name}_TireCompound | string | `$prop('F1ManagerPlotter.{name}_TireCompound')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].TireCompound` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_TireCompound')` | Current tire compound |
| {name}_flTemp | float | `$prop('F1ManagerPlotter.{name}_flTemp')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].FLTemp` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_flTemp')` | Front left tire temp |
| {name}_flSurfaceTemp | float | `$prop('F1ManagerPlotter.{name}_flSurfaceTemp')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].FLSurfaceTemp` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_flSurfaceTemp')` | Front left surface temp |
| {name}_flBrakeTemp | float | `$prop('F1ManagerPlotter.{name}_flBrakeTemp')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].FLBrakeTemp` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_flBrakeTemp')` | Front left brake temp |
| {name}_frTemp | float | `$prop('F1ManagerPlotter.{name}_frTemp')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].FRTemp` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_frTemp')` | Front right tire temp |
| {name}_frSurfaceTemp | float | `$prop('F1ManagerPlotter.{name}_frSurfaceTemp')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].FRSurfaceTemp` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_frSurfaceTemp')` | Front right surface temp |
| {name}_frBrakeTemp | float | `$prop('F1ManagerPlotter.{name}_frBrakeTemp')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].FRBrakeTemp` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_frBrakeTemp')` | Front right brake temp |
| {name}_rlTemp | float | `$prop('F1ManagerPlotter.{name}_rlTemp')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].RLTemp` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_rlTemp')` | Rear left tire temp |
| {name}_rlSurfaceTemp | float | `$prop('F1ManagerPlotter.{name}_rlSurfaceTemp')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].RLSurfaceTemp` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_rlSurfaceTemp')` | Rear left surface temp |
| {name}_rlBrakeTemp | float | `$prop('F1ManagerPlotter.{name}_rlBrakeTemp')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].RLBrakeTemp` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_rlBrakeTemp')` | Rear left brake temp |
| {name}_rrTemp | float | `$prop('F1ManagerPlotter.{name}_rrTemp')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].RRTemp` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_rrTemp')` | Rear right tire temp |
| {name}_rrSurfaceTemp | float | `$prop('F1ManagerPlotter.{name}_rrSurfaceTemp')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].RRSurfaceTemp` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_rrSurfaceTemp')` | Rear right surface temp |
| {name}_rrBrakeTemp | float | `$prop('F1ManagerPlotter.{name}_rrBrakeTemp')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].RRBrakeTemp` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_rrBrakeTemp')` | Rear right brake temp |
| {name}_flDeg | float | `$prop('F1ManagerPlotter.{name}_flDeg')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].FLDeg` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_flDeg')` | Front left tire wear |
| {name}_frDeg | float | `$prop('F1ManagerPlotter.{name}_frDeg')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].FRDeg` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_frDeg')` | Front right tire wear |
| {name}_rlDeg | float | `$prop('F1ManagerPlotter.{name}_rlDeg')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].RLDeg` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_rlDeg')` | Rear left tire wear |
| {name}_rrDeg | float | `$prop('F1ManagerPlotter.{name}_rrDeg')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].RRDeg` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_rrDeg')` | Rear right tire wear |
| {name}_PaceMode | string | `$prop('F1ManagerPlotter.{name}_PaceMode')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].PaceMode` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_PaceMode')` | Current pace mode |
| {name}_FuelMode | string | `$prop('F1ManagerPlotter.{name}_FuelMode')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].FuelMode` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_FuelMode')` | Current fuel mode |
| {name}_ERSMode | string | `$prop('F1ManagerPlotter.{name}_ERSMode')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].ERSMode` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_ERSMode')` | Current ERS mode |
| {name}_DRSMode | string | `$prop('F1ManagerPlotter.{name}_DRSMode')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].DRSMode` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_DRSMode')` | Current DRS mode |
| {name}_EngineTemp | float | `$prop('F1ManagerPlotter.{name}_EngineTemp')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].EngineTemp` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_EngineTemp')` | Engine temperature |
| {name}_EngineDeg | float | `$prop('F1ManagerPlotter.{name}_EngineDeg')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].EngineWear` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_EngineDeg')` | Engine wear |
| {name}_GearboxDeg | float | `$prop('F1ManagerPlotter.{name}_GearboxDeg')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].GearboxWear` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_GearboxDeg')` | Gearbox wear |
| {name}_ERSDeg | float | `$prop('F1ManagerPlotter.{name}_ERSDeg')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].ERSWear` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_ERSDeg')` | ERS wear |
| {name}_NameOfCarBehind | string | `$prop('F1ManagerPlotter.{name}_NameOfCarBehind')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].NameOfCarBehind` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_NameOfCarBehind')` | Name of car behind |
| {name}_NameOfCarAhead | string | `$prop('F1ManagerPlotter.{name}_NameOfCarAhead')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].NameOfCarAhead` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_NameOfCarAhead')` | Name of car ahead |
| {name}_GapBehind | float | `$prop('F1ManagerPlotter.{name}_GapBehind')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].GapBehind` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_GapBehind')` | Gap to car behind |
| {name}_GapAhead | float | `$prop('F1ManagerPlotter.{name}_GapAhead')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].GapAhead` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_GapAhead')` | Gap to car ahead |
| {name}_GapToLeader | float | `$prop('F1ManagerPlotter.{name}_GapToLeader')` | `JSON.parse($prop('F1ManagerPlotter.History_{name}.Lap<x>')).Turns[x].GapToLeader` | `$prop('F1ManagerPlotter.'+$prop('F1ManagerPlotter.CameraFocusedOn')+'_GapToLeader')` | Gap to race leader |

---

###### F1 Manager 2024 SimHub Plugin
###### Copyright: Thomas DEFRANCE - 2025