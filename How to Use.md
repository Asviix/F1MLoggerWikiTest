<div align="right">
    <h4>F1 Manager 2024 Logger</h1>
    <img src="https://i.imgur.com/sHKYZTk.png" width="100">
</div>

---

# SimHub Basics

## NCalc vs Jint

### What is NCalc?

NCalc is a mathematical expression evaluator for .NET. It allows users to write and evaluate complex formulas dynamically at runtime. In SimHub, NCalc is used to process telemetry data and create custom calculations, such as determining optimal lap times or fuel usage.

### What is Jint?

Jint is a JavaScript interpreter for .NET. It enables users to write JavaScript code to manipulate data or create advanced logic. In SimHub, Jint is often used for scripting and creating dynamic behaviors, such as custom dashboards or alerts.

We are mainly going to use Jint for all the examples, as it is more flexible and more can be done with it.

## Acessing the data

In SimHub, when you want to show a data point, it must always be "returned", which means for example:

```js
return "Test123"
```

Will show "Test123" in your Overlay.

## Getting data from the plugin

*In this example, we'll use the Driver's current time.*

Remember that bindings must always be returned with "`return`"

*Example :*

```js
return $prop('F1ManagerPlotter.Ferrari1_CurrentLapTime')
```

Will return the CurrentLapTime of the first Ferrari car. (Which is Charles Leclerc on a new save.)

Note the `$prop()` and `'F1ManagerPlotter'`; They are mandatory when returning values in SimHub Jint.

---

###### F1 Manager 2024 SimHub Plugin

###### Copyright: Thomas DEFRANCE - 2025
