
---

type: concept  
category: physics

---

## Overzicht

Het **center of mass** is het balanceringspunt van een object. Krachten toegepast op dit punt veroorzaken alleen lineaire beweging; krachten elders veroorzaken torque. In Unity wordt dit ingesteld via `rb.centerOfMass`.

## Kernidee

- **Op center of mass**: Kracht → rechte beweging, geen rotatie
- **Buiten center of mass**: Kracht → rotatie + lineaire beweging
- **Automatisch**: Standaard berekent Unity center of mass op basis van collider geometrie
- **Manueel**: Override via `rb.centerOfMass` voor realistisch gedrag

## Gebruik in Unity

- **Voertuigen**: Center of mass laag → stabiel, realistisch handelen
- **Torque control**: Know exact waar torque werd toegepast
- **Balanced objects**: Symmetrische objecten met standaard COM
- **Top-heavy objects**: Custom COM voor realistisch kantelen

## Veelvoorkomende patronen

- **Vehicle tuning**: COM laag zetten voor betere handling
- **Humanoid ragdoll**: COM per bot aanpassen (borst zwaarder dan arm)
- **Unstable stacking**: COM hoog voor gemakkelig kantelen

## Code voorbeeld

csharp

```
// Center of mass aanpassen (bijv. voor voertuig) 
rb.centerOfMass = new Vector3(0, -0.5f, 0); 

// Lager = stabieler // COM uitlezen en visueel maken 
Vector3 worldCOM = rb.worldCenterOfMass; 
Debug.DrawLine(rb.position, worldCOM, Color.red); 

// Force toepassen op specifiek punt (veroorzaakt torque) 
Vector3 wheelPosition = new Vector3(2, 0, 0); rb.AddForceAtPosition(Vector3.forward * 100, wheelPosition);
```

## Valkuilen / Best practices

- **Valkuil**: Symmetrische colliders met asymmetrische COM → vreemd gedrag
- **Valkuil**: COM buiten collider-volume → onrealistisch
- **Best practice**: Visueel COM in Scene view debuggen met gizmos
- **Best practice**: Hoe lager COM, hoe stabieler (bijv. voertuigen)
- **Best practice**: COM aanpassen per vehicle/object type, niet per instance
- **Performance**: Reset COM met `rb.ResetCenterOfMass()` na collider wijziging

## Gerelateerde componenten

 [[Rigidbody]] - [[Collider]] 

## Gerelateerde functies

 [[Rigidbody.centerOfMass]] - [[Rigidbody.worldCenterOfMass]] - [[Rigidbody.AddForceAtPosition]] 

## Gerelateerde concepten

[[Torque en momentum]] - [[Forces en beweging]] 