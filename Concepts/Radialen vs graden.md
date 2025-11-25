
---

type: concept  
category: physics

---

## Overzicht

**Graden** (°) en **radialen** (rad) zijn twee eenheden voor hoeken. Unity gebruikt intern radialen voor physics (angularVelocity, Quaternions), maar toont in Inspector meestal graden. Deze conversie is essentieel om bugs te voorkomen.

## Kernidee

- **Graden**: 360° = volledige cirkel (intuïtief voor mensen)
- **Radialen**: 2π rad = volledige cirkel (mathematisch standaard)
- **Conversie**: `radians = degrees × (π / 180)` en `degrees = radians × (180 / π)`
- **Unity**: Physics uses radialen, Inspector toont graden

## Gebruik in Unity

- **Angular velocity**: Altijd in radialen (`rb.angularVelocity = new Vector3(0, 3f, 0)` = ~172°/sec)
- **Euler angles**: Inspector toont graden, maar `transform.eulerAngles` en `Quaternion.Euler()` converteren
- **Trigonometrie**: `Mathf.Sin()`, `Mathf.Cos()` verwachten radialen
- **Animations**: Degrees, maar intern meestal radialen

## Veelvoorkomende patronen

- **Rotatiesnelheid**: `rb.angularVelocity = Vector3.up * Mathf.Deg2Rad * degreesPerSecond;`
- **Angle naar quaternion**: `Quaternion.Euler(angleX, angleY, angleZ);`
- **Quaternion naar graden**: `transform.eulerAngles` (dan graden)
- **Trigonometric math**: `Mathf.Sin(Mathf.Deg2Rad * angle)`

## Code voorbeeld

csharp

```
	// Omzetten graden naar radialen 
float spinSpeedDegrees = 360f; 

	// graden per seconde 
float spinSpeedRadians = spinSpeedDegrees * Mathf.Deg2Rad; 
rb.angularVelocity = Vector3.up * spinSpeedRadians; 

	// Omzetten radialen naar graden float currentRadians = rb.angularVelocity.magnitude; 
float currentDegrees = currentRadians * Mathf.Rad2Deg; 

	// Euler angles (Unity handelt conversie automatisch af) 
transform.eulerAngles = new Vector3(45, 90, 0); 

	// graden in inspector 
	// Intern: Quaternion.Euler() converteerd naar radialen 

	// Trigonometric berekening 
float angle = 45f; 
	// graden 
float sinValue = Mathf.Sin(angle * Mathf.Deg2Rad);
```

## Valkuilen / Best practices

- **Valkuil**: Graden direct in `rb.angularVelocity` zetten → 50× te snel rotatie
- **Valkuil**: `Mathf.Sin(angle)` zonder `Deg2Rad` → verkeerde waarde
- **Best practice**: Altijd `Mathf.Deg2Rad` / `Mathf.Rad2Deg` gebruiken bij conversie
- **Best practice**: Documentatie aangeven welke eenheid verwacht wordt (graden/radialen)
- **Best practice**: Constants definiëren voor veelgebruikte conversies
- **Debugging**: Debug.Log() tonen beide eenheden

## Gerelateerde componenten

 [[Rigidbody]] - [[Transform]] 

## Gerelateerde functies

 [[Rigidbody.angularVelocity (property)]] - [[Mathf.Deg2Rad]] - [[Mathf.Rad2Deg]] 

## Gerelateerde concepten

 [[ Rotatie en koppel]] - [[Torque en momentum]] 