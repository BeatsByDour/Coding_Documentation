
---

type: concept  
category: physics

---

## Overzicht

**Rotatie** is draaiing rond een as; **Koppel** is de kracht die rotatie veroorzaakt. In plaats van direct rotatie in te stellen (Transform.rotation), kun je realistischer rotatie simuleren via koppel en torque, wat natuurlijke draai-effecten creëert.

## Kernidee

- **Directe rotatie**: `transform.rotation = ...` → instant, onrealistisch
- **Torque-based**: `rb.AddTorque(...)` → geleidelijk, natuurlijk, beïnvloed door massa
- **Angular velocity**: `rb.angularVelocity = ...` → instant snelheid, geen acceleratie

Kinematic vs dynamic: kinematic objecten gebruiken `MoveRotation()`, dynamic gebruiken `AddTorque()`.

## Gebruik in Unity

- **Voertuigbesturing**: Yaw/Pitch/Roll via torque
- **Draaiplatforms**: Kinematic `MoveRotation()`
- **Spineffecten**: `AddTorque()` voor natuurlijke spin-up
- **Animation blending**: Transitie van animation naar physics-rotatie

## Veelvoorkomende patronen

- **Flight controls**: Separate pitch (X-as), yaw (Y-as), roll (Z-as) torque
- **Car steering**: Yaw via velocity * steering angle
- **Instant direction change**: `MoveRotation()` voor kinematic objecten
- **Smooth interpolation**: `Quaternion.Slerp()` voor gradual rotation change

## Code voorbeeld

csharp

```
`// Kinematic rotatie (instant, smooth blending) 
Quaternion targetRot = Quaternion.LookRotation(direction); rb.MoveRotation(Quaternion.Slerp(rb.rotation, targetRot, Time.fixedDeltaTime * rotSpeed)); 

// Dynamic rotatie via torque (geleidelijk) 
float yawInput = Input.GetAxis("Horizontal");
rb.AddRelativeTorque(Vector3.up * yawInput * torqueAmount); 

// Instant angular velocity (geen acceleration) 
rb.angularVelocity = Vector3.up * rotationSpeed;`
```

## Valkuilen / Best practices

- **Valkuil**: Transform.rotation wijzigen ipv rb.MoveRotation() → physics conflicts
- **Valkuil**: AddTorque en directe angularVelocity wijziging op dezelfde frame → onverwacht
- **Best practice**: Kies één methode: torque-based (smooth) of MoveRotation (instant)
- **Best practice**: Freeze rotation axes die niet nodig zijn (bijv. X/Z voor top-down game)
- **Best practice**: Zet `maxAngularVelocity` in voor alle dynamic rigidbodies
- **Debugging**: Visualiseer rotation axes met Gizmos

## Gerelateerde componenten

 [[Rigidbody]] - [[Transform]] 

## Gerelateerde functies

 [[Rigidbody.AddTorque]] - [[Rigidbody.MoveRotation]] - [[Rigidbody.angularVelocity (property)]] 

## Gerelateerde concepten

 [[Torque en momentum]] - [[Kinematic vs dynamic rigidbodies]] 